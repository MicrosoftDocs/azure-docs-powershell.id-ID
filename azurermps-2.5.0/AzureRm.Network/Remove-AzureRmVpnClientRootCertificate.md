---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 5D857FF6-A27D-4031-948D-8A69D24B4AD4
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermvpnclientrootcertificate
schema: 2.0.0
ms.openlocfilehash: 66c026e3e1ec05d94b8dc19b2ceedd92d4fc0200
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142392498"
---
# Remove-AzureRmVpnClientRootCertificate

## SYNOPSIS
Menghapus sertifikat akar klien VPN yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmVpnClientRootCertificate -VpnClientRootCertificateName <String>
 -VirtualNetworkGatewayName <String> -ResourceGroupName <String> -PublicCertData <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmVpnClientRootCertificate** menghapus sertifikat akar tertentu dari gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Jika Anda menghapus komputer sertifikat akar yang menggunakan sertifikat untuk tujuan autentikasi tidak akan bisa lagi tersambung ke gateway.

Ketika menggunakan **Remove-AzureRmVpnClientRootCertificate**, Anda harus memasukkan nama sertifikat dan representasi teks data sertifikat.
Untuk informasi selengkapnya tentang representasi teks sertifikat, lihat deskripsi parameter *PublicCertData* .

## EXAMPLES

### Contoh 1: Menghapus sertifikat akar klien dari gateway jaringan virtual
```
PS C:\>$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> Remove-AzureRmVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway"-VpnClientRootCertificateName "ContosoRootCertificate"
```

Contoh ini menghapus sertifikat akar klien bernama ContosoRootCertificate dari gateway jaringan virtual ContosoVirtualGateway.

Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks sertifikat yang diekspor sebelumnya; representasi teks ini disimpan dalam variabel bernama $Text.

Perintah kedua kemudian menggunakan pengulangan untuk mengekstrak semua teks dalam $Text kecuali baris pertama dan baris terakhir.
Teks yang diekstrak ini disimpan dalam variabel bernama $CertificateText.

Perintah ketiga menggunakan informasi yang disimpan dalam variabel $CertificateText bersama dengan cmdlet **Remove-AzureRmVpnClientRootCertificate** untuk menghapus sertifikat dari gateway.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan representasi teks sertifikat akar yang akan dihapus.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan Base64), lalu buka file yang dihasilkan dalam editor teks.
Anda akan melihat output yang mirip dengan yang berikut ini (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel singkatan yang diperlihatkan di sini):

----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE -----

PublicCertData terdiri dari semua baris antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData menggunakan perintah Windows PowerShell seperti ini:

$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertficate.cer" $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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
Menentukan nama grup sumber daya tempat gateway jaringan maya ditetapkan.

Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi Umum Azure.

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
Menentukan nama gateway jaringan virtual tempat sertifikat dihapus.

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
Menentukan nama sertifikat akar klien yang dihapus cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureRmVpnClientRootCertificate](./Add-AzureRmVpnClientRootCertificate.md)

[Get-AzureRmVpnClientRootCertificate](./Get-AzureRmVpnClientRootCertificate.md)

[New-AzureRmVpnClientRootCertificate](./New-AzureRmVpnClientRootCertificate.md)


