---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: E2A45461-6B41-42FF-A874-A4CEFC867A33
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/set-azurekeyvaultsecretattribute
schema: 2.0.0
ms.openlocfilehash: f8463533f8a153b74df1863ba251950f16f9e19a
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "132415060"
---
# Set-AzureKeyVaultSecretAttribute

## SYNOPSIS
Memperbarui atribut rahasia di kunci vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureKeyVaultSecretAttribute [-VaultName] <String> [-Name] <String> [[-Version] <String>]
 [-Enable <Boolean>] [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureKeyVaultSecretAttribute** memperbarui atribut rahasia yang dapat diedit di kunci vault.

## EXAMPLES

### Contoh 1: Mengubah atribut dari sebuah rahasia
```
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Nbf = (Get-Date).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'medium'; 'HR' = null}
PS C:\> $ContentType= 'xml'
PS C:\> Set-AzureKeyVaultSecretAttribute -VaultName 'ContosoVault' -Name 'HR' -Expires $Expires -NotBefore $Nbf -ContentType $ContentType -Enable $True -Tag $Tags -PassThru
```

Empat perintah pertama menentukan atribut untuk tanggal kedaluwarsa, tanggal NotBefore, tag, dan tipe konteks, dan menyimpan atribut dalam variabel.

Perintah terakhir mengubah atribut untuk rahasia yang bernama HR dalam kunci vault yang bernama ContosoVault, menggunakan variabel yang disimpan.

### Contoh 2: Menghapus tag dan tipe konten untuk rahasia
```
PS C:\>Set-AzureKeyVaultSecretAttribute -VaultName 'ContosoVault' -Name 'HR' -Version '9EEA45C6EE50490B9C3176A80AC1A0DF' -ContentType '' -Tag -@{}
```

Perintah ini menghapus tag dan tipe konten untuk versi rahasia tertentu bernama HR di key vault bernama Contoso.

### Contoh 3: Menonaktifkan versi rahasia saat ini yang namanya dimulai dengan IT
```
PS C:\> $Vault = 'ContosoVault'
PS C:\> $Prefix = 'IT'
PS C:\> Get-AzureKeyVaultSecret $Vault | Where-Object {$_.Name -like $Prefix + '*'} | Set-AzureKeyVaultSecretAttribute -Enable $False
```

Perintah pertama menyimpan nilai string Contoso dalam $Vault string.

Perintah kedua menyimpan nilai string IT dalam $Prefix nilai.

Perintah ketiga menggunakan cmdlet Get-AzureKeyVaultSecret rahasia untuk mendapatkan rahasia dalam penyimpanan kunci tertentu, lalu melewati rahasia tersebut ke cmdlet **Where-Object** . Cmdlet **Where-Object** memfilter rahasia untuk nama yang dimulai dengan karakter IT. Perintah akan pipa rahasia yang cocok dengan filter ke cmdlet Set-AzureKeyVaultSecretAttribute, yang akan menonaktifkannya.

### Contoh 4: Setel ContentType untuk semua versi rahasia
```
PS C:\>$VaultName = 'ContosoVault'
PS C:\> $Name = 'HR'
PS C:\> $ContentType = 'xml'
PS C:\> Get-AzureKeyVaultKey -VaultName $VaultName -Name $Name -IncludeVersions | Set-AzureKeyVaultSecretAttribute -ContentType $ContentType
```

Tiga perintah pertama menentukan variabel string yang akan digunakan untuk *parameter VaultName*, *Name*, *dan ContentType* . Perintah keempat menggunakan cmdlet Get-AzureKeyVaultKey cmdlet untuk mendapatkan kunci yang ditentukan, dan pipakan tombol ke cmdlet Set-AzureKeyVaultSecretAttribute untuk mengatur tipe kontennya ke XML.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktifkan
Menunjukkan apakah ingin mengaktifkan rahasia. Tentukan $False untuk menonaktifkan rahasia, $True untuk mengaktifkan rahasia. Jika Anda tidak menentukan parameter ini, tidak ada perubahan untuk status rahasia aktif atau nonaktif saat ini.

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
Menentukan tanggal dan waktu rahasia kedaluwarsa.

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
Menentukan nama rahasia. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN, Fully Qualified Domain Name) dari rahasia berdasarkan nama yang ditentukan parameter ini, nama kunci vault, dan lingkungan Anda saat ini.

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

### -NotBefore
Menentukan Waktu Universal Terkoordinasi (UTC) sebelum rahasianya tidak dapat digunakan.
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
Mengembalikan objek yang mewakili item yang Anda kerjakan.
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
Menentukan nama kunci vault untuk diubah.
Cmdlet ini menyusun FQDN dari kunci vault berdasarkan nama yang ditentukan parameter ini, dan lingkungan yang saat ini dipilih.

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
Cmdlet ini menyusun FQDN dari rahasia berdasarkan nama key vault, lingkungan yang Anda pilih saat ini, nama rahasia, dan versi rahasia.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.Secret
Mengembalikan objek Microsoft.Azure.Commands.KeyVault.Models.Secret jika PassThru ditentukan. Jika tidak, kembalikan apa pun.

## CATATAN

## RELATED LINKS

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Get-AzureKeyVaultSecret](./Get-AzureKeyVaultSecret.md)

[Remove-AzureKeyVaultSecret](./Remove-AzureKeyVaultSecret.md)
