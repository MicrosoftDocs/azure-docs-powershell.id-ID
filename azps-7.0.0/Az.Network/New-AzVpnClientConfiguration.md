---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientConfiguration.md
ms.openlocfilehash: 21b71c4a661890db28be783483b87f91d9710f2f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136396659"
---
# New-AzVpnClientConfiguration

## SYNOPSIS
Perintah ini memungkinkan pengguna untuk membuat paket profil VPN berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya di gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

## SYNTAX

```
New-AzVpnClientConfiguration [-Name <String>] -ResourceGroupName <String> [-ProcessorArchitecture <String>]
 [-AuthenticationMethod <String>] [-RadiusRootCertificateFile <String>]
 [-ClientRootCertificateFileList <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
ini memungkinkan pengguna untuk membuat paket profil VPN berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya di gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzVpnClientConfiguration -ResourceGroupName "ContosoResourceGroup" -Name "ContosoVirtualNetworkGateway" -AuthenticationMethod "EAPTLS" -RadiusRootCertificateFile "C:\Users\Test\Desktop\VpnProfileRadiusCert.cer"
```

Cmdlet ini digunakan untuk membuat file zip profil klien VPN untuk "ContosoVirtualNetworkGateway" di ResourceGroup "ContosoResourceGroup". Profil dihasilkan untuk server radius yang telah dikonfigurasi sebelumnya yang dikonfigurasi agar menggunakan metode autentikasi "EAPTLS" dengan file sertifikat VpnProfileRadiusCert.

## PARAMETERS

### -AuthenticationMethod
Metode autentikasi Bisa mengambil nilai EAPMSCHAPv2 atau EAPTLS. Saat EAPMSCHAPv2 ditentukan, cmdlet akan menghasilkan penginstal konfigurasi klien untuk autentikasi nama pengguna/kata sandi yang menggunakan EAP-MSCHAPv2 protokol autentikasi. Jika EAPTLS ditentukan, cmdlet akan menghasilkan penginstal konfigurasi klien untuk autentikasi sertifikat yang menggunakan protokol EAP-TLS. Opsi "EapTls" dapat digunakan untuk autentikasi sertifikat berbasis RADIUS dan autentikasi sertifikasi yang dijalankan oleh Gateway Jaringan Virtual dengan mengunggah akar tepercaya. Cmdlet secara otomatis mendeteksi apa yang dikonfigurasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: EAPTLS, EAPMSCHAPv2

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientRootCertificateFileList
Daftar jalur sertifikat akar klien

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

### -Nama
Nama sumber daya.

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

### -ProcessorArchitecture
ProcessorArchitecture

```yaml
Type: System.String
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
Nama grup sumber daya.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnProfile

## CATATAN

## RELATED LINKS

[Get-AzVpnClientConfiguration](./Get-AzVpnClientConfiguration.md)
