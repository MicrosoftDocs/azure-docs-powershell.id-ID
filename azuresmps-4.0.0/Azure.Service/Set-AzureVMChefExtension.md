---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 021D4624-AE78-4FBE-B1DE-A8A84DF1FC90
online version: ''
schema: 2.0.0
ms.openlocfilehash: 197b95d6fddaa7b65d6d56b25dd0ee35f8f4977c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915661"
---
# Set-AzureVMChefExtension

## SYNOPSIS
Menambahkan ekstensi Chef ke mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Windows (Default)
```
Set-AzureVMChefExtension [-Version <String>] -ValidationPem <String> [-ClientRb <String>]
 [-BootstrapOptions <String>] [-RunList <String>] [-JsonAttribute <String>] [-ChefDaemonInterval <String>]
 [-ChefServerUrl <String>] [-ValidationClientName <String>] [-OrganizationName <String>]
 [-BootstrapVersion <String>] [-Daemon <String>] [-Secret <String>] [-SecretFile <String>] [-Windows]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Linux
```
Set-AzureVMChefExtension [-Version <String>] -ValidationPem <String> [-ClientRb <String>]
 [-BootstrapOptions <String>] [-RunList <String>] [-JsonAttribute <String>] [-ChefDaemonInterval <String>]
 [-ChefServerUrl <String>] [-ValidationClientName <String>] [-OrganizationName <String>]
 [-BootstrapVersion <String>] [-Daemon <String>] [-Secret <String>] [-SecretFile <String>] [-Linux]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVMChefExtension** menambahkan ekstensi Chef ke mesin virtual.

## EXAMPLES

### Contoh 1: Tambahkan ekstensi Chef ke mesin virtual Windows
```
PS C:\> Set-AzureVMChefExtension -VM $VM -ValidationPem "C:\\myorg-validator.pem" -ClientRb "C:\\client.rb" -RunList "Apache" -Windows;
```

Perintah ini menambahkan ekstensi Chef ke mesin virtual Windows.
Ketika mesin virtual muncul, itu bootstrap dengan Chef dan menjalankan Apache di atasnya.

### Contoh 2: Tambahkan ekstensi Chef ke mesin virtual Windows dengan bootstrapping
```
PS C:\> Set-AzureVMChefExtension -VM $VM -ValidationPem "C:\\myorg-validator.pem" -BootstrapOptions '{"chef_node_name":"your_node_name","chef_server_url":"https://api.opscode.com/organizations/some-org", "validation_client_name":"some-org-validator"}' -RunList "Apache" -Windows;
```

Perintah ini menambahkan ekstensi Chef ke mesin virtual Windows.
Ketika mesin virtual diluncurkan, itu bootstrap dengan Chef dan menjalankan Apache di atasnya.
Setelah bootstrapping, mesin virtual merujuk ke *BootstrapOptions* yang ditentukan dalam format JSON.

### Contoh 3: Tambahkan ekstensi Chef ke mesin virtual Windows dan instal Apache dan GIT
```
PS C:\> Set-AzureVMChefExtension -VM $VM -ValidationPem "C:\\myorg-validator.pem" -ChefServerUrl "http://ipaddress:port" -ValidationClientName "MyOrg-Validator" -RunList "apache, git" -Windows;
```

Perintah ini menambahkan ekstensi Chef ke mesin virtual Windows.
Ketika mesin virtual diluncurkan, itu bootstrap dengan Chef dan memiliki Apache dan GIT diinstal.
Jika Anda tidak memberikan client.rb, Anda perlu memberikan URL server Chef dan nama klien validasi.

### Contoh 4: Tambahkan ekstensi Chef ke mesin virtual Linux
```
PS C:\> Set-AzureVMChefExtension -VM $VM -ValidationPem "C:\\myorg-validator.pem" -ChefServerUrl "http://ipaddress:port" -OrganizationName "MyOrg" -Linux;
```

Perintah ini menambahkan ekstensi Chef ke mesin virtual Linux.
Ketika mesin virtual diluncurkan, itu bootstrap dengan Chef.
Jika tidak menyediakan client.rb, Anda perlu menyediakan URL dan organisasi server Chef.

## PARAMETERS

### -BootstrapOptions
Menentukan opsi bootstrap dalam format JavaScript Object Notation (JSON).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BootstrapVersion
Menentukan versi klien Chef yang diinstal bersama dengan ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ChefDaemonInterval
Menentukan frekuensi (dalam menit) tempat layanan koki berjalan. Jika Anda tidak ingin layanan koki diinstal di Azure VM lalu tetapkan nilai sebagai 0 di bidang ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ChefServiceInterval

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ChefServerUrl
Menentukan URL server Chef.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientRb
Menentukan jalur lengkap chef client.rb.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Daemon
Mengonfigurasi layanan klien koki untuk eksekusi tanpa pengawas. Platform simpul harus Windows.
Opsi yang diperbolehkan: 'tidak ada','layanan' dan 'tugas'.
tidak ada - Saat ini mencegah layanan chef-client dikonfigurasi sebagai layanan.
service - Mengonfigurasi chef-client untuk berjalan secara otomatis di latar belakang sebagai layanan.
tugas - Mengonfigurasi klien koki untuk berjalan secara otomatis di latar belakang sebagai tugas terjadwal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -JsonAttribute
String JSON yang akan ditambahkan ke run of chef-client pertama. misalnya -JsonAttribute '{"foo" : "bar"}'

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Menunjukkan bahwa cmdlet ini membuat mesin virtual berbasis Linux.

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

### -OrganizationName
Menentukan nama organisasi ekstensi Koki.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RunList
Menentukan daftar run chef node.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rahasia
Kunci enkripsi yang digunakan untuk mengenkripsi dan mendekripsi nilai item tas data.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretFile
Jalur ke file yang berisi kunci enkripsi yang digunakan untuk mengenkripsi dan mendekripsi nilai item tas data.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValidationClientName
Menentukan nama klien validasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ValidationPem
Menentukan jalur file .pem validator Koki.

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

### -Versi
Menentukan nomor versi ekstensi Chef.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual persisten.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa cmdlet ini membuat mesin virtual Windows.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMChefExtension](./Get-AzureVMChefExtension.md)

[Hapus-AzureVMChefExtension](./Remove-AzureVMChefExtension.md)


