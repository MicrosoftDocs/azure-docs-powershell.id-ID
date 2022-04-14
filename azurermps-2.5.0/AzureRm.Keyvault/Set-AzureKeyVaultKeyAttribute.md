---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/set-azurekeyvaultkeyattribute
schema: 2.0.0
ms.openlocfilehash: e7daafc147775b128351a7fa9ffb7b4d807bfe17
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142104083"
---
# Set-AzureKeyVaultKeyAttribute

## SYNOPSIS
Memperbarui atribut kunci dalam kubah kunci.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureKeyVaultKeyAttribute [-VaultName] <String> [-Name] <String> [[-Version] <String>] [-Enable <Boolean>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-KeyOps <String[]>] [-Tag <Hashtable>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureKeyVaultKeyAttribute** memperbarui atribut kunci yang dapat diedit dalam kubah kunci.

## EXAMPLES

### Contoh 1: Memodifikasi kunci untuk mengaktifkannya, dan mengatur tanggal kedaluwarsa dan tag
```
PS C:\>$Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $Tags = @{'Severity' = 'high'; 'Accounting' = null}
PS C:\> Set-AzureKeyVaultKeyAttribute -VaultName 'Contoso' -Name 'ITSoftware' -Expires $Expires -Enable $True -Tag $Tags -PassThru
```

Perintah pertama membuat objek **DateTime** menggunakan cmdlet **Get-Date** . Objek tersebut menentukan waktu dua tahun di masa mendatang. Perintah menyimpan tanggal tersebut dalam variabel $Expires.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

Perintah kedua membuat variabel untuk menyimpan nilai tag dengan tingkat keparahan tinggi dan Akuntansi.

Perintah akhir mengubah kunci bernama ITSoftware. Perintah mengaktifkan kunci, mengatur waktu kedaluwarsanya ke waktu yang disimpan di $Expires, dan mengatur tag yang disimpan di $Tags.

### Contoh 2: Mengubah kunci untuk menghapus semua tag
```
PS C:\>Set-AzureKeyVaultKeyAttribute -VaultName 'Contoso' -Name 'ITSoftware' -Version '7EEA45C6EE50490B9C3176F80AC1A0DG' -Tag @{}
```

Perintah ini menghapus semua tag untuk versi kunci tertentu yang bernama ITSoftware.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Menentukan apakah akan mengaktifkan atau menonaktifkan kunci. Nilai $True mengaktifkan kunci. Nilai $False menonaktifkan kunci. Jika Anda tidak menentukan parameter ini, cmdlet ini tidak mengubah status kunci.

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
Menentukan waktu kedaluwarsa, sebagai objek **DateTime** , untuk kunci yang diperbarui cmdlet ini. Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

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

### -KeyOps
Menentukan array operasi yang dapat dilakukan dengan menggunakan kunci yang ditambahkan cmdlet ini.
Jika Anda tidak menentukan parameter ini, semua operasi dapat dilakukan.

Nilai yang dapat diterima untuk parameter ini adalah daftar operasi kunci yang dipisahkan koma seperti yang ditentukan oleh spesifikasi Kunci Web JSON. Nilai ini (peka huruf besar/kecil) adalah:

- Mengenkripsi
- Mendekripsi
- Bungkus
- Membuka
- Tanda
- Memverifikasi
- Cadangan
- Mengembalikan

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama kunci yang akan diperbarui. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) kunci berdasarkan nama yang ditentukan parameter ini, nama kubah kunci, dan lingkungan Anda saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TidakBefore
Menentukan waktu, sebagai objek **DateTime** , sebelum kunci tidak dapat digunakan.
Parameter ini menggunakan UTC.
Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** .

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
Menentukan nama kubah kunci tempat cmdlet ini mengubah kunci.
Cmdlet ini menyusun FQDN kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Menentukan versi kunci.
Cmdlet ini menyusun FQDN kunci berdasarkan nama kubah kunci, lingkungan yang dipilih saat ini, nama kunci, dan versi kunci.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyVersion

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.KeyBundle

## CATATAN

## RELATED LINKS

[Add-AzureKeyVaultKey](./Add-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Hapus-AzureKeyVaultKey](./Remove-AzureKeyVaultKey.md)
