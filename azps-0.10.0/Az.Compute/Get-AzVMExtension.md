---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 842652D4-0F1C-4D0D-AB55-0D43D3C5D82A
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/get-azvmextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Get-AzVMExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Get-AzVMExtension.md
ms.openlocfilehash: a8ac31efd77d5b8ff5c07920bb14b44f80ac0955
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143358803"
---
# Get-AzVMExtension

## SYNOPSIS
Dapatkan properti Ekstensi Mesin Virtual yang terinstal di mesin virtual.

## SYNTAX

```
Get-AzVMExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String> [-Status]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMExtension** mendapatkan properti Ekstensi Mesin Virtual yang diinstal pada mesin virtual.
Tentukan nama ekstensi untuk mendapatkan properti.
Untuk mendapatkan hanya tampilan instans ekstensi, tentukan parameter Status.

## EXAMPLES

### Contoh 1: Mendapatkan properti ekstensi
```
PS C:\> Get-AzVMExtension -ResourceGroupName "ResourceGroup11" -VMName "VirtualMachine22" -Name "CustomScriptExtension"
```

Perintah ini mendapatkan properti untuk ekstensi bernama CustomScriptExtension pada mesin virtual bernama VirtualMachine22 dalam grup sumber daya ResourceGroup11.

### Contoh 2: Mendapatkan tampilan instans ekstensi
```
PS C:\> Get-AzVMExtension -ResourceGroupName "ResourceGroup11" -VMName "VirtualMachine22" -Name "CustomScriptExtension" -Status
```

Perintah ini mendapatkan tampilan instans untuk ekstensi bernama CustomScriptExtension pada mesin virtual bernama VirtualMachine22 dalam grup sumber daya ResourceGroup11.

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
Menentukan nama ekstensi.
Cmdlet ini mendapatkan properti untuk ekstensi yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

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
Menunjukkan bahwa cmdlet ini hanya mendapatkan tampilan instans ekstensi.

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
Menentukan nama mesin virtual.
Cmdlet ini mendapatkan properti ekstensi dari mesin virtual yang ditentukan parameter ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineExtension

## NOTES

## RELATED LINKS

[Remove-AzVMExtension](./Remove-AzVMExtension.md)

[Set-AzVMExtension](./Set-AzVMExtension.md)


