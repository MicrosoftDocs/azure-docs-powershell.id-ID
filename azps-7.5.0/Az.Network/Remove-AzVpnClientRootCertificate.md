---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 5D857FF6-A27D-4031-948D-8A69D24B4AD4
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVpnClientRootCertificate.md
ms.openlocfilehash: b01be66293876bd567dc50388aa9398ed29cbdeb
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145668262"
---
# Remove-AzVpnClientRootCertificate

## SYNOPSIS
Menghapus sertifikat akar klien VPN yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azvpnclientrootcertificate) untuk informasi terbaru.

## SYNTAX

```
Remove-AzVpnClientRootCertificate -VpnClientRootCertificateName <String> -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> -PublicCertData <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVpnClientRootCertificate** menghapus sertifikat akar yang ditentukan dari gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda: semua sertifikat lain yang digunakan pada gateway mempercayai sertifikat akar.
Jika Anda menghapus komputer sertifikat akar yang menggunakan sertifikat untuk tujuan autentikasi tidak akan lagi dapat tersambung ke gateway.
Saat Anda menggunakan **Remove-AzVpnClientRootCertificate**, Anda harus menyediakan nama sertifikat dan representasi teks data sertifikat.
Untuk informasi selengkapnya tentang representasi teks sertifikat, lihat deskripsi parameter *PublicCertData* .

## EXAMPLES

### Contoh 1: Menghapus sertifikat akar klien dari gateway jaringan virtual
```powershell
$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
Remove-AzVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway" -VpnClientRootCertificateName "ContosoRootCertificate"
```

Contoh ini menghapus sertifikat akar klien bernama ContosoRootCertificate dari gateway jaringan virtual ContosoVirtualGateway.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks sertifikat yang diekspor sebelumnya; representasi teks ini disimpan dalam variabel bernama $Text.
Perintah kedua kemudian menggunakan perulangan for untuk mengekstrak semua teks dalam $Text kecuali untuk baris pertama dan baris terakhir.
Teks yang diekstrak ini disimpan dalam variabel bernama $CertificateText.
Perintah ketiga menggunakan informasi yang disimpan dalam variabel $CertificateText bersama dengan cmdlet **Remove-AzVpnClientRootCertificate** untuk menghapus sertifikat dari gateway.

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

### -PublicCertData
Menentukan representasi teks sertifikat akar yang akan dihapus.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam pengodean format .cer (menggunakan Base64), lalu buka file yang dihasilkan di editor teks.
Anda akan melihat output yang mirip dengan berikut (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel singkatan yang ditunjukkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua baris antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil PublicCertData menggunakan perintah Windows PowerShell yang mirip dengan ini: $Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer" $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}

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
Menentukan nama grup sumber daya tempat gateway jaringan virtual ditetapkan.
Grup sumber daya mengategorikan item untuk membantu menyederhanakan manajemen inventarisasi dan administrasi Azure umum.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Add-AzVpnClientRootCertificate](./Add-AzVpnClientRootCertificate.md)

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[New-AzVpnClientRootCertificate](./New-AzVpnClientRootCertificate.md)


