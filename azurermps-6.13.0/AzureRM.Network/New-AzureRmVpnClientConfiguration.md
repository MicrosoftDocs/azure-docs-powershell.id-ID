---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermvpnclientconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmVpnClientConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmVpnClientConfiguration.md
ms.openlocfilehash: ddd620bb1878106801d6c69c086dc9642e76e1c7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141883284"
---
# New-AzureRmVpnClientConfiguration

## SYNOPSIS
Perintah ini memungkinkan pengguna untuk membuat paket profil Vpn berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya pada gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVpnClientConfiguration [-Name <String>] -ResourceGroupName <String>
 [-ProcessorArchitecture <String>] -AuthenticationMethod <String> [-RadiusRootCertificateFile <String>]
 [-ClientRootCertificateFileList <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
ini memungkinkan pengguna untuk membuat paket profil Vpn berdasarkan pengaturan vpn yang telah dikonfigurasi sebelumnya di gateway VPN, selain beberapa pengaturan tambahan yang mungkin perlu dikonfigurasi pengguna, misalnya beberapa sertifikat akar.

## EXAMPLES

### Contoh 1
```
PS C:\> New-AzureRmVpnClientConfiguration -ResourceGroupName "ContosoResourceGroup" -Name "ContosoVirtualNetworkGateway" -AuthenticationMethod "EAPTLS" -RadiusRootCertificateFile "C:\Users\Test\Desktop\VpnProfileRadiusCert.cer"
```

Cmdlet ini digunakan untuk membuat file zip profil klien VPN untuk "ContosoVirtualNetworkGateway" di ResourceGroup "ContosoResourceGroup". Profil dibuat untuk server radius prakonfigurasi yang dikonfigurasi untuk menggunakan metode autentikasi "EAPTLS" dengan file sertifikat VpnProfileRadiusCert.

## PARAMETERS

### -AuthenticationMethod
Metode Autentikasi Dapat mengambil nilai EAPMSCHAPv2 atau EAPTLS. Ketika EAPMSCHAPv2 ditentukan, cmdlet menghasilkan penginstal konfigurasi klien untuk autentikasi nama pengguna/kata sandi yang menggunakan protokol autentikasi EAP-MSCHAPv2. Jika EAPTLS ditentukan, cmdlet akan menghasilkan penginstal konfigurasi klien untuk autentikasi sertifikat yang menggunakan protokol EAP-TLS. Opsi "EapTls" bisa digunakan untuk autentikasi sertifikat berbasis RADIUS dan autentikasi sertifikasi yang dilakukan oleh Gateway Virtual Network dengan mengunggah akar tepercaya. Cmdlet secara otomatis mendeteksi apa yang dikonfigurasi.

```yaml
Type: System.String
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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
Jalur sertifikat akar server radius. Ini adalah parameter wajib yang harus ditentukan ketika EAP-TLS dengan autentikasi RADIUS digunakan. Ini adalah nama jalur lengkap file .cer yang berisi sertifikat akar RADIUS yang digunakan klien untuk memvalidasi server RADIUS selama autentikasi.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnProfile

## CATATAN

## RELATED LINKS
