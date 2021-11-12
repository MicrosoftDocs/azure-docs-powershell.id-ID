---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: AzureRM.KeyVault
ms.assetid: 9FC72DE9-46BB-4CB5-9880-F53756DBE012
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.keyvault/set-azurekeyvaultsecret
schema: 2.0.0
ms.openlocfilehash: 0c482d3fd4e2e02221799ea72e61eacc80ff9e2a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132429194"
---
# Set-AzureKeyVaultSecret

## SYNOPSIS
Membuat atau memperbarui rahasia di kunci vault.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureKeyVaultSecret [-VaultName] <String> [-Name] <String> [-SecretValue] <SecureString> [-Disable]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureKeyVaultSecret** membuat atau memperbarui rahasia dalam penyimpanan kunci di Azure Key Vault. Jika rahasia tidak ada, cmdlet ini akan membuatnya. Jika rahasia sudah ada, cmdlet ini membuat versi baru rahasia itu.

## EXAMPLES

### Contoh 1: Mengubah nilai rahasia menggunakan atribut default
```
PS C:\> $Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Set-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret
```

Perintah pertama mengonversi string menjadi string yang aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu dalam $Secret variabel. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString` .

Perintah kedua mengubah nilai rahasia bernama ITSecret dalam kunci vault bernama Contoso. Nilai rahasia menjadi nilai yang disimpan di $Secret.

### Contoh 2: Mengubah nilai rahasia menggunakan atribut kustom
```
PS C:\> $Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NBF =(Get-Date).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'medium'; 'IT' = null }
PS C:\> $ContentType = 'txt'
PS C:\> Set-AzureKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret -Expires $Expires -NotBefore $NBF -ContentType $ContentType -Disable $False -Tags $Tags
```

Perintah pertama mengonversi string menjadi string yang aman dengan menggunakan cmdlet **ConvertTo-SecureString,** lalu menyimpan string itu dalam $Secret variabel. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString` .

Perintah berikutnya menentukan atribut kustom untuk tanggal kedaluwarsa, tag, dan tipe konteks, dan menyimpan atribut dalam variabel.

Perintah terakhir mengubah nilai rahasia bernama ITSecret di kunci vault bernama Contoso, dengan menggunakan nilai yang ditentukan sebelumnya sebagai variabel.

## PARAMETERS

### -ContentType
Menentukan tipe konten rahasia.
Untuk menghapus tipe konten yang sudah ada, tentukan string kosong.

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

### -Disable
Mengindikasikan bahwa cmdlet ini rahasia.

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

### -Kedaluwarsa
Menentukan waktu kedaluwarsa, sebagai objek **DateTime,** untuk rahasia pembaruan cmdlet ini.
Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan **objek DateTime,** gunakan cmdlet **Get-Date.** Untuk informasi selengkapnya, ketik `Get-Help Get-Date` .

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
Menentukan nama rahasia untuk diubah. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN, Fully Qualified Domain Name) dari rahasia berdasarkan nama yang ditentukan parameter ini, nama kunci vault, dan lingkungan Anda saat ini.

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
Menentukan waktu, sebagai objek **DateTime,** sebelum di mana rahasia tidak bisa digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan **objek DateTime,** gunakan cmdlet **Get-Date.**

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

### -SecretValue
Menentukan nilai untuk rahasia sebagai objek **SecureString.** Untuk mendapatkan objek **SecureString,** gunakan cmdlet **ConvertTo-SecureString.** Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString` .

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
Menentukan nama kunci vault yang dimiliki rahasia ini. Cmdlet ini menyusun FQDN dari kunci vault berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.Secret

## CATATAN

## RELATED LINKS

[Get-AzureKeyVaultSecret](./Get-AzureKeyVaultSecret.md)

[Remove-AzureKeyVaultSecret](./Remove-AzureKeyVaultSecret.md)
