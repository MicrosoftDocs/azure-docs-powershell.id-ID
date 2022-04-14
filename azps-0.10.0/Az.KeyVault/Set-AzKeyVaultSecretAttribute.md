---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: E2A45461-6B41-42FF-A874-A4CEFC867A33
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/set-AzKeyvaultsecretattribute
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecretAttribute.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecretAttribute.md
ms.openlocfilehash: 719f0676b87cf785785b0adfbfde71ad2a6b965b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142057620"
---
# Set-AzKeyVaultSecretAttribute

## SYNOPSIS
Memperbarui atribut rahasia dalam kubah kunci.

## SYNTAX

```
Set-AzKeyVaultSecretAttribute [-VaultName] <String> [-Name] <String> [[-Version] <String>]
 [-Enable <Boolean>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Set-AzKeyVaultSecretAttribute** memperbarui atribut rahasia yang dapat diedit dalam kubah kunci.

## EXAMPLES

### Contoh 1: Memodifikasi atribut rahasia
```
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Nbf = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'medium'; 'HR' = null}
PS C:\> $ContentType= 'xml'
PS C:\> Set-AzKeyVaultSecretAttribute -VaultName 'ContosoVault' -Name 'HR' -Expires $Expires -NotBefore $Nbf -ContentType $ContentType -Enable $True -Tag $Tags -PassThru
```

Empat perintah pertama menentukan atribut untuk tanggal kedaluwarsa, tanggal NotBefore, tag, dan tipe konteks, dan menyimpan atribut dalam variabel.

Perintah akhir mengubah atribut untuk rahasia bernama HR dalam kubah kunci bernama ContosoVault, menggunakan variabel yang disimpan.

### Contoh 2: Menghapus tag dan tipe konten untuk rahasia
```
PS C:\>Set-AzKeyVaultSecretAttribute -VaultName 'ContosoVault' -Name 'HR' -Version '9EEA45C6EE50490B9C3176A80AC1A0DF' -ContentType '' -Tag -@{}
```

Perintah ini menghapus tag dan tipe konten untuk versi rahasia tertentu yang bernama HR dalam kubah kunci bernama Contoso.

### Contoh 3: Menonaktifkan versi rahasia saat ini yang namanya dimulai dengan TI
```
PS C:\> $Vault = 'ContosoVault'
PS C:\> $Prefix = 'IT'
PS C:\> Get-AzKeyVaultSecret $Vault | Where-Object {$_.Name -like $Prefix + '*'} | Set-AzKeyVaultSecretAttribute -Enable $False
```

Perintah pertama menyimpan nilai string Contoso dalam variabel $Vault.

Perintah kedua menyimpan nilai string TI dalam variabel $Prefix.

Perintah ketiga menggunakan cmdlet Get-AzKeyVaultSecret untuk mendapatkan rahasia dalam kubah kunci yang ditentukan, lalu meneruskan rahasia tersebut ke cmdlet **Where-Object** . Cmdlet **Where-Object** memfilter rahasia untuk nama yang dimulai dengan karakter TI. Perintah menyalurkan rahasia yang cocok dengan filter ke cmdlet Set-AzKeyVaultSecretAttribute, yang menonaktifkannya.

### Contoh 4: Mengatur ContentType untuk semua versi rahasia
```
PS C:\>$VaultName = 'ContosoVault'
PS C:\> $Name = 'HR'
PS C:\> $ContentType = 'xml'
PS C:\> Get-AzKeyVaultKey -VaultName $VaultName -Name $Name -IncludeVersions | Set-AzKeyVaultSecretAttribute -ContentType $ContentType
```

Tiga perintah pertama menentukan variabel string yang akan digunakan untuk parameter *VaultName*, *Name*, dan *ContentType* . Perintah keempat menggunakan cmdlet Get-AzKeyVaultKey untuk mendapatkan tombol yang ditentukan, dan menyalurkan kunci ke cmdlet Set-AzKeyVaultSecretAttribute untuk mengatur tipe kontennya ke XML.

## PARAMETERS

### -ContentType
Menentukan tipe konten rahasia. Jika Anda tidak menentukan parameter ini, tidak ada perubahan pada tipe konten rahasia saat ini. Untuk menghapus tipe konten yang sudah ada, tentukan string kosong.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Menunjukkan apakah akan mengaktifkan rahasia. Tentukan $False untuk menonaktifkan rahasia, atau $True untuk mengaktifkan rahasia. Jika Anda tidak menentukan parameter ini, tidak ada perubahan pada status rahasia saat ini yang diaktifkan atau dinonaktifkan.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kedaluwarsa
Menentukan tanggal dan waktu kedaluwarsa rahasia.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama rahasia. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) rahasia berdasarkan nama yang ditentukan parameter ini, nama kubah kunci, dan lingkungan Anda saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TidakBefore
Menentukan Waktu Universal Terkoordinasi (UTC) sebelum rahasia tidak dapat digunakan.
Jika Anda tidak menentukan parameter ini, tidak ada perubahan pada atribut NotBefore rahasia saat ini.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya:

@{key0="value0";key1=$null;key2="value2"}

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Menentukan nama kubah kunci untuk diubah.
Cmdlet ini menyusun FQDN kubah kunci berdasarkan nama yang ditentukan parameter ini, dan lingkungan yang dipilih saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Menentukan versi rahasia.
Cmdlet ini menyusun FQDN rahasia berdasarkan nama kubah kunci, lingkungan yang dipilih saat ini, nama rahasia, dan versi rahasia.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SecretVersion

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.Secret
Mengembalikan objek Microsoft.Azure.Commands.KeyVault.Models.Secret jika PassThru ditentukan. Jika tidak, tidak mengembalikan apa pun.

## CATATAN

## RELATED LINKS

[Get-AzKeyVaultKey](./Get-AzKeyVaultKey.md)

[Get-AzKeyVaultSecret](./Get-AzKeyVaultSecret.md)

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)
