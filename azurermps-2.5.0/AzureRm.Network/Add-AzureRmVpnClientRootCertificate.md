---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: B9153CA9-06D1-4EF3-9863-D649C2EBAEAA
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/add-azurermvpnclientrootcertificate
schema: 2.0.0
ms.openlocfilehash: 2f5d73cd06d975d6458776dee4242b392b5c160b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420189"
---
# Add-AzureRmVpnClientRootCertificate

## SYNOPSIS
Menambahkan sertifikat akar klien VPN.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmVpnClientRootCertificate -VpnClientRootCertificateName <String> -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> -PublicCertData <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmVpnClientRootCertificate** menambahkan sertifikat akar ke gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda.
Secara desain, semua sertifikat yang digunakan pada gateway mempercayai sertifikat akar.

Cmdlet ini menetapkan sertifikat yang sudah ada sebagai sertifikat akar gateway.
Jika tidak memiliki sertifikat X.509 yang tersedia, Anda dapat menghasilkannya melalui infrastruktur kunci publik atau menggunakan generator sertifikat seperti makecert.exe.

Untuk menambahkan sertifikat akar, Anda harus menentukan nama sertifikat dan menyediakan representasi sertifikat hanya sebagai teks (lihat parameter *PublicCertData* untuk informasi selengkapnya).
Azure memungkinkan Anda untuk menetapkan lebih dari satu sertifikat akar ke gateway.
Beberapa sertifikat akar sering digunakan oleh organisasi yang menyertakan pengguna dari lebih dari satu perusahaan.

## EXAMPLES

### Contoh 1: Menambahkan sertifikat akar klien ke gateway virtual
```
PS C:\>$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> Add-AzureRmVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway" -VpnClientRootCertificateName "ContosoClientRootCertificate"
```

Contoh ini menambahkan sertifikat akar klien ke gateway virtual bernama ContosoVirtualGateway.

Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks yang diekspor sebelumnya dari sertifikat akar dan menyimpan data teks tersebut ke variabel bernama $Text.

Lalu perintah kedua menggunakan pengulangan untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir.
Teks yang diekstrak disimpan dalam variabel yang bernama $CertificateText.

Perintah ketiga lalu menggunakan teks yang disimpan di $CertificateText dengan cmdlet **Add-AzureRmVpnClientRootCertificate** untuk menambahkan sertifikat akar ke gateway.

## PARAMETERS

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

### -PublicCertData
Menentukan representasi teks dari sertifikat akar yang akan ditambahkan.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Ketika melakukan hal tersebut, Anda akan melihat output yang mirip dengan hal berikut (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel yang disingkat diperlihatkan di sini):

----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE -----

PublicCertData terdiri dari semua garis antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil data ini menggunakan Windows PowerShell seperti ini:`$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"`
`$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}`

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

### -ResourceGroupName
Menentukan nama grup sumber daya tempat sertifikat akar ditetapkan.

Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi umum Azure.

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

### -VirtualNetworkGatewayName
Menentukan nama gateway jaringan virtual tempat sertifikat ditambahkan.

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

### -VpnClientRootCertificateName
Menentukan nama sertifikat akar klien yang penambahan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## RELATED LINKS

[Get-AzureRmVpnClientRootCertificate](./Get-AzureRmVpnClientRootCertificate.md)

[New-AzureRmVpnClientRootCertificate](./New-AzureRmVpnClientRootCertificate.md)

[Remove-AzureRmVpnClientRootCertificate](./Remove-AzureRmVpnClientRootCertificate.md)


