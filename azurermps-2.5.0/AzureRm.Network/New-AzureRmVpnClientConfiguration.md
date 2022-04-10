---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermvpnclientconfiguration
schema: 2.0.0
ms.openlocfilehash: d49078e18b6082473c398c9f4aa7ac01f41909ca
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "140852058"
---
# New-AzureRmVpnClientConfiguration

## SYNOPSIS
Perintah ini memungkinkan pengguna untuk membuat paket profil VPN berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya di gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVpnClientConfiguration [-Name <String>] -ResourceGroupName <String>
 [-ProcessorArchitecture <String>] -AuthenticationMethod <String> [-RadiusRootCertificateFile <String>]
 [-ClientRootCertificateFileList <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
ini memungkinkan pengguna untuk membuat paket profil VPN berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya di gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzureRmVpnClientConfiguration -VirtualNetworkGatewayName "ContosoVirtualNetworkGateway" -ResourceGroupName "ContosoResourceGroup" -AuthenticationMethod "EAPTLS" -RadiusRootCert "C:\Users\Test\Desktop\VpnProfileRadiusCert.cer"
```

Cmdlet ini digunakan untuk membuat file zip profil klien VPN untuk "ContosoVirtualNetworkGateway" di ResourceGroup "ContosoResourceGroup". Profil dihasilkan untuk server radius yang telah dikonfigurasi sebelumnya yang dikonfigurasi agar menggunakan metode autentikasi "EAPTLS" dengan file sertifikat VpnProfileRadiusCert.

## PARAMETERS

### -AuthenticationMethod
Metode autentikasi Bisa mengambil nilai EAPMSCHAPv2 atau EAPTLS. Saat EAPMSCHAPv2 ditentukan, cmdlet akan menghasilkan penginstal konfigurasi klien untuk autentikasi nama pengguna/kata sandi yang menggunakan EAP-MSCHAPv2 protokol autentikasi. Jika EAPTLS ditentukan, cmdlet akan menghasilkan penginstal konfigurasi klien untuk autentikasi sertifikat yang menggunakan protokol EAP-TLS. Opsi "EapTls" dapat digunakan untuk autentikasi sertifikat berbasis RADIUS dan autentikasi sertifikasi yang dijalankan oleh Gateway Jaringan Virtual dengan mengunggah akar tepercaya. Cmdlet secara otomatis mendeteksi apa yang dikonfigurasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: EAPTLS, EAPMSCHAPv2

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientRootCertificateFileList
Daftar jalur sertifikat akar klien
```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.
```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProcessorArchitecture
ProcessorArchitecture

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Amd64, X86

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusRootCertificateFile
Radius server root certificate path. Parameter ini adalah parameter wajib yang harus ditentukan saat EAP-TLS dengan autentikasi RADIUS digunakan. Ini adalah nama jalur lengkap file .cer yang berisi sertifikat akar RADIUS yang digunakan klien untuk memvalidasi server RADIUS selama autentikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnProfile

## CATATAN

## RELATED LINKS

