---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D5BEA683-44AE-4D71-827D-02A03F0BEAE9
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmdiagnosticsextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMDiagnosticsExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVMDiagnosticsExtension.md
ms.openlocfilehash: ff65e5f5e41b7b846866b08bf8210f3f4c21f67d
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138286972"
---
# Get-AzVMDiagnosticsExtension

## SYNOPSIS
Dapatkan pengaturan ekstensi Diagnostik di komputer virtual.

## SYNTAX

```
Get-AzVMDiagnosticsExtension [-ResourceGroupName] <String> [-VMName] <String> [[-Name] <String>] [-Status]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVMDiagnosticsExtension** mendapatkan pengaturan ekstensi Azure Diagnostics di komputer virtual.

## EXAMPLES

### Contoh 1: Terapkan ekstensi diagnostik ke komputer virtual
```powershell
PS C:\> Get-AzVMDiagnosticsExtension -ResourceGroupName "ResourceGroup11" -VMName "ContosoVM22"
```

Perintah ini akan menerapkan ekstensi diagnostik ke komputer virtual bernama ContosoVM22.

### Contoh 2

Dapatkan pengaturan ekstensi Diagnostik di komputer virtual. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
Get-AzVMDiagnosticsExtension -Name 'AgentPool01' -ResourceGroupName 'ResourceGroup11' -Status -VMName 'ContosoVM22'
```

## PARAMETERS

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

### -Nama
Tentukan nama ekstensi Diagnostik yang akan mendapatkan pengaturan cmdlet ini.

```yaml
Type: System.String
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
Type: System.String
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachineExtension

## CATATAN

## RELATED LINKS

[Remove-AzVMDiagnosticsExtension](./Remove-AzVMDiagnosticsExtension.md)

[Set-AzVMDiagnosticsExtension](./Set-AzVMDiagnosticsExtension.md)


