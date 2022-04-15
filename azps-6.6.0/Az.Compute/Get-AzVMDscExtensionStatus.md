---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 695F224D-DA25-49F2-916E-25DA2A48A4A7
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmdscextensionstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMDscExtensionStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMDscExtensionStatus.md
ms.openlocfilehash: 298834e5d6b9a24f01c87f459420fb5f23e86f11
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142272715"
---
# Get-AzVMDscExtensionStatus

## SYNOPSIS
Mendapatkan status pengatur ekstensi DSC untuk mesin virtual.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/get-azvmdscextensionstatus) untuk informasi terbaru.

## SYNTAX

### GetDscExtension (Default)
```
Get-AzVMDscExtensionStatus [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### VMParameterSet
```
Get-AzVMDscExtensionStatus [-VM <PSVirtualMachine>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMDscExtensionStatus** mendapatkan status handler ekstensi Konfigurasi Negara Yang Diinginkan (DSC) untuk mesin virtual dalam grup sumber daya.
Ketika konfigurasi diterapkan cmdlet ini menghasilkan output yang konsisten dengan cmdlet Start-DscConfiguration.

## EXAMPLES

### Contoh 1

Mendapatkan status pengatur ekstensi DSC untuk mesin virtual. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
Get-AzVMDscExtensionStatus -Name 'AgentPool01' -ResourceGroupName myresourcegroup -VMName 'VM01'
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Menentukan nama sumber daya Azure Resource Manager yang mewakili ekstensi.
Cmdlet Set-AzVMDscExtension mengatur nama ini ke Microsoft.Powershell.DSC, yang merupakan nilai yang sama yang digunakan oleh **Get-AzVMDscExtensionStatus**.
Tentukan parameter ini hanya jika Anda mengubah nama default dalam cmdlet Atur atau menggunakan nama sumber daya yang berbeda dalam templat Resource Manager.

```yaml
Type: System.String
Parameter Sets: GetDscExtension
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya mesin virtual.

```yaml
Type: System.String
Parameter Sets: GetDscExtension
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin maya tempat ekstensi diaktifkan.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: VMParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual tempat cmdlet ini mendapatkan status ekstensi DSC.

```yaml
Type: System.String
Parameter Sets: GetDscExtension
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineInstanceView

## CATATAN

## RELATED LINKS

[Set-AzVMDscExtension](./Set-AzVMDscExtension.md)


