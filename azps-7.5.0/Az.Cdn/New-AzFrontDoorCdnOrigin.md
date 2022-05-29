---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnorigin
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOrigin.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOrigin.md
ms.openlocfilehash: a3c27867a4ebb4f7a15545a524d6c3fbb7d6fee8
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145786690"
---
# New-AzFrontDoorCdnOrigin

## SYNOPSIS
Membuat asal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cdn/new-azfrontdoorcdnorigin) untuk informasi terbaru.

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
Nama domain, alamat IPv4, dan alamat IPv6 didukung. Ini harus unik di semua asal dalam titik akhir.

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
Nama grup asal Azure Front Door.

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
Nilai header host dikirim ke asal dengan setiap permintaan.
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
Nama asal Azure Front Door.

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
Prioritas asal dalam grup asal yang diberikan untuk penyeimbangan beban.
Prioritas yang lebih tinggi tidak akan digunakan untuk penyeimbangan beban jika asal prioritas yang lebih rendah sehat.

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
Id sumber daya Azure dari sumber daya tautan privat bersama.

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
Lokasi sumber daya tautan privat bersama.

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
Pesan permintaan untuk meminta persetujuan sumber daya tautan privat bersama.

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
Berat asal dalam grup asal yang diberikan untuk penyeimbangan beban.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdOrigin

## NOTES

## RELATED LINKS
