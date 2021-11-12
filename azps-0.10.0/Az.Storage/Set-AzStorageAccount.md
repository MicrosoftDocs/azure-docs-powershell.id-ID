---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 4D7EEDD7-89D4-4B1E-A9A1-B301E759CE72
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/set-azstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Set-AzStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Storage/Storage.Management/help/Set-AzStorageAccount.md
ms.openlocfilehash: 00665fbe6fc2cc0d78ebbfadded419a8b0157644
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427966"
---
# Set-AzStorageAccount

## SYNOPSIS
Mengubah akun Storage Anda.

## SYNTAX

### StorageEncryption (Default)
```
Set-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-SkuName <String>]
 [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>] [-Tag <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-StorageEncryption] [-AssignIdentity]
 [-NetworkRuleSet <PSNetworkRuleSet>] [-UpgradeToStorageV2] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### KeyvaultEncryption
```
Set-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-SkuName <String>]
 [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>] [-Tag <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-KeyvaultEncryption] -KeyName <String> -KeyVersion <String>
 -KeyVaultUri <String> [-AssignIdentity] [-NetworkRuleSet <PSNetworkRuleSet>] [-UpgradeToStorageV2] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageAccount** mengubah akun Azure Storage Anda.
Anda dapat menggunakan cmdlet ini untuk mengubah tipe akun, memperbarui domain pelanggan, atau mengatur tag di akun Storage Anda.

## EXAMPLES

### Contoh 1: Atur tipe akun Storage Anda
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Type "Standard_RAGRS"
```

Perintah ini mengatur tipe Storage ini ke Standard_RAGRS.

### Contoh 2: Mengatur domain kustom untuk akun Storage Anda
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -CustomDomainName "www.contoso.com" -UseSubDomain $True
```

Perintah ini mengatur domain kustom untuk suatu Storage kustom.

### Contoh 3: Mengatur nilai tingkat akses
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -AccessTier Cool
```

Perintah mengatur nilai Tingkat Akses menjadi keren.

### Contoh 4: Setel domain dan tag kustom
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -CustomDomainName "www.domainname.com" -UseSubDomain $true -Tag @{tag0="value0";tag1="value1";tag2="value2"}
```

Perintah mengatur domain dan tag kustom untuk akun Storage tersebut.

### Contoh 5: Set Encryption KeySource to Keyvault
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -AssignIdentity
PS C:\>$account = Get-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount"

PS C:\>$keyVault = New-AzKeyVault -VaultName "MyKeyVault" -ResourceGroupName "MyResourceGroup" -Location "EastUS2"
PS C:\>$key = Add-AzureKeyVaultKey -VaultName "MyKeyVault" -Name "MyKey" -Destination 'Software'
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName "MyKeyVault" -ObjectId $account.Identity.PrincipalId -PermissionsToKeys wrapkey,unwrapkey,get

PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -KeyvaultEncryption -KeyName $key.Name -KeyVersion $key.Version -KeyVaultUri $keyVault.VaultUri
```

Perintah ini mengatur Encryption KeySource dengan Keyvault yang dibuat baru.

### Contoh 6: Set Encryption KeySource to "Microsoft. Storage"
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -StorageEncryption
```

Perintah ini mengatur Encryption KeySource ke "Microsoft. Storage"

### Contoh 7: Mengatur properti NetworkRuleSet dari Storage anda dengan JSON
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -NetworkRuleSet (@{bypass="Logging,Metrics";
    ipRules=(@{IPAddressOrRange="20.11.0.0/16";Action="allow"},
            @{IPAddressOrRange="10.0.0.0/7";Action="allow"});
    virtualNetworkRules=(@{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet1/subnets/subnet1";Action="allow"},
                        @{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet2/subnets/subnet2";Action="allow"});
    defaultAction="allow"})
```

Perintah ini mengatur properti NetworkRuleSet dari Storage lain dengan JSON

### Contoh 8: Dapatkan properti NetworkRuleSet dari Storage, lalu atur ke akun Storage lain
```
PS C:\> $networkRuleSet = (Get-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount").NetworkRuleSet 
PS C:\> Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount2" -NetworkRuleSet $networkRuleSet
```

Perintah pertama ini mendapatkan properti NetworkRuleSet dari Storage, dan perintah kedua mengaturnya ke akun Storage lain 

### Contoh 9: Memutakhirkan akun Storage dengan Jenis "Storage" atau "BlobStorage" ke jenis "StorageV2" Storage lain
```
PS C:\> Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -UpgradeToStorageV2
```

Perintah memutakhirkan akun Storage dengan Jenis "Storage" atau "BlobStorage" ke akun Storage "StorageV2".

## PARAMETERS

### -AccessTier
Menentukan tingkatan akses dari akun Storage yang ditentukan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Hot dan Cool.
Jika Anda mengubah tingkat akses, hal itu mungkin akan mengakibatkan biaya tambahan. Untuk informasi selengkapnya, [lihat Azure Blob Storage: Hot dan cool storage tiers](http://go.microsoft.com/fwlink/?LinkId=786482).
Jika akun Storage memiliki Kind as StorageV2 atau BlobStorage, Anda dapat menentukan parameter *AccessTier.* Jika Storage memiliki Jenis sebagai Storage, jangan tentukan parameter *AccessTier.*

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Hot, Cool

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang

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

### -AssignIdentity
Buat dan tetapkan Identitas akun Storage baru untuk akun Storage ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

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

### -CustomDomainName
Menentukan nama domain kustom.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHttpsTrafficOnly
Menunjukkan apakah akun Storage hanya mengaktifkan lalu lintas HTTPS.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Memaksa perubahan untuk ditulis ke akun Storage tersebut.

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

### -KeyName
Jika menggunakan -KeyvaultEncryption untuk mengaktifkan enkripsi dengan Key Vault, tentukan properti Keyname dengan opsi ini.

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyvaultEncryption
Menunjukkan apakah menggunakan Microsoft KeyVault atau tidak untuk kunci enkripsi ketika menggunakan Storage Service Encryption. Jika KeyName, KeyVersion, dan KeyVaultUri sudah siap, KeySource akan diatur ke Microsoft.Keyvault apakah parameter ini diatur atau tidak. 

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: KeyvaultEncryption
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultUri
Ketika menggunakan Enkripsi Key Vault dengan menentukan parameter -KeyvaultEncryption, gunakan opsi ini untuk menentukan URI ke Key Vault.

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVersion
Ketika menggunakan Enkripsi Key Vault dengan menentukan parameter -KeyvaultEncryption, gunakan opsi ini untuk menentukan URI ke Versi Kunci.

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun Storage diubah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkRuleSet
NetworkRuleSet digunakan untuk menetapkan serangkaian aturan konfigurasi untuk firewall dan jaringan virtual, serta untuk mengatur nilai untuk properti jaringan seperti layanan yang diperbolehkan untuk melewati aturan dan cara menangani permintaan yang tidak cocok dengan salah satu aturan yang ditentukan.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSNetworkRuleSet
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk memodifikasi Storage tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuName
Menentukan nama SKU akun Storage tersebut.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_LRS - Penyimpanan yang berlebihan secara lokal.
- Standard_ZRS - Penyimpanan berlebihan zona.
- Standard_GRS - Penyimpanan geo berulang.
- Standard_RAGRS - Membaca akses yang tidak ada lagi penyimpanan geo.
- Premium_LRS - Premium lokal yang berlebihan.
Anda tidak bisa Standard_ZRS tipe Premium_LRS ke tipe akun lain.
Anda tidak dapat mengubah tipe akun lain Standard_ZRS atau Premium_LRS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType, Type
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEncryption
Menunjukkan apakah menyetel atau tidak mengatur Storage enkripsi akun untuk menggunakan kunci yang dikelola Microsoft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StorageEncryption
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash yang diatur sebagai tag di server. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpgradeToStoragev2
Mutakhirkan Storage akun Anda dari Storage atau BlobStorage ke StorageV2.

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

### -UseSubDomain
Menunjukkan apakah akan mengaktifkan validasi CName tidak langsung.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## CATATAN

## RELATED LINKS

[Get-AzStorageAccount](./Get-AzStorageAccount.md)

[New-AzStorageAccount](./New-AzStorageAccount.md)

[Remove-AzStorageAccount](./Remove-AzStorageAccount.md)
