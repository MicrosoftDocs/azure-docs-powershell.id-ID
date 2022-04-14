---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: C54AC64C-DA21-443E-8CFE-6CCAC6152C2B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmVpnClientRootCertificate.md
ms.openlocfilehash: 18d634650248ea03c43b8ea24ec15aa3a2b79528
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141926268"
---
# New-AzureRmVpnClientRootCertificate

## SYNOPSIS
Membuat sertifikat akar klien VPN baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVpnClientRootCertificate -Name <String> -PublicCertData <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVpnClientRootCertificate** membuat sertifikat akar VPN baru untuk digunakan di gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Cmdlet ini membuat sertifikat mandiri yang tidak ditetapkan ke gateway virtual.
Sebagai gantinya, sertifikat yang dibuat oleh **New-AzureRmVpnClientRootCertificate** digunakan bersama dengan cmdlet New-AzureRmVirtualNetworkGateway saat membuat gateway baru.
Misalnya, Anda membuat sertifikat baru dan menyimpannya dalam variabel bernama $Certificate.
Anda kemudian bisa menggunakan objek sertifikat itu saat membuat gateway virtual baru.
Misalnya, `New-AzureRmVirtualNetworkGateway -Name "ContosoVirtualGateway" -ResourceGroupName "ContosoResourceGroup" -Location "West US" -GatewayType "VPN" -IpConfigurations $Ipconfig  -VPNType "RouteBased" -VpnClientRootCertificates $Certificate`
Untuk informasi selengkapnya, lihat dokumentasi untuk cmdlet New-AzureRmVirtualNetworkGateway.

## EXAMPLES

### Contoh 1: Membuat sertifikat akar akpit
```
PS C:\> $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> $Certificate = New-AzureRmVpnClientRootCertificate -PublicCertData $CertificateText -Name "ContosoClientRootCertificate"
```

Contoh ini membuat sertifikat akar klien dan menyimpan objek sertifikat dalam variabel bernama $Certificate.
Variabel ini kemudian dapat digunakan oleh cmdlet **New-AzureRmVirtualNetworkGateway** untuk menambahkan sertifikat akar ke gateway jaringan virtual baru.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks yang sebelumnya diekspor dari sertifikat akar; data teks tersebut disimpan dalam variabel bernama $Text.
Perintah kedua kemudian menggunakan pengulangan untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir, menyimpan teks yang diekstrak dalam variabel bernama $CertificateText.
Perintah ketiga menggunakan cmdlet **New-AzureRmVpnClientRootCertificate** untuk membuat sertifikat, menyimpan objek yang dibuat dalam variabel bernama $Certificate.

## PARAMETERS

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
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan dalam editor teks.
Anda akan melihat output yang mirip dengan ini (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel singkatan yang diperlihatkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua baris antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData menggunakan perintah Windows PowerShell seperti ini: $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer" $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## RELATED LINKS

[Add-AzureRmVpnClientRootCertificate](./Add-AzureRmVpnClientRootCertificate.md)

[Get-AzureRmVpnClientRootCertificate](./Get-AzureRmVpnClientRootCertificate.md)

[Hapus-AzureRmVpnClientRootCertificate](./Remove-AzureRmVpnClientRootCertificate.md)


