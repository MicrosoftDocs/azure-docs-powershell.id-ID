---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C54AC64C-DA21-443E-8CFE-6CCAC6152C2B
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRootCertificate.md
ms.openlocfilehash: efa6d160dccb1a3cd0b1854bd9451cffdcec04d7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140205686"
---
# New-AzVpnClientRootCertificate

## SYNOPSIS
Membuat sertifikat akar klien VPN yang baru.

## SYNTAX

```
New-AzVpnClientRootCertificate -Name <String> -PublicCertData <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVpnClientRootCertificate** membuat sertifikat akar VPN baru untuk digunakan di gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Cmdlet ini membuat sertifikat mandiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat **oleh New-AzVpnClientRootCertificate** digunakan bersama dengan cmdlet New-AzVirtualNetworkGateway saat membuat gateway baru.
Misalnya, anggaplah Anda membuat sertifikat baru dan menyimpannya di variabel yang bernama $Certificate.
Anda lalu bisa menggunakan objek sertifikat tersebut saat membuat gateway virtual baru.
Sebagai contoh, `New-AzVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRootCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzVirtualNetworkGateway lanjut.

## EXAMPLES

### Contoh 1: Membuat sertifikat akar klien
```
PS C:\> $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> $Certificate = New-AzVpnClientRootCertificate -PublicCertData $CertificateText -Name "ContosoClientRootCertificate"
```

Contoh ini membuat sertifikat akar klien dan menyimpan objek sertifikat dalam variabel yang bernama $Certificate.
Variabel ini lalu bisa digunakan oleh cmdlet **New-AzVirtualNetworkGateway** untuk menambahkan sertifikat akar ke gateway jaringan virtual yang baru.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks akar yang diekspor sebelumnya; bahwa data teks disimpan dalam variabel yang bernama $Text.
Lalu perintah kedua menggunakan pengulangan untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir, menyimpan teks yang diekstrak dalam variabel yang bernama $CertificateText.
Perintah ketiga menggunakan cmdlet **New-AzVpnClientRootCertificate** untuk membuat sertifikat, menyimpan objek yang dibuat di variabel yang bernama $Certificate.

## PARAMETERS

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
Menentukan nama untuk sertifikat akar klien baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicCertData
Menentukan representasi teks dari sertifikat akar yang akan ditambahkan.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Anda akan melihat output seperti ini (perhatikan bahwa output aktual akan berisi lebih banyak baris teks dari sampel yang disingkat, diperlihatkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua garis antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData menggunakan perintah Windows PowerShell seperti ini: $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer" $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## RELATED LINKS

[Add-AzVpnClientRootCertificate](./Add-AzVpnClientRootCertificate.md)

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[Remove-AzVpnClientRootCertificate](./Remove-AzVpnClientRootCertificate.md)


