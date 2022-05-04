---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 8D84F81A-F6B5-413D-B349-50947FCD5CFC
online version: https://docs.microsoft.com/powershell/module/az.network/new-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
ms.openlocfilehash: 6214101701e575e41462e9e919c809708a3bb584
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144729338"
---
# New-AzPublicIpAddress

## SYNOPSIS
Membuat alamat IP publik.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azpublicipaddress) untuk informasi terbaru.

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

### Contoh 1: Membuat alamat IP publik baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang menunjuk ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini karena -AllocationMethod ditentukan sebagai 'Statis'. Jika ditentukan sebagai 'Dinamis', alamat IP publik hanya dialokasikan saat Anda memulai (atau membuat) sumber daya terkait (seperti VM atau load balancer).

### Contoh 2: Membuat alamat IP publik dengan FQDN terbalik
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -ReverseFqdn $customFqdn
```

Perintah ini membuat sumber daya alamat IP publik baru. Dengan parameter -ReverseFqdn, Azure membuat rekaman DNS PTR (pencarian terbalik) untuk alamat IP publik yang dialokasikan ke sumber daya ini, menunjuk ke $customFqdn yang ditentukan dalam perintah. Sebagai prasyarat, $customFqdn (misalnya webapp.contoso.com) harus memiliki catatan DNS CNAME (pencarian maju) yang menunjuk ke $dnsPrefix.$location.cloudapp.azure.com.

### Contoh 3: Membuat alamat IP publik baru dengan IpTag
```powershell
$ipTag = New-AzPublicIpTag -IpTagType "FirstPartyUsage" -Tag "/Sql"
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -IpTag $ipTag
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang menunjuk ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini karena -AllocationMethod ditentukan sebagai 'Statis'. Jika ditentukan sebagai 'Dinamis', alamat IP publik hanya dialokasikan saat Anda memulai (atau membuat) sumber daya terkait (seperti VM atau load balancer). Iptag digunakan untuk menentukan Tag yang terkait dengan sumber daya. Iptag dapat ditentukan menggunakan New-AzPublicIpTag dan diteruskan sebagai input melalui -IpTags.

### Contoh 4: Membuat alamat IP publik baru dari Awalan
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang menunjuk ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan untuk sumber daya ini dari publicIpPrefix yang ditentukan.
Opsi ini hanya didukung untuk Sku 'Standar' dan 'Statis' AllocationMethod.

### Contoh 5: Membuat alamat IP publik tertentu dari Awalan BYOIP
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -Location $location -IpAddress 0.0.0.0 -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini membuat sumber daya alamat IP publik baru dengan IP tertentu. NRP akan memeriksa apakah IP yang diberikan berada di dalam PublicIpPrefix dan apakah PublicIpPrefix yang diberikan adalah BYOIP PublicIpPrefix.
alamat IP publik yang diberikan segera dialokasikan untuk sumber daya ini dari publicIpPrefix yang ditentukan. Opsi ini hanya didukung untuk Sku 'Standar' dan 'Statis' AllocationMethod dan BYOIP PublicIpPrefix.

### Contoh 6: Membuat alamat IP publik global baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $domainNameLabel -Location $location -Sku Standard -Tier Global
```

Perintah ini membuat sumber daya alamat IP publik global baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang menunjuk ke alamat IP publik sumber daya ini. Alamat IP publik global segera dialokasikan untuk sumber daya ini.
Opsi ini hanya didukung untuk Sku 'Standar' dan 'Statis' AllocationMethod.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Menentukan batas waktu diam, dalam menit.

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
Menentukan wilayah tempat membuat alamat IP publik.

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

### -Name
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
Menentukan PSPublicIpPrefix untuk mengalokasikan alamat IP publik.

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
Menentukan alamat IP saat membuat publicIpAddress BYOIP.

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
Menentukan nama domain terbalik yang sepenuhnya memenuhi syarat (FQDN).

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
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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

### -Tingkat
Tingkat Sku IP publik.

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

### -Zona
Daftar zona ketersediaan yang menunjukkan IP yang dialokasikan untuk kebutuhan sumber daya.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSPublicIpTag[]

### Microsoft.Azure.Commands.Network.Models.PSPublicIpPrefix

### System.Int32

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPublicIpAddress

## NOTES

## RELATED LINKS

[Dapatkan-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)

[Set-AzPublicIpAddress](./Set-AzPublicIpAddress.md)
