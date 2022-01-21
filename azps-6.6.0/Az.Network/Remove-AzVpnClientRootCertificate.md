---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 5D857FF6-A27D-4031-948D-8A69D24B4AD4
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVpnClientRootCertificate.md
ms.openlocfilehash: f7b0414c47ae5fb57ba5ac970bddc958dfffe04b
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136389995"
---
# Remove-AzVpnClientRootCertificate

## SYNOPSIS
Menghapus sertifikat akar klien VPN yang sudah ada.

## SYNTAX

```
Remove-AzVpnClientRootCertificate -VpnClientRootCertificateName <String> -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> -PublicCertData <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVpnClientRootCertificate** menghapus sertifikat akar yang ditentukan dari gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan di gateway mempercayai sertifikat akar.
Jika Anda menghapus komputer sertifikat akar yang menggunakan sertifikat untuk tujuan autentikasi tidak akan bisa lagi menyambungkan ke gateway.
Ketika menggunakan **Remove-AzVpnClientRootCertificate,** Anda harus menyediakan nama sertifikat dan teks representasi data sertifikat.
Untuk informasi selengkapnya tentang teks representasi sertifikat, lihat deskripsi parameter *PublicCertData.*

## EXAMPLES

### Contoh 1: Menghapus sertifikat akar klien dari gateway jaringan virtual
```powershell
PS C:\>$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> Remove-AzVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway" -VpnClientRootCertificateName "ContosoRootCertificate"
```

Contoh ini menghapus sertifikat akar klien yang bernama ContosoRootCertificate dari gateway jaringan virtual ContosoVirtualGateway.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks sertifikat yang diekspor sebelumnya; representasi teks ini disimpan dalam variabel yang bernama $Text.
Lalu perintah kedua menggunakan pengulangan untuk mengekstrak semua teks dalam $Text kecuali untuk baris pertama dan baris terakhir.
Teks yang diekstrak ini disimpan dalam variabel yang bernama $CertificateText.
Perintah ketiga menggunakan informasi yang disimpan di variabel $CertificateText bersama dengan cmdlet **Remove-AzVpnClientRootCertificate** untuk menghapus sertifikat dari gateway.

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

### -PublicCertData
Menentukan representasi teks dari sertifikat akar yang akan dihapus.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Anda akan melihat output seperti berikut (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel yang disingkat di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua garis antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData menggunakan perintah Windows PowerShell seperti ini: $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer" $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text \[ $i \] }

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang ditetapkan untuk gateway jaringan virtual.
Grup sumber daya mengkategorikan item untuk membantu menyederhanakan manajemen inventaris dan administrasi umum Azure.

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

### -VirtualNetworkGatewayName
Menentukan nama gateway jaringan virtual tempat sertifikat dihapus.

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

### -VpnClientRootCertificateName
Menentukan nama sertifikat akar klien yang dihapus cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Add-AzVpnClientRootCertificate](./Add-AzVpnClientRootCertificate.md)

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[New-AzVpnClientRootCertificate](./New-AzVpnClientRootCertificate.md)


