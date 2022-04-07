---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 8D84F81A-F6B5-413D-B349-50947FCD5CFC
online version: https://docs.microsoft.com/powershell/module/az.network/new-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
ms.openlocfilehash: 02e5084ff53b92c94182df42863139b42a3498c6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140385894"
---
# New-AzPublicIpAddress

## SYNOPSIS
Membuat alamat IP publik.

## SYNTAX

```
New-AzPublicIpAddress [-Name <String>] -ResourceGroupName <String> [-Location <String>] [-EdgeZone <String>]
 [-Sku <String>] [-Tier <String>] -AllocationMethod <String> [-IpAddressVersion <String>] [-IpAddress <String>]
 [-DomainNameLabel <String>] [-IpTag <PSPublicIpTag[]>] [-PublicIpPrefix <PSPublicIpPrefix>]
 [-ReverseFqdn <String>] [-IdleTimeoutInMinutes <Int32>] [-Zone <String[]>] [-Tag <Hashtable>] [-Force]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzPublicIpAddress** membuat alamat IP publik.

## EXAMPLES

### Contoh 1: Buat alamat IP publik baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location
```

Perintah ini akan membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini sebagai -AllocationMethod ditentukan sebagai 'Statis'. Jika ditetapkan sebagai 'Dynamic', alamat IP publik akan dialokasikan hanya ketika Anda memulai (atau membuat) sumber daya yang terkait (seperti VM atau load balancer).

### Contoh 2: Membuat alamat IP publik dengan FQDN terbalik
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -ReverseFqdn $customFqdn
```

Perintah ini akan membuat sumber daya alamat IP publik baru. Dengan parameter -ReverseFqdn, Azure membuat catatan DNS PTR (pencarian terbalik) untuk alamat IP publik yang dialokasikan ke sumber daya ini, mengarahkan ke $customFqdn ditentukan dalam perintah. Sebagai prasyarat, $customFqdn (misalnya webapp.contoso.com) harus memiliki catatan DNS CNAME (pencarian terusan) yang menunjuk ke $dnsPrefix.$location.cloudapp.azure.com.

### Contoh 3: Buat alamat IP publik baru dengan IpTag
```powershell
$ipTag = New-AzPublicIpTag -IpTagType "FirstPartyUsage" -Tag "/Sql"
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -IpTag $ipTag
```

Perintah ini akan membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini sebagai -AllocationMethod ditentukan sebagai 'Statis'. Jika ditetapkan sebagai 'Dynamic', alamat IP publik akan dialokasikan hanya ketika Anda memulai (atau membuat) sumber daya yang terkait (seperti VM atau load balancer). Iptag digunakan untuk spesifik Tag yang terkait dengan sumber daya. Iptag dapat ditentukan menggunakan New-AzPublicIpTag dan diteruskan sebagai input melalui -IpTags.

### Contoh 4: Membuat alamat IP publik baru dari Prefiks
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini akan membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini dari publicIpPrefix yang ditentukan.
Opsi ini hanya didukung untuk Metode Alokasi 'Standar' Sku dan 'Statis'.

### Contoh 5: Membuat alamat IP publik tertentu dari Prefiks BYOIP
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -Location $location -IpAddress 0.0.0.0 -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini akan membuat sumber daya alamat IP publik baru dengan IP tertentu. NRP akan memeriksa apakah IP yang diberikan berada di dalam PublicIpPrefix dan jika PublicIpPrefix yang diberikan adalah BYOIP PublicIpPrefix.
alamat IP publik yang diberikan segera dialokasikan ke sumber daya ini dari publicIpPrefix yang ditentukan. Opsi ini hanya didukung untuk Metode Alokasi 'Standar' Sku dan 'Statis' dan BYOIP PublicIpPrefix.

### Contoh 6: Membuat alamat IP publik global baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $domainNameLabel -Location $location -Sku Standard -Tier Global
```

Perintah ini akan membuat sumber daya alamat IP publik global baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik global segera dialokasikan ke sumber daya ini.
Opsi ini hanya didukung untuk Metode Alokasi 'Standar' Sku dan 'Statis'.

## PARAMETERS

### -AllocationMethod
Menentukan metode untuk mengalokasikan alamat IP publik.
Nilai yang dapat diterima untuk parameter ini adalah: Statis atau Dinamis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Dynamic, Static

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNameLabel
Menentukan nama DNS relatif untuk alamat IP publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EdgeZone
Nama lokasi yang diperluas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -IdleTimeoutInMinutes
Menentukan waktu diam yang habis, dalam menit.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddressVersion
Menentukan versi alamat IP.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpTag
Daftar IpTag.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpTag[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan kawasan untuk membuat alamat IP publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama alamat IP publik yang dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIpPrefix
Menentukan PSPublicIpPrefix yang mengalokasikan alamat IP publik.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddress
Menentukan alamat IP saat membuat BYOIP publicIpAddress.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk membuat alamat IP publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseFqdn
Menentukan kebalikan nama domain yang sepenuhnya memenuhi syarat (FQDN).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Nama Sku IP publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tier
Ip Sku Tier publik.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Regional, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Daftar zona ketersediaan mencantumkan IP yang dialokasikan untuk sumber daya yang diperlukan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSPublicIpTag[]

### Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix

### System.Int32

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## CATATAN

## RELATED LINKS

[Get-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)

[Set-AzPublicIpAddress](./Set-AzPublicIpAddress.md)
