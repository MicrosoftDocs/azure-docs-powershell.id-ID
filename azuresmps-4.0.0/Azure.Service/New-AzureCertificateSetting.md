---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 11919623-9EDF-42A3-93FE-54E93D76D3D0
online version: ''
schema: 2.0.0
ms.openlocfilehash: ea7ba95e023308ccef6f1c19ce874dfcadcfb9d2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104247"
---
# New-AzureCertificateSetting

## SYNOPSIS
Membuat objek pengaturan sertifikat untuk sertifikat berada dalam layanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
New-AzureCertificateSetting [[-StoreName] <String>] [-Thumbprint] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureCertificateSetting** membuat objek pengaturan sertifikat untuk sertifikat yang ada di layanan Azure.

Anda dapat menggunakan objek pengaturan sertifikat untuk membuat objek konfigurasi menggunakan cmdlet **Add-AzureProvisioningConfig** .
Gunakan objek konfigurasi untuk membuat mesin virtual menggunakan cmdlet **New-AzureVM** .
Anda dapat menggunakan objek pengaturan sertifikat untuk membuat mesin virtual menggunakan cmdlet **New-AzureQuickVM** .

## EXAMPLES

### Contoh 1: Membuat objek pengaturan sertifikat
```
PS C:\> New-AzureCertificateSetting -Thumbprint "D7BECD4D63EBAF86023BB41FA5FBF5C2C924902A" -StoreName "My"
```

Perintah ini membuat objek pengaturan sertifikat untuk sertifikat yang sudah ada.

### Contoh 2: Membuat mesin virtual yang menggunakan objek pengaturan konfigurasi
```
PS C:\> Add-AzureCertificate -ServiceName "ContosoService" -CertToDeploy "C:\temp\ContosoCert.cer"
PS C:\> $CertificateSetting = New-AzureCertificateSetting -Thumbprint "D7BECD4D63EBAF86023BB41FA5FBF5C2C924902A" -StoreName "My" 
PS C:\> $Image = Get-AzureVMImage -ImageName "ContosoStandard"
PS C:\> New-AzureVMConfig -Name "VirtualMachine17" -InstanceSize Small -ImageName $Image | Add-AzureProvisioningConfig -Windows -Certificates $CertificateSetting -Password "password" | New-AzureVM -ServiceName "ContosoService"
```

Perintah pertama menambahkan sertifikat ContosoCert.cer ke layanan bernama ContosoService menggunakan cmdlet **Add-AzureCertificate** .

Perintah kedua membuat objek pengaturan sertifikat, lalu menyimpannya dalam variabel $CertificateSetting.

Perintah ketiga mendapatkan gambar dari repositori gambar menggunakan cmdlet **Get-AzureVMImage** .
Perintah ini menyimpan gambar dalam variabel $Image.

Perintah akhir membuat objek konfigurasi mesin virtual berdasarkan gambar di $Image menggunakan cmdlet **New-AzureVMConfig** .
Perintah melewati objek tersebut ke cmdlet **Add-AzureProvisioningConfig** menggunakan operator pipeline.
Cmdlet tersebut menambahkan informasi penyediaan ke konfigurasi.
Perintah melewati objek ke cmdlet **New-AzureVM** , yang membuat mesin virtual.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoreName
Menentukan penyimpanan sertifikat untuk meletakkan sertifikat.
Nilai yang valid adalah: 

- Addressbook
- AuthRoot
- SertifikatAuthority
- Batasan
- Saya
- Akar
- TrustedPeople
- TrustedPublisher

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sidik jari
Menentukan sidik jari sertifikat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureCertificate](./Add-AzureCertificate.md)

[Add-AzureProvisioningConfig](./Add-AzureProvisioningConfig.md)

[Get-AzureCertificate](./Get-AzureCertificate.md)

[Get-AzureVMImage](./Get-AzureVMImage.md)

[New-AzureQuickVM](./New-AzureQuickVM.md)

[AzureVM baru](./New-AzureVM.md)

[Hapus-AzureCertificate](./Remove-AzureCertificate.md)


