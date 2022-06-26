---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/import-azcdnendpointcontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Import-AzCdnEndpointContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Import-AzCdnEndpointContent.md
ms.openlocfilehash: 9e612dc165a455296fa3b75352b361c829a5be82
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146619220"
---
# Import-AzCdnEndpointContent

## SYNOPSIS
Pra-muat konten ke CDN.
Tersedia untuk Profil Verizon.

## SYNTAX

### LoadExpanded (Default)
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 -ContentPath <String[]> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Muat
```
Import-AzCdnEndpointContent -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 -ContentFilePath <ILoadParameters> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### LoadViaIdentity
```
Import-AzCdnEndpointContent -InputObject <ICdnIdentity> -ContentFilePath <ILoadParameters>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### LoadViaIdentityExpanded
```
Import-AzCdnEndpointContent -InputObject <ICdnIdentity> -ContentPath <String[]> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Pra-muat konten ke CDN.
Tersedia untuk Profil Verizon.

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

### -AsJob
Jalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentFilePath
Parameter yang diperlukan untuk pemuatan konten.
Untuk membuat, lihat bagian CATATAN untuk properti CONTENTFILEPATH dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.ILoadParameters
Parameter Sets: Load, LoadViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ContentPath
Jalur ke konten yang akan dimuat.
Jalur harus berupa URL file relatif dari asal.

```yaml
Type: System.String[]
Parameter Sets: LoadExpanded, LoadViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: Load, LoadExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: LoadViaIdentity, LoadViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil CDN yang unik dalam grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Load, LoadExpanded
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
Parameter Sets: Load, LoadExpanded
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
Type: System.String
Parameter Sets: Load, LoadExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.ILoadParameters

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTENTFILEPATH `<ILoadParameters>`: Parameter yang diperlukan untuk pemuatan konten.
  - `ContentPath <String[]>`: Jalur ke konten yang akan dimuat. Jalur harus berupa URL file relatif dari asal.

INPUTOBJECT `<ICdnIdentity>`: Parameter Identitas
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

