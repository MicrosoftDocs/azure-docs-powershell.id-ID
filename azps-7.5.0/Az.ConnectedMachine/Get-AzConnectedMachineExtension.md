---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/get-azconnectedmachineextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Get-AzConnectedMachineExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Get-AzConnectedMachineExtension.md
ms.openlocfilehash: 10ef1f8d6c71e955f1bcd0e4e6b38ab7e82a27e3
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145817010"
---
# Get-AzConnectedMachineExtension

## SYNOPSIS
Operasi untuk mendapatkan ekstensi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.connectedmachine/get-azconnectedmachineextension) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzConnectedMachineExtension -MachineName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-Expand <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedMachineExtension -MachineName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk mendapatkan ekstensi.

## EXAMPLES

### Contoh 1: Mencantumkan semua ekstensi untuk komputer
```powershell
Get-AzConnectedMachineExtension -ResourceGroupName contoso-connected-machines -MachineName winwestus2_2
```

```output
Name    Location  PropertiesType        ProvisioningState
----    --------  --------------        -----------------
custom  westus2   CustomScriptExtension Succeeded
custom  westus2   CustomScriptExtension Succeeded
dsc     westus2   DSC                   Succeeded
```

Mencantumkan semua ekstensi untuk komputer tertentu.

### Contoh 2: Mendapatkan ekstensi tertentu pada komputer
```powershell
Get-AzConnectedMachineExtension -ResourceGroupName contoso-connected-machines -MachineName winwestus2_2 -Name dsc
```

```output
Name  Location  PropertiesType        ProvisioningState
----  --------  --------------        -----------------
dsc   westus2   CustomScriptExtension Succeeded
```

Mendapatkan ekstensi tertentu pada komputer.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Perluas
Ekspresi perluas untuk diterapkan pada operasi.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Nama komputer yang berisi ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ekstensi komputer.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtension

## NOTES

ALIAS

## RELATED LINKS

