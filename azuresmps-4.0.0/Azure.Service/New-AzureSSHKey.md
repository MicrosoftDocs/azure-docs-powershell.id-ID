---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: AA58B897-EFA0-4321-9246-ED8E11AB3538
online version: ''
schema: 2.0.0
ms.openlocfilehash: 99c011e61b4381e7241d3f5fdcfde43572e6d685
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245152"
---
# New-AzureSSHKey

## SYNOPSIS
Membuat objek Kunci SSH untuk menyisipkan sertifikat yang sudah ada ke mesin virtual Azure berbasis Linux yang baru.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### keypair
```
New-AzureSSHKey [-KeyPair] [-Fingerprint] <String> [-Path] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### kunci publik
```
New-AzureSSHKey [-PublicKey] [-Fingerprint] <String> [-Path] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **AzureSSHKey Baru** membuat objek Kunci SSH untuk sertifikat yang telah ditambahkan ke Azure.
Objek Kunci SSH ini kemudian dapat digunakan oleh **New-AzureProvisioningConfig** saat membuat objek konfigurasi untuk mesin virtual baru menggunakan **New-AzureVM**, atau saat membuat mesin virtual baru dengan **New-AzureQuickVM**.
Ketika disertakan sebagai bagian dari skrip pembuatan mesin virtual, ini menambahkan Kunci Publik SSH atau Pasangan Kunci tertentu ke mesin virtual baru.

## EXAMPLES

### Contoh 1: Membuat objek pengaturan sertifikat
```
PS C:\> $myLxCert = New-AzureSSHKey -Fingerprint "D7BECD4D63EBAF86023BB4F1A5FBF5C2C924902A" -Path "/home/username/.ssh/authorized_keys"
```

Perintah ini membuat objek pengaturan sertifikat untuk sertifikat yang sudah ada lalu menyimpan objek dalam variabel untuk digunakan nanti.

### Contoh 2: Menambahkan sertifikat ke layanan
```
PS C:\> Add-AzureCertificate -ServiceName "MySvc" -CertToDeploy "C:\temp\MyLxCert.cer"
$myLxCert = New-AzureSSHKey ?Fingerprint "D7BECD4D63EBAF86023BB4F1A5FBF5C2C924902A" -Path "/home/username/.ssh/authorized_keys"
New-AzureVMConfig -Name "MyVM2" -InstanceSize Small -ImageName $LxImage `
          | Add-AzureProvisioningConfig -Linux -LinuxUser $lxUser -SSHPublicKeys $myLxCert -Password 'pass@word1' `
          | New-AzureVM -ServiceName "MySvc"
```

Perintah ini menambahkan sertifikat ke layanan Azure, lalu membuat mesin virtual Linux baru yang menggunakan sertifikat.

## PARAMETERS

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

### -KeyPair
Menentukan bahwa cmdlet ini membuat objek untuk menyisipkan Pasangan Tombol SSH ke konfigurasi mesin virtual baru.

```yaml
Type: SwitchParameter
Parameter Sets: keypair
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur untuk menyimpan Kunci Publik SSH atau Pasangan Kunci.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicKey
Menentukan bahwa cmdlet ini membuat objek untuk menyisipkan Kunci Publik SSH ke konfigurasi mesin virtual baru.

```yaml
Type: SwitchParameter
Parameter Sets: publickey
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureProvisioningConfig](./Add-AzureProvisioningConfig.md)

[AzureVMConfig baru](./New-AzureVMConfig.md)

[AzureVM baru](./New-AzureVM.md)

[New-AzureQuickVM](./New-AzureQuickVM.md)


