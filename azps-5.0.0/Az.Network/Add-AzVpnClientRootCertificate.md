---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: B9153CA9-06D1-4EF3-9863-D649C2EBAEAA
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/add-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Add-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Add-AzVpnClientRootCertificate.md
ms.openlocfilehash: efb8640f765468432a2927f865ce9f67c7b9164f
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410561"
---
# Add-AzVpnClientRootCertificate

## SYNOPSIS
Menambahkan sertifikat akar klien VPN.

## SINTAKS

```
Add-AzVpnClientRootCertificate -VpnClientRootCertificateName <String> -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> -PublicCertData <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Add-AzVpnClientRootCertificate** menambahkan sertifikat akar ke gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda.
Secara desain, semua sertifikat yang digunakan pada gateway mempercayai sertifikat akar.
Cmdlet ini menetapkan sertifikat yang sudah ada sebagai sertifikat akar gateway.
Jika tidak memiliki sertifikat X.509 yang tersedia, Anda dapat menghasilkannya melalui infrastruktur kunci publik atau menggunakan generator sertifikat seperti makecert.exe.
Untuk menambahkan sertifikat akar, Anda harus menentukan nama sertifikat dan menyediakan representasi sertifikat hanya sebagai teks (lihat parameter *PublicCertData* untuk informasi selengkapnya).
Azure memungkinkan Anda untuk menetapkan lebih dari satu sertifikat akar ke gateway.
Beberapa sertifikat akar sering digunakan oleh organisasi yang menyertakan pengguna dari lebih dari satu perusahaan.

## CONTOH

### Contoh 1: Menambahkan sertifikat akar klien ke gateway virtual
```
PS C:\>$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
PS C:\> $CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
PS C:\> Add-AzVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway" -VpnClientRootCertificateName "ContosoClientRootCertificate"
```

Contoh ini menambahkan sertifikat akar klien ke gateway virtual bernama ContosoVirtualGateway.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks yang diekspor sebelumnya dari sertifikat akar dan menyimpan data teks tersebut ke variabel bernama $Text.
Lalu perintah kedua menggunakan pengulangan untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir.
Teks yang diekstrak disimpan dalam variabel yang bernama $CertificateText.
Perintah ketiga lalu menggunakan teks yang disimpan di $CertificateText dengan cmdlet **Add-AzVpnClientRootCertificate** untuk menambahkan sertifikat akar ke gateway.

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
Menentukan representasi teks dari sertifikat akar yang akan ditambahkan.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Ketika melakukan hal tersebut, Anda akan melihat output seperti berikut (perhatikan bahwa output aktual akan berisi lebih banyak baris teks dari sampel yang disingkat yang diperlihatkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua garis antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil data ini menggunakan Windows PowerShell seperti ini:`$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"`
`$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text\[$i\]}`

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
Menentukan nama grup sumber daya tempat sertifikat akar ditetapkan.
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
Menentukan nama gateway jaringan virtual tempat sertifikat ditambahkan.

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
Menentukan nama sertifikat akar klien yang penambahan cmdlet ini.

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

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## CATATAN

## LINK TERKAIT

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[New-AzVpnClientRootCertificate](./New-AzVpnClientRootCertificate.md)

[Remove-AzVpnClientRootCertificate](./Remove-AzVpnClientRootCertificate.md)


