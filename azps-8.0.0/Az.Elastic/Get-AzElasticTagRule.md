---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/get-azelastictagrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticTagRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticTagRule.md
ms.openlocfilehash: f99ef71994cd1aa83ed48a7301177238d2d4cda8
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146606010"
---
# Get-AzElasticTagRule

## SYNOPSIS
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

## SYNTAX

### Dapatkan (Default)
```
Get-AzElasticTagRule -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzElasticTagRule -InputObject <IElasticIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu
```powershell
Get-AzElasticTagRule -ResourceGroupName azure-elastic-test -MonitorName elastic-pwsh02
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         azure-elastic-test
```

Perintah ini mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu.

### Contoh 2: Mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu menurut alur
```powershell
New-AzElasticTagRule -ResourceGroupName azps-elastic-test -MonitorName elastic-pwsh02 | Get-AzElasticTagRule
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         azure-elastic-test
```

Perintah ini mendapatkan seperangkat aturan tag untuk sumber daya monitor tertentu menurut alur.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -MonitorName
Memantau nama sumber daya

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
Nama grup sumber daya tempat sumber daya Elastic berada.

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

### -SubscriptionId
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

```yaml
Type: System.String[]
Parameter Sets: Get
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

### Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.Api20200701.IMonitoringTagRules

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IElasticIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya Elastic berada.
  - `[RuleSetName <String>]`: Nama sumber daya Seperangkat Aturan Tag
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

## RELATED LINKS

