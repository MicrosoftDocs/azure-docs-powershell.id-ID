---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 89DA3965-5344-4A1D-AEF1-10EA58E129CF
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/remove-azurermvmdiagnosticsextension
schema: 2.0.0
ms.openlocfilehash: 57e3aef7ff5b6acece0ccba1505d33f2add05ae2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142928783"
---
# Remove-AzureRmVMDiagnosticsExtension

## SYNOPSIS
Menghapus ekstensi Diagnostik dari mesin virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmVMDiagnosticsExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmVMDiagnosticsExtension** menghapus ekstensi Diagnostik Azure dari mesin virtual.
Anda harus meneruskan output cmdlet ini ke cmdlet Update-AzureRmVM untuk menerapkan perubahan Anda.

## EXAMPLES

### Contoh 1: Hapus ekstensi Diagnostik dari mesin virtual
```
PS C:\> Remove-AzureRmVMDiagnosticsExtension -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM22" | Update-AzureRmVM
```

Perintah ini menghapus ekstensi Diagnostik dari mesin virtual bernama ContosoVM22.
Perintah melewati hasil ke cmdlet Update-AzureRmVM menggunakan operator pipeline.
Perintah itu memperbarui mesin virtual.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama ekstensi Diagnostik yang dihapus cmdlet ini.

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
Menentukan nama grup sumber daya mesin virtual.

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
Menentukan nama mesin virtual tempat cmdlet ini menghapus ekstensi Diagnostik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureRmVMDiagnosticsExtension](./Get-AzureRMVMDiagnosticsExtension.md)

[Set-AzureRmVMDiagnosticsExtension](./Set-AzureRMVMDiagnosticsExtension.md)

[Perbarui-AzureRmVM](./Update-AzureRmVM.md)


