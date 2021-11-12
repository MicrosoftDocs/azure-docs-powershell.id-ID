---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: AA58B897-EFA0-4321-9246-ED8E11AB3538
online version: ''
schema: 2.0.0
ms.openlocfilehash: 83bab34bea06b65f1f824c03694b1fc570a2dfc761333516334802d361b52987
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419220"
---
# New-AzureSSHKey

## SYNOPSIS
Membuat objek Kunci LINUX untuk menyisipkan sertifikat yang sudah ada ke komputer virtual Azure berbasis Linux baru.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### keypair
```
New-AzureSSHKey [-KeyPair] [-Fingerprint] <String> [-Path] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### publickey
```
New-AzureSSHKey [-PublicKey] [-Fingerprint] <String> [-Path] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureSSHKey** membuat objek Key CMDLETSINDAH UNTUK sertifikat yang telah ditambahkan ke Azure.
Objek Kunci ROUTER ini kemudian dapat digunakan oleh **New-AzureProvisioningConfig** ketika membuat objek konfigurasi untuk mesin virtual baru menggunakan **New-AzureVM**, atau saat membuat mesin virtual baru dengan **New-AzureQuickVM**.
Ketika disertakan sebagai bagian dari skrip pembuatan mesin virtual, langkah ini akan menambahkan Kunci Publik SHELL atau Key Pair yang ditentukan ke mesin virtual baru.

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

Perintah ini menambahkan sertifikat ke layanan Azure, lalu membuat mesin virtual Linux baru yang menggunakan sertifikat tersebut.

## PARAMETERS

### -Fingerprint
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
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

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
Menentukan bahwa cmdlet ini membuat objek untuk menyisipkan Pasangan Tombol CMDLET CMDLET ke dalam konfigurasi mesin virtual yang baru.

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

### -Path
Menentukan jalur untuk menyimpan Kunci Publik DAN Key Pair CHROME.

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
Menentukan bahwa cmdlet ini membuat objek untuk menyisipkan Kunci Publik CMDLETS ke konfigurasi mesin virtual yang baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureProvisioningConfig](./Add-AzureProvisioningConfig.md)

[New-AzureVMConfig](./New-AzureVMConfig.md)

[New-AzureVM](./New-AzureVM.md)

[New-AzureQuickVM](./New-AzureQuickVM.md)


