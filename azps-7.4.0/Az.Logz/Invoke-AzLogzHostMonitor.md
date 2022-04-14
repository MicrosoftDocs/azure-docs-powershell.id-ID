---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/invoke-azlogzhostmonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Invoke-AzLogzHostMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Invoke-AzLogzHostMonitor.md
ms.openlocfilehash: 4784cb313454d7e554bb9c1735a4e7b275a5fd91
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177737"
---
# Invoke-AzLogzHostMonitor

## SYNOPSIS
Mengembalikan muatan yang perlu dilewati dalam isi permintaan untuk menginstal agen Logz.io pada VM.

## SYNTAX

### Host (Default)
```
Invoke-AzLogzHostMonitor -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### HostViaIdentitas
```
Invoke-AzLogzHostMonitor -InputObject <ILogzIdentity> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan muatan yang perlu dilewati dalam isi permintaan untuk menginstal agen Logz.io pada VM.

## EXAMPLES

### Contoh 1: Mengembalikan muatan yang perlu dialihkan dalam isi permintaan untuk menginstal agen Logz.io di VM
```powershell
Invoke-AzLogzHostMonitor -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04
```

```output
ApiKey                           Region
------                           ------
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx   westus2
```

Perintah ini mengembalikan muatan yang perlu dilewatkan dalam isi permintaan untuk menginstal agen Logz.io pada VM.

### Contoh 2: Mengembalikan muatan yang perlu dialihkan dalam isi permintaan untuk menginstal agen Logz.io pada VM menurut pipeline
```powershell
Get-AzLogzMonitor -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 | Invoke-AzLogzHostMonitor
```

```output
ApiKey                           Region
------                           ------
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx   westus2
```

Perintah ini mengembalikan muatan yang perlu dilewati dalam isi permintaan untuk menginstal agen Logz.io pada VM menurut pipeline.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity
Parameter Sets: HostViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MonitorName
Pantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: Host
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: Host
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
Type: System.String
Parameter Sets: Host
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.ILogzIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IVMExtensionPayload

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ILogzIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[RuleSetName <String>]`: 
  - `[SubAccountName <String>]`: Nama sumber daya Sub Akun
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

