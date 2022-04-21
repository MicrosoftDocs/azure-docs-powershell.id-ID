---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnorigin
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOrigin.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOrigin.md
ms.openlocfilehash: b80244be45c5018e86ab80b14f33d73ed5c0d1e6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142810738"
---
# New-AzFrontDoorCdnOrigin

## SYNOPSIS
Membuat asal.

## SYNTAX

### ByFieldsParameterSet (Default)
```
New-AzFrontDoorCdnOrigin -HostName <String> [-HttpPort <Int32>] [-HttpsPort <Int32>] -OriginGroupName <String>
 [-OriginHostHeader <String>] -OriginName <String> [-Priority <Int32>] -ProfileName <String>
 -ResourceGroupName <String> [-Weight <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SharedPrivateLinkResource
```
New-AzFrontDoorCdnOrigin -HostName <String> [-HttpPort <Int32>] [-HttpsPort <Int32>] -OriginGroupName <String>
 [-OriginHostHeader <String>] -OriginName <String> [-Priority <Int32>] -PrivateLinkId <String>
 -PrivateLinkLocation <String> -PrivateLinkRequestMessage <String> -ProfileName <String>
 -ResourceGroupName <String> [-Weight <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat asal.

## EXAMPLES

### Contoh 1
```powershell
New-AzFrontDoorCdnOrigin -HostName $hostName -OriginGroupName $originGroupName -OriginName $originName -ProfileName $profileName -ResourceGroupName $resourceGroupName
```

Membuat asal.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Alamat asal.
Nama domain, alamat IPv4, dan alamat IPv6 didukung. Ini harus unik di seluruh asal usul di titik akhir.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpPort
Nilai port HTTP.
Harus antara 1 dan 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpsPort
Nilai port HTTPS.
Harus antara 1 dan 65535.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroupName
Nama grup asal Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginHostHeader
Nilai header host yang dikirim ke asal dengan setiap permintaan.
Jika Anda membiarkan ini kosong, nama host permintaan menentukan nilai ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginName
Nama asal Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prioritas
Prioritas asal dalam grup asal yang diberikan untuk keseimbangan muat.
Prioritas yang lebih tinggi tidak akan digunakan untuk keseimbangan beban jika asal prioritas yang lebih rendah sehat.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLinkId
Id sumber daya Azure dari sumber daya tautan pribadi bersama.

```yaml
Type: String
Parameter Sets: SharedPrivateLinkResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLinkLocation
Lokasi sumber daya tautan pribadi bersama.

```yaml
Type: String
Parameter Sets: SharedPrivateLinkResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateLinkRequestMessage
Pesan permintaan untuk meminta persetujuan sumber daya tautan pribadi bersama.

```yaml
Type: String
Parameter Sets: SharedPrivateLinkResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Azure Front Door.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Berat
Berat asal dalam grup asal tertentu untuk keseimbangan beban.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdOrigin

## NOTES

## RELATED LINKS
