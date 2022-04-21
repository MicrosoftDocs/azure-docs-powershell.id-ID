---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 8D84F81A-F6B5-413D-B349-50947FCD5CFC
online version: https://docs.microsoft.com/powershell/module/az.network/new-azpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPublicIpAddress.md
ms.openlocfilehash: 02e5084ff53b92c94182df42863139b42a3498c6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142678060"
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

### Contoh 1: Membuat alamat IP publik baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini karena -AllocationMethod ditentukan sebagai 'Statis'. Jika ditentukan sebagai 'Dinamis', alamat IP publik akan dialokasikan hanya ketika Anda memulai (atau membuat) sumber daya terkait (seperti VM atau penyeimbang muat).

### Contoh 2: Membuat alamat IP publik dengan FQDN terbalik
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -ReverseFqdn $customFqdn
```

Perintah ini membuat sumber daya alamat IP publik baru. Dengan parameter -ReverseFqdn, Azure membuat catatan DNS PTR (reverse-lookup) untuk alamat IP publik yang dialokasikan ke sumber daya ini, mengarah ke $customFqdn yang ditentukan dalam perintah. Sebagai prasyarat, $customFqdn (misalnya webapp.contoso.com) harus memiliki catatan DNS CNAME (pencarian maju) yang mengarah ke $dnsPrefix.$location.cloudapp.azure.com.

### Contoh 3: Membuat alamat IP publik baru dengan IpTag
```powershell
$ipTag = New-AzPublicIpTag -IpTagType "FirstPartyUsage" -Tag "/Sql"
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -IpTag $ipTag
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini karena -AllocationMethod ditentukan sebagai 'Statis'. Jika ditentukan sebagai 'Dinamis', alamat IP publik akan dialokasikan hanya ketika Anda memulai (atau membuat) sumber daya terkait (seperti VM atau penyeimbang muat). Iptag digunakan untuk spesifik Tag yang terkait dengan sumber daya. Iptag dapat ditentukan menggunakan New-AzPublicIpTag dan dikirim sebagai input melalui -IpTags.

### Contoh 4: Membuat alamat IP publik baru dari Prefiks
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $dnsPrefix -Location $location -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini membuat sumber daya alamat IP publik baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik segera dialokasikan ke sumber daya ini dari publicIpPrefix yang ditentukan.
Opsi ini hanya didukung untuk 'Standar' Sku dan 'Static' AllocationMethod.

### Contoh 5: Membuat alamat IP publik tertentu dari Prefiks BYOIP
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -Location $location -IpAddress 0.0.0.0 -PublicIpPrefix $publicIpPrefix -Sku Standard
```

Perintah ini membuat sumber daya alamat IP publik baru dengan IP tertentu. NRP akan memeriksa apakah IP yang diberikan berada di dalam PublicIpPrefix dan apakah PublicIpPrefix yang diberikan adalah BYOIP PublicIpPrefix.
alamat IP publik yang diberikan segera dialokasikan ke sumber daya ini dari publicIpPrefix yang ditentukan. Opsi ini hanya didukung untuk Sku 'Standar' dan Alokasi 'Statis'Method dan Byoip PublicIpPrefix.

### Contoh 6: Membuat alamat IP publik global baru
```powershell
$publicIp = New-AzPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName -AllocationMethod Static -DomainNameLabel $domainNameLabel -Location $location -Sku Standard -Tier Global
```

Perintah ini membuat sumber daya alamat IP publik global yang baru. Catatan DNS dibuat untuk $dnsPrefix.$location.cloudapp.azure.com yang mengarah ke alamat IP publik sumber daya ini. Alamat IP publik global segera dialokasikan ke sumber daya ini.
Opsi ini hanya didukung untuk 'Standar' Sku dan 'Static' AllocationMethod.

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
Menjalankan cmdlet di latar belakang

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

### -Paksa
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
Menentukan waktu habis diam, dalam menit.

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
Menentukan kawasan tempat untuk membuat alamat IP publik.

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
Menentukan reverse nama domain yang sepenuhnya memenuhi syarat (FQDN).

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
Nama IP Sku publik.

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

### -Tingkat
Ip publik Sku Tier.

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
Daftar zona ketersediaan yang mencantumkan IP yang dialokasikan untuk sumber daya yang diperlukan.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

[Get-AzPublicIpAddress](./Get-AzPublicIpAddress.md)

[Remove-AzPublicIpAddress](./Remove-AzPublicIpAddress.md)

[Set-AzPublicIpAddress](./Set-AzPublicIpAddress.md)
