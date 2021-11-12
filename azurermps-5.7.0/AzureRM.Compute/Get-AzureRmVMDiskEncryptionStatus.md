---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: E6F91D2E-6481-44C2-AF21-F62947C3D78C
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRmVMDiskEncryptionStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRmVMDiskEncryptionStatus.md
ms.openlocfilehash: 9ec94d0c11bf9302156355c28566ce16f48ae148
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428548"
---
# Get-AzureRmVMDiskEncryptionStatus

## SYNOPSIS
Mendapatkan status enkripsi mesin virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVMDiskEncryptionStatus [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVMDiskEncryptionStatus** mendapatkan status enkripsi mesin virtual.
Area ini menampilkan status enkripsi sistem operasi dan volume data.
Selain status enkripsi, ia juga menampilkan URL rahasia enkripsi, URL kunci enkripsi kunci, ID sumber daya **KeyVault di** mana kunci enkripsi dan kunci enkripsi kunci untuk volume sistem operasi ada.

## EXAMPLES

### Contoh 1: Mendapatkan status enkripsi dari mesin virtual
```
PS C:\> Get-AzureRmVmDiskEncryptionStatus -ResourceGroupName "MyResourceGroup001" -VMName "VM001"
```

Perintah ini mendapatkan status enkripsi mesin virtual bernama VM001.

## PARAMETERS

### -Nama
```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

## CATATAN

## RELATED LINKS

[Remove-AzureRmVMDiskEncryptionExtension](./Remove-AzureRmVMDiskEncryptionExtension.md)

[Set-AzureRmVMDiskEncryptionExtension](./Set-AzureRmVMDiskEncryptionExtension.md)


