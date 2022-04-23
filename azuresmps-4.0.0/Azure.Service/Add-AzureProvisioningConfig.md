---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 0B3EF123-8424-4CCA-95E8-01301B70CBDC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 063014d8230346d580f4be3959da674efece041f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212301"
---
# Add-AzureProvisioningConfig

## SYNOPSIS
Menambahkan konfigurasi penyediaan untuk mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Windows (Default)
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-CustomDataFile <String>] [-Windows]
 [-AdminUsername <String>] [-Password <String>] [-ResetPasswordOnFirstLogon] [-DisableAutomaticUpdates]
 [-NoRDPEndpoint] [-TimeZone <String>] [-Certificates <CertificateSettingList>] [-EnableWinRMHttp]
 [-DisableWinRMHttps] [-WinRMCertificate <X509Certificate2>] [-X509Certificates <X509Certificate2[]>]
 [-NoExportPrivateKey] [-NoWinRMEndpoint] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Linux
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-Linux] [-LinuxUser <String>]
 [-DisableSSH] [-NoSSHEndpoint] [-NoSSHPassword] [-SSHPublicKeys <SSHPublicKeyList>]
 [-SSHKeyPairs <SSHKeyPairList>] [-CustomDataFile <String>] [-Password <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### WindowsDomain
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-CustomDataFile <String>]
 -AdminUsername <String> [-WindowsDomain] [-Password <String>] [-ResetPasswordOnFirstLogon]
 [-DisableAutomaticUpdates] [-NoRDPEndpoint] [-TimeZone <String>] [-Certificates <CertificateSettingList>]
 -JoinDomain <String> -Domain <String> -DomainUserName <String> -DomainPassword <String>
 [-MachineObjectOU <String>] [-EnableWinRMHttp] [-DisableWinRMHttps] [-WinRMCertificate <X509Certificate2>]
 [-X509Certificates <X509Certificate2[]>] [-NoExportPrivateKey] [-NoWinRMEndpoint] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureProvisioningConfig** menambahkan penyediaan informasi konfigurasi ke konfigurasi mesin virtual Azure.
Anda dapat menggunakan objek konfigurasi untuk membuat mesin virtual.

Cmdlet ini mendukung konfigurasi penyediaan yang berbeda, termasuk server Windows mandiri, server Windows yang bergabung ke domain Direktori Aktif, dan server berbasis Linux.

Untuk membuat server gabungan domain Direktori Aktif, tentukan nama domain domain yang sepenuhnya memenuhi syarat dari domain Direktori Aktif dan kredensial domain pengguna yang memiliki izin untuk bergabung dengan mesin virtual ke domain.

## EXAMPLES

### Contoh 1: Membuat mesin virtual mandiri
```
PS C:\> New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" | New-AzureVM -ServiceName "ContosoService"
```

Perintah ini membuat objek konfigurasi mesin virtual menggunakan cmdlet **New-AzureVMConfig** .
Perintah melewati objek tersebut ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menambahkan konfigurasi penyediaan untuk mesin virtual yang menjalankan sistem operasi Windows.
Konfigurasi mencakup nama pengguna dan kata sandi administrator.
Perintah melewati konfigurasi ke cmdlet **New-AzureVM** , yang membuat mesin virtual.

### Contoh 2: Membuat mesin virtual gabungan domain
```
PS C:\> New-AzureVMConfig -Name "DomainVM" -InstanceSize Small -ImageName "Image09" | Add-AzureProvisioningConfig -WindowsDomain -Password "password" -AdminUsername "AdminMain" -ResetPasswordOnFirstLogon -JoinDomain "contoso.com" -Domain "contoso" -DomainUserName "DomainAdminUser" -DomainPassword "DomainPassword" -MachineObjectOU 'OU=AzureVMs,DC=contoso,DC=com' | New-AzureVM -ServiceName "ContosoService"
```

Perintah ini membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan untuk mesin virtual yang akan digabungkan dengan domain contoso.
Perintah ini menyertakan nama pengguna dan kata sandi yang diperlukan untuk bergabung dengan mesin virtual ke domain.
Konfigurasi mengharuskan pengguna untuk mengubah kata sandi pengguna pada saat masuk pertama.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

### Contoh 3: Membuat mesin virtual berbasis Linux
```
PS C:\> New-AzureVMConfig -Name "LinuxVM" -InstanceSize Small -ImageName "LinuxImage03" | Add-AzureProvisioningConfig -Linux -LinuxUser "LinuxRoot" -Password "password" | New-AzureVM -ServiceName "ContosoService"
```

Perintah ini membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan untuk mesin virtual yang menjalankan sistem operasi Linux.
Konfigurasi mencakup nama pengguna dan kata sandi akar.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

### Contoh 4: Membuat mesin virtual yang menyertakan sertifikat untuk WinRM
```
PS C:\> $certs = Get-ChildItem Cert:\CurrentUser\My
New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image11" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -WinRMCertificate $certs[0] -X509Certificates $certs[1], $certs[2] | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

Perintah pertama mendapatkan sertifikat dari penyimpanan sertifikat, lalu menyimpannya dalam variabel array $certs.

Perintah kedua membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan yang menyertakan sertifikat untuk WinRM.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

### Contoh 5: Membuat mesin virtual yang mengaktifkan WinRM melalui HTTP
```
PS C:\> New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image14" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -EnableWinRMHttp | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

Perintah ini membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan yang mengaktifkan WinRM melalui HTTP.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

### Contoh 6: Membuat mesin virtual yang menonaktifkan WinRM melalui HTTPS
```
PS C:\> New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -DisableWinRMHttps | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

Perintah ini membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan yang menonaktifkan WinRM melalui HTTPS.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

### Contoh 7: Membuat mesin virtual tanpa ekspor kunci
```
PS C:\> $certs = Get-ChildItem Cert:\CurrentUser\My
New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -X509Certificates $certs[0], $certs[1] -NoExportPrivateKey | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

Perintah pertama mendapatkan sertifikat dari penyimpanan sertifikat, lalu menyimpannya dalam variabel array $certs.

Perintah kedua membuat objek konfigurasi mesin virtual, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini menambahkan konfigurasi penyediaan untuk mesin virtual yang menyertakan sertifikat dan tidak mengekspor kunci privat.
Perintah membuat mesin virtual berdasarkan objek penyediaan.

## PARAMETERS

### -AdminUsername
Menentukan nama pengguna akun Administrator yang dibuat konfigurasi ini pada mesin virtual.

```yaml
Type: String
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sertifikat
Menentukan sekumpulan sertifikat yang diinstal konfigurasi ini pada mesin virtual.

```yaml
Type: CertificateSettingList
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomDataFile
Menentukan file data untuk mesin virtual.
Cmdlet ini mengkodekan konten file sebagai Base64.
Panjang file harus kurang dari 64 kilobyte.

Jika sistem operasi tamu adalah sistem operasi Windows, konfigurasi ini menyimpan data ini sebagai file biner bernama %SYSTEMDRIVE%\AzureData\CustomData.bin.

Jika sistem operasi tamu adalah Linux, konfigurasi ini melewati data menggunakan file ovf-env.xml.
Konfigurasi menyalin file tersebut ke direktori /var/lib/waagent.
Agen juga menyimpan data berkode Base64 di /var/lib/waagent/CustomData.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutomaticUpdates
Menunjukkan bahwa konfigurasi ini menonaktifkan pembaruan otomatis.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGuestAgent
Menunjukkan bahwa konfigurasi ini menonaktifkan infrastruktur sebagai agen tamu layanan (IaaS).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSSH
Menunjukkan bahwa konfigurasi ini menonaktifkan SSH.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableWinRMHttps
Menunjukkan bahwa konfigurasi ini menonaktifkan Windows Remote Management (WinRM) di HTTPS.
Secara default, WinRM diaktifkan melalui HTTPS.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Menentukan nama domain akun yang memiliki izin untuk menambahkan komputer ke domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainPassword
Menentukan kata sandi akun pengguna yang memiliki izin untuk menambahkan komputer ke domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainUserName
Menentukan nama akun pengguna yang memiliki izin untuk menambahkan komputer ke domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWinRMHttp
Menunjukkan bahwa konfigurasi ini mengaktifkan WinRM melalui HTTP.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
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

### -JoinDomain
Menentukan nama domain yang sepenuhnya memenuhi syarat (FQDN) domain yang akan digabungkan.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Linux
Menunjukkan bahwa konfigurasi ini membuat konfigurasi Linux.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxUser
Menentukan nama pengguna akun administratif Linux yang dibuat konfigurasi ini pada mesin virtual.

```yaml
Type: String
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineObjectOU
Menentukan nama unit organisasi (OU) yang sepenuhnya memenuhi syarat di mana konfigurasi membuat akun komputer.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoExportPrivateKey
Menunjukkan bahwa konfigurasi ini tidak mengunggah kunci privat.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRDPEndpoint
Menunjukkan bahwa konfigurasi ini membuat mesin virtual tanpa titik akhir desktop jarak jauh.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSSHEndpoint
Menunjukkan bahwa konfigurasi ini membuat mesin virtual tanpa titik akhir SSH.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSSHPassword
Menunjukkan bahwa konfigurasi ini membuat mesin virtual tanpa kata sandi SSH.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWinRMEndpoint
Menunjukkan bahwa konfigurasi ini tidak menambahkan titik akhir WinRM untuk mesin virtual.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Menentukan kata sandi akun administrator.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResetPasswordOnFirstLogon
Menunjukkan bahwa mesin virtual mengharuskan pengguna untuk mengubah kata sandi pada saat masuk pertama.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHKeyPairs
Menentukan pasangan kunci SSH.

```yaml
Type: SSHKeyPairList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHPublicKeys
Menentukan kunci publik SSH.

```yaml
Type: SSHPublicKeyList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona Waktu
Menentukan zona waktu untuk mesin virtual, misalnya, Waktu Standar Pasifik atau Waktu Standar Pusat Kanada.

```yaml
Type: String
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa konfigurasi ini membuat mesin virtual mandiri yang menjalankan sistem operasi Windows.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsDomain
Menunjukkan bahwa konfigurasi ini membuat server Windows yang digabungkan ke domain Direktori Aktif.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinRMCertificate
Menentukan sertifikat yang terkait dengan konfigurasi ini ke titik akhir WinRM.

```yaml
Type: X509Certificate2
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X509Sertifikaat
Menentukan array sertifikat X509 yang digunakan untuk layanan yang dihosting.

```yaml
Type: X509Certificate2[]
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
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

[AzureVM baru](./New-AzureVM.md)

[AzureVMConfig baru](./New-AzureVMConfig.md)


