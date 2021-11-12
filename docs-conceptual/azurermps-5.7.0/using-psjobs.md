---
title: Menjalankan cmdlet secara paralel menggunakan pekerjaan PowerShell
description: Cara menjalankan cmdlet secara paralel menggunakan parameter -AsJob.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/11/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: b5385a9fa3da508e6f0841baea2e4bcd20503b9f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425045"
---
# <a name="running-cmdlets-in-parallel-using-powershell-jobs"></a>Menjalankan cmdlet secara paralel menggunakan pekerjaan PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

PowerShell mendukung tindakan asinkron dengan [Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).
Azure PowerShell sangat bergantung pada pembuatan, dan menunggu, panggilan jaringan ke Azure. Sebagai pengembang, Anda mungkin sering mendapati diri Anda mencari untuk melakukan beberapa panggilan yang tidak memblokir ke Azure dalam satu skrip, atau Anda mungkin menemukan bahwa Anda ingin membuat sumber daya Azure di REPL tanpa memblokir sesi saat ini. Untuk mengatasi kebutuhan ini, Azure PowerShell menyediakan dukungan [PSJob kelas](/powershell/module/microsoft.powershell.core/about/about_jobs) satu.

## <a name="context-persistence-and-psjobs"></a>Persistensi Konteks dan PSJobs

PSJobs dijalankan dalam proses terpisah, yang berarti bahwa informasi tentang koneksi Azure Anda harus dibagikan dengan benar dengan pekerjaan yang Anda buat. Setelah menyambungkan akun Azure ke sesi PowerShell dengan `Connect-AzureRmAccount` , Anda dapat menyampaikan konteks ke pekerjaan.

```azurepowershell-interactive
$creds = Get-Credential
$job = Start-Job { param($context,$vmadmin) New-AzureRmVM -Name MyVm -AzureRmContext $context -Credential $vmadmin} -Arguments (Get-AzureRmContext),$creds
```

Namun, jika Anda telah memilih untuk membuat konteks Anda disimpan secara otomatis dengan , konteks akan otomatis `Enable-AzureRmContextAutosave` dibagikan dengan pekerjaan yang Anda buat.

```azurepowershell-interactive
Enable-AzureRmContextAutosave
$creds = Get-Credential
$job = Start-Job { param($vmadmin) New-AzureRmVM -Name MyVm -Credential $vmadmin} -Arguments $creds
```

## <a name="automatic-jobs-with--asjob"></a>Pekerjaan Otomatis dengan `-AsJob`

Demi kenyamanan, Azure PowerShell menyediakan `-AsJob` pengalih pada beberapa cmdlet yang berjalan dalam waktu lama.
Sakelar `-AsJob` membuat PSJobs lebih mudah.

```azurepowershell-interactive
$creds = Get-Credential
$job = New-AzureRmVM -Name MyVm -Credential $creds -AsJob
```

Anda dapat memeriksa pekerjaan dan kemajuan kapan saja dengan `Get-Job` dan `Get-AzureRmVM` .

```azurepowershell-interactive
Get-Job $job
Get-AzureRmVM MyVm
```

```output
Id Name                                       PSJobTypeName         State   HasMoreData Location  Command
-- ----                                       -------------         -----   ----------- --------  -------
1  Long Running Operation for 'New-AzureRmVM' AzureLongRunningJob`1 Running True        localhost New-AzureRmVM

ResourceGroupName    Name Location          VmSize  OsType     NIC ProvisioningState Zone
-----------------    ---- --------          ------  ------     --- ----------------- ----
MyVm                 MyVm   eastus Standard_DS1_v2 Windows    MyVm          Creating
```

Kemudian, setelah selesai, Anda dapat memperoleh hasil pekerjaan menggunakan `Receive-Job` .

> [!NOTE]
> `Receive-Job` mengembalikan hasil dari cmdlet seperti jika `-AsJob` bendera tidak ada.
> Misalnya, `Receive-Job` hasil dari tipe yang sama dengan hasil `Do-Action -AsJob` `Do-Action` .

```azurepowershell-interactive
$vm = Receive-Job $job
$vm
```

```output
ResourceGroupName        : MyVm
Id                       : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyVm/providers/Microsoft.Compute/virtualMachines/MyVm
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

## <a name="example-scenarios"></a>Contoh Skenario

Membuat beberapa VM sekaligus.

```azurepowershell-interactive
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

Dalam contoh ini, `Wait-Job` cmdlet menyebabkan skrip untuk dijeda saat pekerjaan berjalan. Skrip terus menjalankan setelah semua pekerjaan telah selesai. Ini memungkinkan Anda membuat beberapa pekerjaan yang berjalan secara paralel lalu menunggu penyelesaian sebelum melanjutkan.

```output
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
