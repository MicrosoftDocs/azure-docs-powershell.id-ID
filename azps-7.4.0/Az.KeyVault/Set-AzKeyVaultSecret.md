---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
ms.assetid: 9FC72DE9-46BB-4CB5-9880-F53756DBE012
online version: https://docs.microsoft.com/powershell/module/az.keyvault/set-azkeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultSecret.md
ms.openlocfilehash: d6cf0d443e6dd41af4e7aae2c1905c2f3a232217
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144656030"
---
# Atur-AzKeyVaultSecret

## SYNOPSIS
Membuat atau memperbarui rahasia di brankas kunci.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/set-azkeyvaultsecret) untuk informasi terbaru.

## SYNTAX

### Default (Default)
```
Set-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [-SecretValue] <SecureString> [-Disable]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Set-AzKeyVaultSecret [-InputObject] <PSKeyVaultSecretIdentityItem> [-SecretValue] <SecureString> [-Disable]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzKeyVaultSecret** membuat atau memperbarui rahasia di brankas kunci di Azure Key Vault. Jika rahasia tidak ada, cmdlet ini membuatnya. Jika rahasia sudah ada, cmdlet ini membuat versi baru rahasia tersebut.

## EXAMPLES

### Contoh 1: Mengubah nilai rahasia menggunakan atribut default
```powershell
$Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
Set-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret
```

```output
Vault Name   : Contoso
Name         : ITSecret
Version      : 8b5c0cb0326e4350bd78200fac932b51
Id           : https://contoso.vault.azure.net:443/secrets/ITSecret/8b5c0cb0326e4350bd78200fac932b51
Enabled      : True
Expires      :
Not Before   :
Created      : 5/25/2018 6:39:30 PM
Updated      : 5/25/2018 6:39:30 PM
Content Type :
Tags         :
```

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Secret. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString`.
Perintah kedua memodifikasi nilai rahasia bernama ITSecret di brankas kunci bernama Contoso. Nilai rahasia menjadi nilai yang disimpan dalam $Secret.

### Contoh 2: Mengubah nilai rahasia menggunakan atribut kustom
```powershell
$Secret = ConvertTo-SecureString -String 'Password' -AsPlainText -Force
$Expires = (Get-Date).AddYears(2).ToUniversalTime()
$NBF =(Get-Date).ToUniversalTime()
$Tags = @{ 'Severity' = 'medium'; 'IT' = 'true'}
$ContentType = 'txt'
Set-AzKeyVaultSecret -VaultName 'Contoso' -Name 'ITSecret' -SecretValue $Secret -Expires $Expires -NotBefore $NBF -ContentType $ContentType -Disable -Tags $Tags
```

```output
Vault Name   : Contoso
Name         : ITSecret
Version      : a2c150be3ea24dd6b8286986e6364851
Id           : https://contoso.vault.azure.net:443/secrets/ITSecret/a2c150be3ea24dd6b8286986e6364851
Enabled      : False
Expires      : 5/25/2020 6:40:00 PM
Not Before   : 5/25/2018 6:40:05 PM
Created      : 5/25/2018 6:41:22 PM
Updated      : 5/25/2018 6:41:22 PM
Content Type : txt
Tags         : Name      Value
               Severity  medium
               IT        true
```

Perintah pertama mengonversi string menjadi string aman dengan menggunakan cmdlet **ConvertTo-SecureString** , lalu menyimpan string tersebut dalam variabel $Secret. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString`.
Perintah berikutnya menentukan atribut kustom untuk tanggal kedaluwarsa, tag, dan jenis konteks, dan menyimpan atribut dalam variabel.
Perintah akhir memodifikasi nilai rahasia bernama ITSecret di brankas kunci bernama Contoso, dengan menggunakan nilai yang ditentukan sebelumnya sebagai variabel.

## PARAMETERS

### -ContentType
Menentukan tipe isi rahasia.
Untuk menghapus tipe konten yang ada, tentukan string kosong.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonaktifkan
Menunjukkan bahwa cmdlet ini menonaktifkan rahasia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kedaluwarsa
Menentukan waktu kedaluwarsa, sebagai objek **DateTime** , untuk rahasia yang diperbarui cmdlet ini.
Parameter ini menggunakan Waktu Universal Terkoordinasi (UTC). Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** . Untuk informasi selengkapnya, ketik `Get-Help Get-Date`.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek rahasia

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Menentukan nama rahasia yang akan diubah. Cmdlet ini membangun nama domain yang sepenuhnya memenuhi syarat (FQDN) dari rahasia berdasarkan nama yang ditentukan parameter ini, nama brankas kunci, dan lingkungan Anda saat ini.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: SecretName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotBefore
Menentukan waktu, sebagai objek **DateTime** , yang sebelumnya rahasianya tidak dapat digunakan. Parameter ini menggunakan UTC. Untuk mendapatkan objek **DateTime** , gunakan cmdlet **Get-Date** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretValue
Menentukan nilai untuk rahasia sebagai objek **SecureString** . Untuk mendapatkan objek **SecureString** , gunakan cmdlet **ConvertTo-SecureString** . Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString`.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Menentukan nama brankas kunci tempat rahasia ini berada. Cmdlet ini membangun FQDN dari brankas kunci berdasarkan nama yang ditentukan parameter ini dan lingkungan Anda saat ini.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecretIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecret

## NOTES

## RELATED LINKS

[Get-AzKeyVaultSecret](./Get-AzKeyVaultSecret.md)

[Remove-AzKeyVaultSecret](./Remove-AzKeyVaultSecret.md)
