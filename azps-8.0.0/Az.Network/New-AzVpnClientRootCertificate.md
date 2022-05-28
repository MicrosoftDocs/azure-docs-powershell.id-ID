---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C54AC64C-DA21-443E-8CFE-6CCAC6152C2B
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVpnClientRootCertificate.md
ms.openlocfilehash: 9df8679005709d430e64e2e56431f624e6de3dc8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145530151"
---
# New-AzVpnClientRootCertificate

## SYNOPSIS
Membuat sertifikat akar klien VPN baru.

## SYNTAX

```
New-AzVpnClientRootCertificate -Name <String> -PublicCertData <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVpnClientRootCertificate** membuat sertifikat akar VPN baru untuk digunakan pada gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan pada gateway mempercayai sertifikat akar.
Cmdlet ini membuat sertifikat yang berdiri sendiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat oleh **New-AzVpnClientRootCertificate** digunakan bersama dengan cmdlet New-AzVirtualNetworkGateway saat membuat gateway baru.
Misalnya, Anda membuat sertifikat baru dan menyimpannya dalam variabel bernama $Certificate.
Anda kemudian dapat menggunakan objek sertifikat tersebut saat membuat gateway virtual baru.
Contohnya, `New-AzVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRootCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzVirtualNetworkGateway.

## EXAMPLES

### Contoh 1: Membuat sertifikat akar klien
```powershell
$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
$Certificate = New-AzVpnClientRootCertificate -PublicCertData $CertificateText -Name "ContosoClientRootCertificate"
```

Contoh ini membuat sertifikat akar klien dan menyimpan objek sertifikat dalam variabel bernama $Certificate.
Variabel ini kemudian dapat digunakan oleh cmdlet **New-AzVirtualNetworkGateway** untuk menambahkan sertifikat akar ke gateway jaringan virtual baru.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks yang diekspor sebelumnya dari sertifikat akar; data teks tersebut disimpan dalam variabel bernama $Text.
Perintah kedua kemudian menggunakan perulangan for untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir, menyimpan teks yang diekstrak dalam variabel bernama $CertificateText.
Perintah ketiga menggunakan cmdlet **New-AzVpnClientRootCertificate** untuk membuat sertifikat, menyimpan objek yang dibuat dalam variabel bernama $Certificate.

## PARAMETERS

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

### -Name
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
Menentukan representasi teks sertifikat akar yang akan ditambahkan.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Anda akan melihat output yang mirip dengan ini (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel singkatan yang ditampilkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua baris antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData dengan menggunakan perintah Windows PowerShell yang mirip dengan ini: $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer" $CertificateText = untuk ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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

## NOTES

## RELATED LINKS

[Add-AzVpnClientRootCertificate](./Add-AzVpnClientRootCertificate.md)

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[Remove-AzVpnClientRootCertificate](./Remove-AzVpnClientRootCertificate.md)


