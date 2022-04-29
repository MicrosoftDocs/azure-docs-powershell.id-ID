---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultsecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultSecret.md
ms.openlocfilehash: 2524f9f0e748cdec0f5f5c96281c066665bdd517
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144247821"
---
# Update-AzKeyVaultSecret

## SYNOPSIS
Memperbarui atribut rahasia di brankas kunci.

## SYNTAX

### Default (Default)
```
Update-AzKeyVaultSecret [-VaultName] <String> [-Name] <String> [[-Version] <String>] [-Enable <Boolean>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Update-AzKeyVaultSecret [-InputObject] <PSKeyVaultSecretIdentityItem> [[-Version] <String>] [-Enable <Boolean>]
 [-Expires <DateTime>] [-NotBefore <DateTime>] [-ContentType <String>] [-Tag <Hashtable>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzKeyVaultSecret** memperbarui atribut rahasia yang dapat diedit di brankas kunci.

## EXAMPLES

### Contoh 1: Mengubah atribut rahasia
```powershell
$Expires = (Get-Date).AddYears(2).ToUniversalTime()
$Nbf = (Get-Date).ToUniversalTime()
$Tags = @{ 'Severity' = 'medium'; 'HR' = 'true'}
$ContentType= 'xml'
Update-AzKeyVaultSecret -VaultName 'ContosoVault' -Name 'HR' -Expires $Expires -NotBefore $Nbf -ContentType $ContentType -Enable $True -Tag $Tags -PassThru
```

```output
Vault Name   : ContosoVault
Name         : HR
Version      : d476edfcd3544017a03bc49c1f3abec0
Id           : https://ContosoVault.vault.azure.net:443/secrets/HR/d476edfcd3544017a03bc49c1f3abec0
Enabled      : True
Expires      : 5/25/2020 8:01:58 PM
Not Before   : 5/25/2018 8:02:02 PM
Created      : 4/11/2018 11:45:06 PM
Updated      : 5/25/2018 8:02:45 PM
Content Type : xml
Tags         : Name      Value
               Severity  medium
               HR        true
```

Empat perintah pertama menentukan atribut untuk tanggal kedaluwarsa, tanggal NotBefore, tag, dan jenis konteks, dan menyimpan atribut dalam variabel.
Perintah akhir memodifikasi atribut untuk rahasia bernama HR di brankas kunci bernama ContosoVault, menggunakan variabel yang disimpan.

### Contoh 2: Menghapus tag dan jenis konten untuk rahasia
```powershell
Update-AzKeyVaultSecret -VaultName 'ContosoVault' -Name 'HR' -Version '9EEA45C6EE50490B9C3176A80AC1A0DF' -ContentType '' -Tag @{}
```

Perintah ini menghapus tag dan jenis konten untuk versi rahasia yang ditentukan bernama HR di brankas kunci bernama Contoso.

### Contoh 3: Nonaktifkan versi rahasia saat ini yang namanya dimulai dengan IT
```powershell
$Vault = 'ContosoVault'
$Prefix = 'IT'
Get-AzKeyVaultSecret $Vault | Where-Object {$_.Name -like $Prefix + '*'} | Update-AzKeyVaultSecret -Enable $False
```

Perintah pertama menyimpan nilai string Contoso dalam variabel $Vault.
Perintah kedua menyimpan nilai string IT dalam variabel $Prefix.
Perintah ketiga menggunakan cmdlet Get-AzKeyVaultSecret untuk mendapatkan rahasia di brankas kunci yang ditentukan, lalu meneruskan rahasia tersebut ke cmdlet **Where-Object** . Cmdlet **Where-Object** memfilter rahasia untuk nama yang dimulai dengan karakter IT. Perintah menyalurkan rahasia yang cocok dengan filter ke cmdlet Update-AzKeyVaultSecret, yang menonaktifkannya.

### Contoh 4: Mengatur ContentType untuk semua versi rahasia
```powershell
$VaultName = 'ContosoVault'
$Name = 'HR'
$ContentType = 'xml'
Get-AzKeyVaultKey -VaultName $VaultName -Name $Name -IncludeVersions | Update-AzKeyVaultSecret -ContentType $ContentType
```

Tiga perintah pertama menentukan variabel string yang akan digunakan untuk parameter *VaultName*, *Name*, dan *ContentType* . Perintah keempat menggunakan cmdlet Get-AzKeyVaultKey untuk mendapatkan kunci yang ditentukan, dan menyalurkan kunci ke cmdlet Update-AzKeyVaultSecret untuk mengatur jenis kontennya ke XML.

## PARAMETERS

### -ContentType
Jenis konten rahasia.
Jika tidak ditentukan, nilai yang ada dari jenis konten rahasia tetap tidak berubah.
Hapus nilai tipe konten yang ada dengan menentukan string kosong.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Aktifkan
Jika ada, aktifkan rahasia jika nilainya benar.
Nonaktifkan rahasia jika nilainya salah.
Jika tidak ditentukan, nilai yang ada dari status rahasia yang diaktifkan/dinonaktifkan tetap tidak berubah.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kedaluwarsa
Waktu kedaluwarsa rahasia dalam waktu UTC.
Jika tidak ditentukan, nilai yang ada dari waktu kedaluwarsa rahasia tetap tidak berubah.

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
Nama rahasia.
Cmdlet membangun FQDN rahasia dari nama brankas, lingkungan dan nama rahasia yang saat ini dipilih.

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
Waktu UTC sebelum rahasia mana yang tidak dapat digunakan.
Jika tidak ditentukan, nilai yang ada dari atribut NotBefore rahasia tetap tidak berubah.

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

### -PassThru
Cmdlet tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, kembalikan objek Rahasia.

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

### -Tag
Hashtable yang mewakili tag rahasia.
Jika tidak ditentukan, tag rahasia yang ada tetap tidak berubah.
Hapus tag dengan menentukan Hashtable kosong.

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
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

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

### -Versi
Versi rahasia.
Cmdlet membangun FQDN rahasia dari nama vault, lingkungan yang saat ini dipilih, nama rahasia, dan versi rahasia.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SecretVersion

Required: False
Position: 2
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
