---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/get-azelasticmonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticMonitor.md
ms.openlocfilehash: ff31822d77d66b730de76388ff73baa374d08836
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146609783"
---
# Get-AzElasticMonitor

## SYNOPSIS
Mendapatkan properti sumber daya monitor tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.elastic/get-azelasticmonitor) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzElasticMonitor [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzElasticMonitor -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzElasticMonitor -InputObject <IElasticIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzElasticMonitor -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan semua monitor elastis di bawah langganan
```powershell
Get-AzElasticMonitor
```

```output
Name                           SkuName                         MonitoringStatus Location      ResourceGroupName
----                           -------                         ---------------- --------      -----------------
kk-elastictest02               ess-monthly-consumption_Monthly Enabled          westus2       kk-rg
kk-elastictest03               ess-monthly-consumption_Monthly Enabled          westus2       kk-rg
wusDeployValidate              ess-monthly-consumption_Monthly Enabled          westus2       poshett-rg
poshett-WestUS2-01             staging_Monthly                 Enabled          westus2       poshett-rg
hashahdemo01                   staging_Monthly                 Enabled          westus2       test-sub
```

Perintah ini mencantumkan semua monitor elastis di bawah langganan.

### Contoh 2: Mencantumkan semua monitor elastis di bawah grup sumber daya
```powershell
Get-AzElasticMonitor -ResourceGroupName azure-elastic-test
```

```output
Name             SkuName                         MonitoringStatus Location ResourceGroupName
----             -------                         ---------------- -------- -----------------
elastic-portal01 ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
elastic-portal02 ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
elastic-pwsh01   ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
elastic-pwsh02   ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
```

Perintah ini mencantumkan semua monitor elastis di bawah grup sumber daya.

### Contoh 3: Mendapatkan properti sumber daya monitor tertentu
```powershell
Get-AzElasticMonitor -ResourceGroupName azure-elastic-test -Name elastic-pwsh02
```

```output
Name           SkuName                         MonitoringStatus Location ResourceGroupName
----           -------                         ---------------- -------- -----------------
elastic-pwsh02 ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
```

Perintah ini mendapatkan properti sumber daya monitor tertentu.

### Contoh 4: Mendapatkan properti sumber daya monitor tertentu menurut alur
```powershell
New-AzElasticMonitor -ResourceGroupName azps-elastic-test -Name elastic-pwsh02 -Location "westus2" -Sku "ess-monthly-consumption_Monthly" -UserInfoEmailAddress 'xxx@microsoft.com' | Get-AzElasticMonitor
```

```output
Name           SkuName                         MonitoringStatus Location ResourceGroupName
----           -------                         ---------------- -------- -----------------
elastic-pwsh02 ess-monthly-consumption_Monthly Enabled          westus2  azure-elastic-test
```

Perintah ini mendapatkan properti sumber daya monitor tertentu menurut alur.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.IElasticIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: Get
Aliases: MonitorName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya Elastic berada.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000)

```yaml
Type: System.String[]
Parameter Sets: Get, List, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.IElasticIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.IElasticMonitorResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IElasticIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya Elastic berada.
  - `[RuleSetName <String>]`: Nama sumber daya Seperangkat Aturan Tag
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000)

## RELATED LINKS

