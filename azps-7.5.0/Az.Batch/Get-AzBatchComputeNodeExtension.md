---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchcommandnodeextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchComputeNodeExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchComputeNodeExtension.md
ms.openlocfilehash: 2f0725754be838fea1d4ad8174318b28f515535c
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145745002"
---
# Get-AzBatchComputeNodeExtension

## SYNOPSIS
Mendapatkan ekstensi simpul komputasi Batch dari simpul komputasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.batch/get-azbatchcomputenodeextension) untuk informasi terbaru.

## SYNTAX

### Id (Default)
```
Get-AzBatchComputeNodeExtension [-PoolId] <String> [-ComputeNodeId] <String> [[-Name] <String>]
 [-Select <String>] [-MaxCount <Int32>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObject
```
Get-AzBatchComputeNodeExtension [-Pool] <PSCloudPool> [-ComputeNodeId] <String> [[-Name] <String>]
 [-Select <String>] [-MaxCount <Int32>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Jika nama ekstensi disediakan, satu ekstensi dengan nama yang cocok dikembalikan dari simpul komputasi yang disediakan (jika ditemukan). Jika tidak, semua ekstensi pada simpul komputasi dikembalikan. Detail ekstensi lebih lanjut dapat ditemukan pada Properti VmExtension ekstensi.

## EXAMPLES

### Contoh 1 Dapatkan semua ekstensi dari simpul komputasi.
```powershell
PS C:\> Get-AzBatchComputeNodeExtension "testPool" "testNode" -BatchContext $context

InstanceView                                                    ProvisioningState VmExtension
------------                                                    ----------------- -----------
Microsoft.Azure.Commands.Batch.Models.PSVMExtensionInstanceView Succeeded         Microsoft.Azure.Commands.Batch.Models.PSVMExtension
Microsoft.Azure.Commands.Batch.Models.PSVMExtensionInstanceView Failed            Microsoft.Azure.Commands.Batch.Models.PSVMExtension
```

### Contoh 2 Dapatkan ekstensi tertentu dari simpul komputasi.

```powershell
PS C:\> Get-AzBatchComputeNodeExtension "testPool" "testNode" "secretext" -BatchContext $context

InstanceView                                                    ProvisioningState VmExtension
------------                                                    ----------------- -----------
Microsoft.Azure.Commands.Batch.Models.PSVMExtensionInstanceView Failed            Microsoft.Azure.Commands.Batch.Models.PSVMExtension
```

## PARAMETERS

### -BatchContext
Instans BatchAccountContext untuk digunakan saat berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch.
Untuk menggunakan autentikasi kunci bersama sebagai gantinya, gunakan cmdlet Get-AzBatchAccountKeys untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi.
Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default.
Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

```yaml
Type: Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNodeId
Id simpul komputasi tempat ekstensi berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum ekstensi simpul komputasi yang akan dikembalikan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ekstensi yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pool
Kumpulan tempat simpul komputasi ekstensi berada.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudPool
Parameter Sets: ParentObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PoolId
Id kumpulan tempat simpul komputasi ekstensi berada.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pilih
Menentukan klausa pilih OData.
Tentukan nilai untuk parameter ini untuk mendapatkan properti tertentu daripada semua properti objek.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudPool

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSNodeVMExtension

## NOTES

## RELATED LINKS
