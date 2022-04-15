---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 9FC72DE9-46BB-4CB5-9880-F53756DBE012
online version: https://docs.microsoft.com/en-us/powershell/module/Az.keyvault/set-AzKeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecret.md
ms.openlocfilehash: 56a3fb2d31e4f80b15c027945437ffdc78aa131a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141917499"
---
# Set-AzKeyVaultSecret

## SYNOPSIS
Membuat atau memperbarui rahasia dalam kubah kunci.

## SYNTAX

```
Set-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [-SecretValue] <SecureString> [-Disable]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzKeyVaultSecret** membuat atau memperbarui rahasia dalam kubah kunci di Azure Key Vault. Jika rahasia tidak ada, cmdlet ini akan membuatnya. Jika rahasia sudah ada, cmdlet ini membuat versi baru rahasia itu.

## EXAMPLES

### Contoh 1: Memodifikasi nilai rahasia menggunakan atribut default
```
PS C:\> $Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> Set-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret
```

Perintah pertama mengonversi string menjadi string aman menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Secret. Untuk informasi selengkapnya, ketik .`Get-Help
ConvertTo-SecureString`

Perintah kedua mengubah nilai rahasia bernama ITSecret dalam kubah kunci bernama Contoso. Nilai rahasia menjadi nilai yang disimpan dalam $Secret.

### Contoh 2: Memodifikasi nilai rahasia menggunakan atribut kustom
```
PS C:\> $Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
PS C:\> $Expires = (Get-Date).AddYears(2).ToUniversalTime()
PS C:\> $NBF =(Get-Date).ToUniversalTime()
PS C:\> $Tags = @{ 'Severity' = 'medium'; 'IT' = null }
PS C:\> $ContentType = 'txt'
PS C:\> Set-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret -Expires $Expires -NotBefore $NBF -ContentType $ContentType -Disable $False -Tags $Tags
```

Perintah pertama mengonversi string menjadi string aman menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Secret. Untuk informasi selengkapnya, ketik .`Get-Help
ConvertTo-SecureString`

Perintah berikutnya menentukan atribut kustom untuk tanggal kedaluwarsa, tag, dan tipe konteks, dan menyimpan atribut dalam variabel.

Perintah akhir mengubah nilai rahasia bernama ITSecret dalam kubah kunci bernama Contoso, dengan menggunakan nilai yang ditentukan sebelumnya sebagai variabel.

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

### -Non-fungsikan
Menunjukkan bahwa cmdlet ini menonaktifkan rahasia.

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
Menentukan waktu kedaluwarsa, sebagai objek **DateTime** , untuk rahasia cmdlet ini diperbarui.
Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Untuk informasi selengkapnya, ketik .`Get-Help Get-Date`

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
Menentukan nama rahasia yang akan diubah. Cmdlet ini menyusun nama domain yang sepenuhnya memenuhi syarat (FQDN) rahasia berdasarkan nama yang ditentukan parameter ini, nama kubah kunci, dan lingkungan Anda saat ini.

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
Menentukan waktu, sebagai objek **DateTime** , sebelum rahasia tidak dapat digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** .

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
Menentukan nilai untuk rahasia sebagai objek **SecureString** . Untuk mendapatkan objek **SecureString** , gunakan cmdlet **ConvertTo-SecureString** . Untuk informasi selengkapnya, ketik .`Get-Help
ConvertTo-SecureString`

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
Menentukan nama kubah kunci tempat rahasia ini berada. Cmdlet ini menyusun FQDN kubah kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

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

## CATATAN

## RELATED LINKS

[Get-AzKeyVaultSecret](./Get-AzKeyVaultSecret.md)

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)
