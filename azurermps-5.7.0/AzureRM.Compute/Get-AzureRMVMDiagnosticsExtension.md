---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: D5BEA683-44AE-4D71-827D-02A03F0BEAE9
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRMVMDiagnosticsExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Get-AzureRMVMDiagnosticsExtension.md
ms.openlocfilehash: 32d3d5a152f36c0e4e5f8e3e4e4ecc2b8eb6ee31
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421900"
---
# Get-AzureRmVMDiagnosticsExtension

## SYNOPSIS
Dapatkan pengaturan ekstensi Diagnostik di komputer virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmVMDiagnosticsExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>] [-Status]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmVMDiagnosticsExtension** mendapatkan pengaturan ekstensi Azure Diagnostics di komputer virtual.

## EXAMPLES

### Contoh 1: Terapkan ekstensi diagnostik ke komputer virtual
```
PS C:\> Get-AzureRmVMDiagnosticsExtension -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM22"
```

Perintah ini akan menerapkan ekstensi diagnostik ke komputer virtual bernama ContosoVM22.

## PARAMETERS

### -Nama
Tentukan nama ekstensi Diagnostik yang akan mendapatkan pengaturan cmdlet ini.

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

### -Status
Mengindikasikan bahwa cmdlet ini menggunakan nilai Status.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama komputer virtual yang akan mendapatkan ekstensi Diagnostik dari cmdlet ini.

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

[Remove-AzureRmVMDiagnosticsExtension](./Remove-AzureRmVMDiagnosticsExtension.md)

[Set-AzureRmVMDiagnosticsExtension](./Set-AzureRMVMDiagnosticsExtension.md)


