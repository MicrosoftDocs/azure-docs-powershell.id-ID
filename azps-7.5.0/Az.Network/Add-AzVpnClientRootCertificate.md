---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: B9153CA9-06D1-4EF3-9863-D649C2EBAEAA
online version: https://docs.microsoft.com/powershell/module/az.network/add-azvpnclientrootcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVpnClientRootCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVpnClientRootCertificate.md
ms.openlocfilehash: 81d70eec26ba4b8ebc32815693b66060015b8140
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144228938"
---
# Add-AzVpnClientRootCertificate

## SYNOPSIS
Menambahkan sertifikat akar klien VPN.

## SYNTAX

```
Add-AzVpnClientRootCertificate -VpnClientRootCertificateName <String> -VirtualNetworkGatewayName <String>
 -ResourceGroupName <String> -PublicCertData <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVpnClientRootCertificate** menambahkan sertifikat akar ke gateway jaringan virtual.
Sertifikat akar adalah sertifikat X.509 yang mengidentifikasi Otoritas Sertifikasi Akar Anda.
Secara desain, semua sertifikat yang digunakan pada gateway mempercayai sertifikat akar.
Cmdlet ini menetapkan sertifikat yang sudah ada sebagai sertifikat akar gateway.
Jika Anda tidak memiliki sertifikat X.509 yang tersedia, Anda dapat membuatnya melalui infrastruktur kunci publik Anda atau menggunakan generator sertifikat seperti makecert.exe.
Untuk menambahkan sertifikat akar, Anda harus menentukan nama sertifikat dan memberikan representasi sertifikat khusus teks (lihat parameter *PublicCertData* untuk informasi selengkapnya).
Azure memungkinkan Anda menetapkan lebih dari satu sertifikat akar ke gateway.
Beberapa sertifikat akar sering disebarkan oleh organisasi yang menyertakan pengguna dari lebih dari satu perusahaan.

## EXAMPLES

### Contoh 1: Menambahkan sertifikat akar klien ke gateway virtual
```powershell
$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"
$CertificateText = for ($i=1; $i -lt $Text.Length -1 ; $i++){$Text[$i]}
Add-AzVpnClientRootCertificate -PublicCertData $CertificateText -ResourceGroupName "ContosoResourceGroup" -VirtualNetworkGatewayName "ContosoVirtualGateway" -VpnClientRootCertificateName "ContosoClientRootCertificate"
```

Contoh ini menambahkan sertifikat akar klien ke gateway virtual bernama ContosoVirtualGateway.
Perintah pertama menggunakan cmdlet **Get-Content** untuk mendapatkan representasi teks yang diekspor sebelumnya dari sertifikat akar dan menyimpan data teks variabel bernama $Text.
Perintah kedua kemudian menggunakan perulangan for untuk mengekstrak semua teks kecuali untuk baris pertama dan baris terakhir.
Teks yang diekstrak disimpan dalam variabel bernama $CertificateText.
Perintah ketiga kemudian menggunakan teks yang disimpan di $CertificateText dengan cmdlet **Add-AzVpnClientRootCertificate** untuk menambahkan sertifikat akar ke gateway.

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
Menentukan representasi teks sertifikat akar yang akan ditambahkan.
Untuk mendapatkan representasi teks, ekspor sertifikat Anda dalam format .cer (menggunakan pengodean Base64), lalu buka file yang dihasilkan di editor teks.
Ketika Anda melakukannya, Anda akan melihat output yang mirip dengan yang berikut ini (perhatikan bahwa output aktual akan berisi lebih banyak baris teks daripada sampel yang disingkat yang ditunjukkan di sini): ----- BEGIN CERTIFICATE ----- MIIC13FAAXC3671Auij9HHgUNEW8343NMJklo09982CVVFAw8w ----- END CERTIFICATE ----- PublicCertData terdiri dari semua baris antara baris pertama (----- BEGIN CERTIFICATE -----) dan baris terakhir (----- END CERTIFICATE -----) dalam file.
Anda dapat mengambil data ini dengan menggunakan perintah Windows PowerShell yang mirip dengan ini:`$Text = Get-Content -Path "C:\Azure\Certificates\ExportedCertificate.cer"`
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
Menentukan nama sertifikat akar klien yang ditambahkan cmdlet ini.

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

### Microsoft.Azure.Commands.Network.Models.PSVpnClientRootCertificate

## NOTES

## RELATED LINKS

[Get-AzVpnClientRootCertificate](./Get-AzVpnClientRootCertificate.md)

[New-AzVpnClientRootCertificate](./New-AzVpnClientRootCertificate.md)

[Remove-AzVpnClientRootCertificate](./Remove-AzVpnClientRootCertificate.md)


