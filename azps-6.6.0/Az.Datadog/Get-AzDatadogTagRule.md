---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/get-azdatadogtagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogTagRule.md
ms.openlocfilehash: 967d27a9a6ea36531811e8977fe3c5f21fae183a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141957723"
---
# Get-AzDatadogTagRule

## SYNOPSIS
Dapatkan kumpulan aturan tag untuk sumber daya monitor tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datadog/get-azdatadogtagrule) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDatadogTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzDatadogTagRule -MonitorName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDatadogTagRule -InputObject <IDatadogIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan kumpulan aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan semua aturan tag yang ditetapkan untuk sumber daya monitor tertentu
```powershell
PS C:\> Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mencantumkan semua aturan tag yang ditetapkan untuk sumber daya monitor tertentu.

### Contoh 2: Dapatkan kumpulan aturan tag untuk sumber daya monitor tertentu
```powershell
PS C:\> Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default'

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mendapatkan kumpulan aturan tag untuk sumber daya monitor tertentu.

### Contoh 3: Dapatkan kumpulan aturan tag untuk sumber daya monitor tertentu menurut pipeline
```powershell
PS C:\> Get-AzDatadogTagRule -ResourceGroupName azure-rg-Datadog -MonitorName Datadog -Name 'default' | Get-AzDatadogTagRule

Name    Type
----    ----
default microsoft.Datadog/monitors/tagrules
```

Perintah ini mendapatkan kumpulan aturan tag untuk sumber daya monitor tertentu menurut saluran.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity
Parameter Sets: GetViaIdentity
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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kumpulan aturan

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
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: Get, List
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
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.IDatadogIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.IMonitoringTagRules

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDatadogIdentity>: Parameter Identitas
  - `[ConfigurationName <String>]`: Nama konfigurasi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[RuleSetName <String>]`: Nama kumpulan aturan
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

