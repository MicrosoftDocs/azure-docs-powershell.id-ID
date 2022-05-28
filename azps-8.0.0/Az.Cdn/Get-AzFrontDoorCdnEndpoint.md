---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azfrontdoorcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Get-AzFrontDoorCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Get-AzFrontDoorCdnEndpoint.md
ms.openlocfilehash: 3c629c89b93095256a70f8167a59dc20f7aabc4f
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145558525"
---
# Get-AzFrontDoorCdnEndpoint

## SYNOPSIS
Mendapatkan titik akhir AzureFrontDoor yang sudah ada dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzFrontDoorCdnEndpoint -ProfileName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzFrontDoorCdnEndpoint -InputObject <ICdnIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan titik akhir AzureFrontDoor yang sudah ada dengan nama titik akhir yang ditentukan di bawah langganan, grup sumber daya, dan profil yang ditentukan.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

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

### -EndpointName
Nama titik akhir di bawah profil yang unik secara global.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProfileName
Nama profil Premium Azure Front Door Standard atau Azure Front Door yang unik dalam grup sumber daya.

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

### -ResourceGroupName
Nama grup Sumber Daya dalam langganan Azure.

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
ID Langganan Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IAfdEndpoint

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <ICdnIdentity>: Parameter Identitas
  - `[CustomDomainName <String>]`: Nama domain di bawah profil yang unik secara global.
  - `[EndpointName <String>]`: Nama titik akhir di bawah profil yang unik secara global.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OriginGroupName <String>]`: Nama grup asal yang unik dalam titik akhir.
  - `[OriginName <String>]`: Nama asal yang unik dalam profil.
  - `[ProfileName <String>]`: Nama profil Azure Front Door Standard atau Azure Front Door Premium atau CDN yang unik dalam grup sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup Sumber Daya dalam langganan Azure.
  - `[RouteName <String>]`: Nama aturan perutean.
  - `[RuleName <String>]`: Nama aturan pengiriman yang unik dalam titik akhir.
  - `[RuleSetName <String>]`: Nama seperangkat aturan di bawah profil yang unik secara global.
  - `[SecretName <String>]`: Nama Rahasia di bawah profil.
  - `[SecurityPolicyName <String>]`: Nama kebijakan keamanan di bawah profil.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

## RELATED LINKS

