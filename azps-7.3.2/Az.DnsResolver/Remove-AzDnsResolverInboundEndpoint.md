---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/remove-azdnsresolverinboundendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Remove-AzDnsResolverInboundEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Remove-AzDnsResolverInboundEndpoint.md
ms.openlocfilehash: 7047dbaf4600344d6747910e38d049826acc73c7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140187006"
---
# Remove-AzDnsResolverInboundEndpoint

## SYNOPSIS
Menghapus titik akhir masuk untuk resolver DNS.
PERINGATAN: Operasi ini tidak dapat dibatalkan.

## SYNTAX

### Hapus (Default)
```
Remove-AzDnsResolverInboundEndpoint -DnsResolverName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzDnsResolverInboundEndpoint -InputObject <IDnsResolverIdentity> [-IfMatch <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus titik akhir masuk untuk resolver DNS.
PERINGATAN: Operasi ini tidak dapat dibatalkan.

## EXAMPLES

### Contoh 1: Hapus Titik Akhir Masuk berdasarkan nama
```powershell
Remove-AzDnsResolverInboundEndpoint  -DnsResolverName pstestdnsresolvername -Name sampleInboundEndpoint -ResourceGroupName powershell-test-rg
```

Perintah ini menghapus Titik Akhir Masuk menurut nama

### Contoh 2: Hapus Titik akhir masuk melalui identitas
```powershell
$inputobject = Get-AzDnsResolverInboundEndpoint -DnsResolverName pstestdnsresolvername -Name sampleInboundEndpoint -ResourceGroupName powershell-test-rg

Remove-AzDnsResolverInboundEndpoint -InputObject $inputObject
```

Perintah ini menghapus Titik Akhir masuk melalui identitas

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -DnsResolverName
Nama resolver DNS.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IfMatch
ETag sumber daya.
Menghilangkan nilai ini agar selalu menimpa sumber daya saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah secara tidak sengaja menimpa perubahan konklar apa pun.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.IDnsResolverIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama titik akhir masuk untuk resolver DNS.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: InboundEndpointName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Delete
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
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.IDnsResolverIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDnsResolverIdentity>: Parameter Identitas
  - `[DnsForwardingRulesetName <String>]`: Nama daftar aturan penerusan DNS.
  - `[DnsResolverName <String>]`: Nama resolver DNS.
  - `[ForwardingRuleName <String>]`: Nama aturan penerusan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InboundEndpointName <String>]`: Nama titik akhir masuk untuk resolver DNS.
  - `[OutboundEndpointName <String>]`: Nama titik akhir keluar untuk resolver DNS.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkLinkName <String>]`: Nama link jaringan virtual.
  - `[VirtualNetworkName <String>]`: Nama jaringan virtual.

## RELATED LINKS

