---
title: Menjalankan cmdlet secara paralel dengan menggunakan pekerjaan PowerShell
description: Cara menjalankan cmdlet secara paralel dengan menggunakan parameter -AsJob.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 70cf7b8e0046a1402ec2d3b93a161d13f5c7a67f
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429340"
---
# <a name="running-cmdlets-in-parallel-using-powershell-jobs"></a>Menjalankan cmdlet secara paralel dengan menggunakan pekerjaan PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

PowerShell mendukung tindakan asinkron dengan [Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs). Azure PowerShell sangat bergantung pada pembuatan, dan menunggu, panggilan jaringan ke Azure. Anda mungkin sering merasa perlu membuat panggilan non-pemblokiran. Untuk mengatasi kebutuhan ini, Azure PowerShell menyediakan dukungan [PSJob](/powershell/module/microsoft.powershell.core/about/about_jobs) kelas satu.

## <a name="context-persistence-and-psjobs"></a>Persistensi Konteks dan PSJobs

Karena PSJobs dijalankan sebagai proses terpisah, koneksi Azure Anda harus dibagikan dengan PSJobs. Setelah masuk ke akun Azure Anda dengan `Connect-AzureRmAccount`, berikan konteks ke pekerjaan.

```azurepowershell
$creds = Get-Credential
$job = Start-Job { param($context,$vmadmin) New-AzureRmVM -Name MyVm -AzureRmContext $context -Credential $vmadmin} -Arguments (Get-AzureRmContext),$creds
```

Namun, jika Anda telah memilih untuk menyimpan konteks Anda secara otomatis dengan `Enable-AzureRmContextAutosave`, konteks dibagikan secara otomatis dengan pekerjaan yang Anda buat.

```azurepowershell
Enable-AzureRmContextAutosave
$creds = Get-Credential
$job = Start-Job { param($vmadmin) New-AzureRmVM -Name MyVm -Credential $vmadmin} -Arguments $creds
```

## <a name="automatic-jobs-with--asjob"></a>Pekerjaan Otomatis dengan `-AsJob`

Untuk kemudahan, Azure PowerShell juga menyediakan sakelar `-AsJob` di beberapa cmdlet yang berjalan lama.
Sakelar `-AsJob` memudahkan pembuatan PSJobs.

```azurepowershell
$creds = Get-Credential
$job = New-AzureRmVM -Name MyVm -Credential $creds -AsJob
```

Anda dapat memeriksa pekerjaan dan kemajuan kapan saja dengan `Get-Job` dan `Get-AzureRmVM`.

```azurepowershell
Get-Job $job
Get-AzureRmVM MyVm
```

```Output
Id Name                                       PSJobTypeName         State   HasMoreData Location  Command
-- ----                                       -------------         -----   ----------- --------  -------
1  Long Running Operation for 'New-AzureRmVM' AzureLongRunningJob`1 Running True        localhost New-AzureRmVM

ResourceGroupName    Name Location          VmSize  OsType     NIC ProvisioningState Zone
-----------------    ---- --------          ------  ------     --- ----------------- ----
MyVm                 MyVm   eastus Standard_DS1_v2 Windows    MyVm          Creating
```

Ketika pekerjaan selesai, dapatkan hasil pekerjaan dengan `Receive-Job`.

> [!NOTE]
> `Receive-Job` mengembalikan hasil dari cmdlet seolah-olah bendera `-AsJob` tidak ada. Misalnya, hasil `Receive-Job` dari `Do-Action -AsJob` berasal dari jenis yang sama dengan hasil dari `Do-Action`.

```azurepowershell
$vm = Receive-Job $job
$vm
```

```Output
ResourceGroupName        : MyVm
Id                       : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyVm/providers/Microsoft.Compute/virtualMachines/MyVm
VmId                     : dff1f79e-a8f7-4664-ab72-0ec28b9fbb5b
Name                     : MyVm
Type                     : Microsoft.Compute/virtualMachines
Location                 : eastus
Tags                     : {}
HardwareProfile          : {VmSize}
NetworkProfile           : {NetworkInterfaces}
OSProfile                : {ComputerName, AdminUsername, WindowsConfiguration, Secrets}
ProvisioningState        : Succeeded
StorageProfile           : {ImageReference, OsDisk, DataDisks}
FullyQualifiedDomainName : myvmmyvm.eastus.cloudapp.azure.com
```

## <a name="example-scenarios"></a>Skenario Contoh

Membuat beberapa VM sekaligus:

```azurepowershell
$creds = Get-Credential
# Create 10 jobs.
for($k = 0; $k -lt 10; $k++) {
    New-AzureRmVm -Name MyVm$k  -Credential $creds -AsJob
}

# Get all jobs and wait on them.
Get-Job | Wait-Job
"All jobs completed"
Get-AzureRmVM
```

Dalam contoh ini, cmdlet `Wait-Job` menyebabkan skrip berhenti sejenak saat pekerjaan berjalan. Skrip terus berjalan setelah semua pekerjaan selesai. Beberapa pekerjaan berjalan secara paralel kemudian skrip menunggu penyelesaian sebelum melanjutkan.

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
3      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
4      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
5      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
6      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
7      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
8      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
9      Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
10     Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
11     Long Running... AzureLongRun... Running       True            localhost            New-AzureRmVM
2      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
3      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
4      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
5      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
6      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
7      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
8      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
9      Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
10     Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
11     Long Running... AzureLongRun... Completed     True            localhost            New-AzureRmVM
All Jobs completed.

ResourceGroupName        Name   Location          VmSize  OsType           NIC ProvisioningState Zone
-----------------        ----   --------          ------  ------           --- ----------------- ----
MYVM                     MyVm     eastus Standard_DS1_v2 Windows          MyVm         Succeeded
MYVM0                   MyVm0     eastus Standard_DS1_v2 Windows         MyVm0         Succeeded
MYVM1                   MyVm1     eastus Standard_DS1_v2 Windows         MyVm1         Succeeded
MYVM2                   MyVm2     eastus Standard_DS1_v2 Windows         MyVm2         Succeeded
MYVM3                   MyVm3     eastus Standard_DS1_v2 Windows         MyVm3         Succeeded
MYVM4                   MyVm4     eastus Standard_DS1_v2 Windows         MyVm4         Succeeded
MYVM5                   MyVm5     eastus Standard_DS1_v2 Windows         MyVm5         Succeeded
MYVM6                   MyVm6     eastus Standard_DS1_v2 Windows         MyVm6         Succeeded
MYVM7                   MyVm7     eastus Standard_DS1_v2 Windows         MyVm7         Succeeded
MYVM8                   MyVm8     eastus Standard_DS1_v2 Windows         MyVm8         Succeeded
MYVM9                   MyVm9     eastus Standard_DS1_v2 Windows         MyVm9         Succeeded
```
