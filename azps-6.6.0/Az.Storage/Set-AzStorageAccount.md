---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 4D7EEDD7-89D4-4B1E-A9A1-B301E759CE72
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageAccount.md
ms.openlocfilehash: 881b3c513c9a716b7b62ece4043de24bc4264397
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141946599"
---
# Set-AzStorageAccount

## SYNOPSIS
Mengubah akun Storage.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/set-azstorageaccount) untuk informasi terbaru.

## SYNTAX

### StorageEncryption (Default)
```
Set-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-SkuName <String>]
 [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>] [-Tag <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-StorageEncryption] [-AssignIdentity] [-UserAssignedIdentityId <String>]
 [-KeyVaultUserAssignedIdentityId <String>] [-IdentityType <String>] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-UpgradeToStorageV2] [-EnableAzureActiveDirectoryDomainServicesForFile <Boolean>] [-EnableLargeFileShare]
 [-PublishMicrosoftEndpoint <Boolean>] [-PublishInternetEndpoint <Boolean>] [-AllowBlobPublicAccess <Boolean>]
 [-MinimumTlsVersion <String>] [-AllowSharedKeyAccess <Boolean>] [-SasExpirationPeriod <TimeSpan>]
 [-KeyExpirationPeriodInDay <Int32>] [-AllowCrossTenantReplication <Boolean>]
 [-DefaultSharePermission <String>] [-PublicNetworkAccess <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### KeyvaultEncryption
```
Set-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-SkuName <String>]
 [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>] [-Tag <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-KeyvaultEncryption] -KeyName <String> [-KeyVersion <String>]
 -KeyVaultUri <String> [-AssignIdentity] [-UserAssignedIdentityId <String>]
 [-KeyVaultUserAssignedIdentityId <String>] [-IdentityType <String>] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-UpgradeToStorageV2] [-EnableAzureActiveDirectoryDomainServicesForFile <Boolean>] [-EnableLargeFileShare]
 [-PublishMicrosoftEndpoint <Boolean>] [-PublishInternetEndpoint <Boolean>] [-AllowBlobPublicAccess <Boolean>]
 [-MinimumTlsVersion <String>] [-AllowSharedKeyAccess <Boolean>] [-SasExpirationPeriod <TimeSpan>]
 [-KeyExpirationPeriodInDay <Int32>] [-AllowCrossTenantReplication <Boolean>]
 [-DefaultSharePermission <String>] [-PublicNetworkAccess <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ActiveDirectoryDomainServicesForFile
```
Set-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Force] [-SkuName <String>]
 [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>] [-Tag <Hashtable>]
 [-EnableHttpsTrafficOnly <Boolean>] [-AssignIdentity] [-UserAssignedIdentityId <String>]
 [-KeyVaultUserAssignedIdentityId <String>] [-IdentityType <String>] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-UpgradeToStorageV2] [-EnableLargeFileShare] [-PublishMicrosoftEndpoint <Boolean>]
 [-PublishInternetEndpoint <Boolean>] -EnableActiveDirectoryDomainServicesForFile <Boolean>
 [-ActiveDirectoryDomainName <String>] [-ActiveDirectoryNetBiosDomainName <String>]
 [-ActiveDirectoryForestName <String>] [-ActiveDirectoryDomainGuid <String>]
 [-ActiveDirectoryDomainSid <String>] [-ActiveDirectoryAzureStorageSid <String>]
 [-AllowBlobPublicAccess <Boolean>] [-MinimumTlsVersion <String>] [-AllowSharedKeyAccess <Boolean>]
 [-SasExpirationPeriod <TimeSpan>] [-KeyExpirationPeriodInDay <Int32>] [-AllowCrossTenantReplication <Boolean>]
 [-DefaultSharePermission <String>] [-PublicNetworkAccess <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageAccount** mengubah akun Azure Storage.
Anda dapat menggunakan cmdlet ini untuk mengubah tipe akun, memperbarui domain pelanggan, atau mengatur tag pada akun Storage.

## EXAMPLES

### Contoh 1: Mengatur tipe akun Storage
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Type "Standard_RAGRS"
```

Perintah ini mengatur tipe akun Storage ke Standard_RAGRS.

### Contoh 2: Mengatur domain kustom untuk akun Storage
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -CustomDomainName "www.contoso.com" -UseSubDomain $True
```

Perintah ini mengatur domain kustom untuk akun Storage.

### Contoh 3: Mengatur nilai tingkat akses
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -AccessTier Cool
```

Perintah mengatur nilai Tingkat Access agar dingin.

### Contoh 4: Mengatur domain dan tag kustom
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -CustomDomainName "www.domainname.com" -UseSubDomain $true -Tag @{tag0="value0";tag1="value1";tag2="value2"}
```

Perintah mengatur domain dan tag kustom untuk akun Storage.

### Contoh 5: Atur Encryption KeySource ke Keyvault
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -AssignIdentity
PS C:\>$account = Get-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount"

PS C:\>$keyVault = New-AzKeyVault -VaultName "MyKeyVault" -ResourceGroupName "MyResourceGroup" -Location "EastUS2"
PS C:\>$key = Add-AzKeyVaultKey -VaultName "MyKeyVault" -Name "MyKey" -Destination 'Software'
PS C:\>Set-AzKeyVaultAccessPolicy -VaultName "MyKeyVault" -ObjectId $account.Identity.PrincipalId -PermissionsToKeys wrapkey,unwrapkey,get

# In case to enable key auto rotation, don't set KeyVersion
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -KeyvaultEncryption -KeyName $key.Name -KeyVersion $key.Version -KeyVaultUri $keyVault.VaultUri

# In case to enable key auto rotation after set keyvault proeprites with KeyVersion, can update account by set KeyVersion to empty
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -KeyvaultEncryption -KeyName $key.Name -KeyVersion "" -KeyVaultUri $keyVault.VaultUri
```

Perintah ini mengatur Encryption KeySource dengan Keyvault yang baru dibuat.
Jika ingin mengaktifkan rotasi otomatis kunci, jangan atur keyversion saat mengatur properti Keyvault untuk pertama kalinya, atau bersihkan dengan mengatur properti keyvault lagi dengan keyversion sebagai kosong.

### Contoh 6: Atur Encryption KeySource ke "Microsoft. Storage"
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -StorageEncryption
```

Perintah ini mengatur Encryption KeySource ke "Microsoft. Storage"

### Contoh 7: Mengatur properti NetworkRuleSet dari akun Storage dengan JSON
```
PS C:\>Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -NetworkRuleSet (@{bypass="Logging,Metrics";
    ipRules=(@{IPAddressOrRange="20.11.0.0/16";Action="allow"},
            @{IPAddressOrRange="10.0.0.0/7";Action="allow"});
    virtualNetworkRules=(@{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet1/subnets/subnet1";Action="allow"},
                        @{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet2/subnets/subnet2";Action="allow"});
    defaultAction="allow"})
```

Perintah ini mengatur properti NetworkRuleSet dari akun Storage dengan JSON

### Contoh 8: Dapatkan properti NetworkRuleSet dari akun Storage, dan atur ke akun Storage lain
```
PS C:\> $networkRuleSet = (Get-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount").NetworkRuleSet 
PS C:\> Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount2" -NetworkRuleSet $networkRuleSet
```

Perintah pertama ini mendapatkan properti NetworkRuleSet dari akun Storage, dan perintah kedua mengaturnya ke akun Storage lain 

### Contoh 9: Memutakhirkan akun Storage dengan Kind "Storage" atau "BlobStorage" ke akun Storage jenis "StorageV2"
```
PS C:\> Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -UpgradeToStorageV2
```

Perintah memutakhirkan akun Storage dengan kind "Storage" atau "BlobStorage" ke akun Storage jenis "StorageV2".

### Contoh 10: Memperbarui akun Storage dengan mengaktifkan Autentikasi DS Azure Files AAD dan mengatur DefaultSharePermission.
```
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -EnableAzureActiveDirectoryDomainServicesForFile $true -DefaultSharePermission StorageFileDataSmbShareOwner

PS C:\> $account.AzureFilesIdentityBasedAuth

DirectoryServiceOptions ActiveDirectoryProperties                                                      DefaultSharePermission      
----------------------- -------------------------                                                      ----------------------      
AADDS                   Microsoft.Azure.Commands.Management.Storage.Models.PSActiveDirectoryProperties StorageFileDataSmbShareOwner
```

Perintah memperbarui akun Storage dengan mengaktifkan Autentikasi DS Azure Files AAD.

### Contoh 11: Perbarui akun Storage dengan mengaktifkan Autentikasi Layanan Domain Direktori Aktif File, lalu perlihatkan pengaturan autentikasi Berbasis Identitas File
```
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -EnableActiveDirectoryDomainServicesForFile $true `
        -ActiveDirectoryDomainName "mydomain.com" `
        -ActiveDirectoryNetBiosDomainName "mydomain.com" `
        -ActiveDirectoryForestName "mydomain.com" `
        -ActiveDirectoryDomainGuid "12345678-1234-1234-1234-123456789012" `
        -ActiveDirectoryDomainSid "S-1-5-21-1234567890-1234567890-1234567890" `
        -ActiveDirectoryAzureStorageSid "S-1-5-21-1234567890-1234567890-1234567890-1234"
        
PS C:\> $account.AzureFilesIdentityBasedAuth.DirectoryServiceOptions
AD

PS C:\> $account.AzureFilesIdentityBasedAuth.ActiveDirectoryProperties

DomainName        : mydomain.com
NetBiosDomainName : mydomain.com
ForestName        : mydomain.com
DomainGuid        : 12345678-1234-1234-1234-123456789012
DomainSid         : S-1-5-21-1234567890-1234567890-1234567890
AzureStorageSid   : S-1-5-21-1234567890-1234567890-1234567890-1234
```

Perintah memperbarui akun Storage dengan mengaktifkan Azure Files Autentikasi Layanan Domain Direktori Aktif, lalu memperlihatkan pengaturan autentikasi Berbasis Identitas File

### Contoh 12: Atur MinimumTlsVersion, AllowBlobPublicAccess dan AllowSharedKeyAccess
```
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -MinimumTlsVersion TLS1_1 -AllowBlobPublicAccess $false -AllowSharedKeyAccess $true

PS C:\> $account.MinimumTlsVersion
TLS1_1

PS C:\> $account.AllowBlobPublicAccess
False

PS C:\> $a.AllowSharedKeyAccess
True
```

Perintah mengatur MinimumTlsVersion, AllowBlobPublicAccess dan AllowSharedKeyAccess, lalu memperlihatkan 3 properti akun 

### Contoh 13: Memperbarui akun Storage dengan pengaturan PeruteanPreferensi
```powershell
PS C:\>$account = Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -PublishMicrosoftEndpoint $false -PublishInternetEndpoint $true -RoutingChoice InternetRouting

PS C:\>$account.RoutingPreference

RoutingChoice   PublishMicrosoftEndpoints PublishInternetEndpoints
-------------   ------------------------- ------------------------
InternetRouting                     False                     True

PS C:\>$account.PrimaryEndpoints

Blob               : https://mystorageaccount.blob.core.windows.net/
Queue              : https://mystorageaccount.queue.core.windows.net/
Table              : https://mystorageaccount.table.core.windows.net/
File               : https://mystorageaccount.file.core.windows.net/
Web                : https://mystorageaccount.z2.web.core.windows.net/
Dfs                : https://mystorageaccount.dfs.core.windows.net/
MicrosoftEndpoints : 
InternetEndpoints  : {"Blob":"https://mystorageaccount-internetrouting.blob.core.windows.net/","File":"https://mystorageaccount-internetrouting.file.core.windows.net/","Web":"https://mystorageaccount-internetrouting.z2.web.core.windows.net/","Dfs":"https://w
                     eirp3-internetrouting.dfs.core.windows.net/"}
```

Perintah ini memperbarui akun Storage dengan pengaturan RoutingPreference: PublishMicrosoftEndpoint sebagai false, PublishInternetEndpoint sebagai true, dan RoutingChoice sebagai MicrosoftRouting.

### Contoh 14: Memperbarui akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod
```powershell
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -KeyExpirationPeriodInDay 5 -SasExpirationPeriod "1.12:05:06" -EnableHttpsTrafficOnly $true

PS C:\> $$account.KeyPolicy.KeyExpirationPeriodInDays
5

PS C:\> $$account.SasPolicy.SasExpirationPeriod
1.12:05:06
```

Perintah ini memperbarui akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod, lalu menampilkan properti terkait akun yang diperbarui.

### Contoh 15: Memperbarui akun Storage ke enkripsi Keyvault, dan mengakses Keyvault dengan identitas yang ditetapkan pengguna
```powershell
# Create KeyVault (no need if using exist keyvault)
PS C:\> $keyVault = New-AzKeyVault -VaultName $keyvaultName -ResourceGroupName $resourceGroupName -Location eastus2euap -EnablePurgeProtection
PS C:\> $key = Add-AzKeyVaultKey -VaultName $keyvaultName -Name $keyname -Destination 'Software'

# create user assigned identity and grant access to keyvault (no need if using exist user assigned identity)
PS C:\> $userId = New-AzUserAssignedIdentity -ResourceGroupName $resourceGroupName -Name $userIdName
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName $keyvaultName -ResourceGroupName $resourceGroupName -ObjectId $userId.PrincipalId -PermissionsToKeys get,wrapkey,unwrapkey -BypassObjectIdValidation
PS C:\> $useridentityId= $userId.Id

# Update Storage account with Keyvault encryption and access Keyvault with user assigned identity, then show properties
PS C:\> $account = Update-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName `
                -IdentityType UserAssigned  -UserAssignedIdentityId $useridentityId  `
                -KeyVaultUri $keyVault.VaultUri -KeyName $keyname -KeyVaultUserAssignedIdentityId $useridentityId

PS C:\> $account.Encryption.EncryptionIdentity.EncryptionUserAssignedIdentity
/subscriptions/{subscription-id}/resourceGroups/myresourcegroup/providers/Microsoft.ManagedIdentity/userAssignedIdentities/myuserid

PS C:\> $account.Encryption.KeyVaultProperties

KeyName                       : wrappingKey
KeyVersion                    : 
KeyVaultUri                   : https://mykeyvault.vault.azure.net:443
CurrentVersionedKeyIdentifier : https://mykeyvault.vault.azure.net/keys/wrappingKey/8e74036e0d534e58b3bd84b319e31d8f
LastKeyRotationTimestamp      : 4/12/2021 8:17:57 AM
```

Perintah ini pertama-tama membuat keyvault dan identitas yang ditetapkan pengguna, lalu memperbarui akun penyimpanan dengan enkripsi keyvault, keyvault akses penyimpanan dengan identitas yang ditetapkan pengguna.

### Contoh 16: Memperbarui akun Storage keyvault yang dienkripsi, dari akses Keyvault dengan identitas yang ditetapkan pengguna, untuk mengakses Keyvault dengan identitas sistem yang ditetapkan
```powershell
# Assign System identity to the account, and give the system assigned identity acces to the keyvault
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName  -IdentityType SystemAssignedUserAssigned
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName $keyvaultName -ResourceGroupName $resourceGroupName -ObjectId $account.Identity.PrincipalId -PermissionsToKeys get,wrapkey,unwrapkey -BypassObjectIdValidation

# Update account from access Keyvault with user assigned identity to access Keyvault with system assigned identity
$account = Set-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName -IdentityType SystemAssignedUserAssigned -KeyName $keyname -KeyVaultUri $keyvaultUri -KeyVaultUserAssignedIdentityId ""

# EncryptionUserAssignedIdentity is empty, so the account access keyvault with system assigned identity
PS C:\> $account.Encryption.EncryptionIdentity

EncryptionUserAssignedIdentity                                                                                                                 
------------------------------ 

PS C:\> $account.Encryption.KeyVaultProperties

KeyName                       : wrappingKey
KeyVersion                    : 
KeyVaultUri                   : https://mykeyvault.vault.azure.net:443
CurrentVersionedKeyIdentifier : https://mykeyvault.vault.azure.net/keys/wrappingKey/8e74036e0d534e58b3bd84b319e31d8f
LastKeyRotationTimestamp      : 4/12/2021 8:17:57 AM
```

Perintah ini terlebih dahulu menetapkan Identitas sistem ke akun, dan memberi sistem akses identitas yang ditetapkan ke keyvault; lalu perbarui akun Storage untuk mengakses Keyvault dengan identitas sistem yang ditetapkan.

### Contoh 17: Memperbarui keyvault dan identitas yang ditetapkan pengguna untuk mengakses keyvault
```powershell
# Update to another user assigned identity
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName -IdentityType SystemAssignedUserAssigned -UserAssignedIdentityId $useridentity2 -KeyVaultUserAssignedIdentityId $useridentity2

# Update to encrypt with another keyvault
$account = Set-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName -KeyVaultUri $keyvaultUri2 -KeyName $keyname2 -KeyVersion $keyversion2
```

Perintah ini terlebih dahulu memperbarui identitas yang ditetapkan pengguna untuk mengakses keyvault, lalu memperbarui keyvault untuk enkripsi.
Untuk memperbarui Keyvault dan identitas yang ditetapkan pengguna, kami memerlukan pembaruan dengan 2 langkah di atas. 

### Contoh 18: Memperbarui akun Storage dengan AllowCrossTenantReplication
```powershell
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -AllowCrossTenantReplication $false -EnableHttpsTrafficOnly $true

PS C:\> $account.AllowCrossTenantReplication
False
```

Perintah ini memperbarui akun Storage dengan mengatur AllowCrossTenantReplication ke false, lalu memperlihatkan properti akun terkait yang diperbarui.

### Contoh 18: Memperbarui akun Storage dengan mengaktifkan PublicNetworkAccess
```powershell
PS C:\> $account = Set-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -PublicNetworkAccess Enabled

PS C:\> $account.PublicNetworkAccess
Enabled
```

Perintah ini memperbarui akun Storage dengan mengatur PublicNetworkAccess sebagai diaktifkan.

## PARAMETERS

### -AccessTier
Menentukan tingkat akses akun Storage yang diubah cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Panas dan Keren.
Jika Anda mengubah tingkat akses, hal ini dapat mengakibatkan biaya tambahan. Untuk informasi selengkapnya, lihat [Azure Blob Storage: Tingkat penyimpanan yang panas dan keren](http://go.microsoft.com/fwlink/?LinkId=786482).
Jika akun Storage memiliki Kind as StorageV2 atau BlobStorage, Anda dapat menentukan parameter *AccessTier*. Jika akun Storage memiliki Kind as Storage, jangan tentukan parameter *AccessTier*.

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

### -ActiveDirectoryAzureStorageSid
Menentukan pengidentifikasi keamanan (SID) untuk Azure Storage. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryDomainGuid
Menentukan domain GUID. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryDomainName
Menentukan domain utama yang menjadi otoritatif server DNS AD. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryDomainSid
Menentukan pengidentifikasi keamanan (SID). Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryForestName
Menentukan hutan Direktori Aktif untuk didapatkan. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryNetBiosDomainName
Menentukan nama domain NetBIOS. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

```yaml
Type: System.String
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowBlobPublicAccess
Mengizinkan atau tidak mengizinkan akses publik ke semua blob atau kontainer dalam akun penyimpanan.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowCrossTenantReplication
Mendapatkan atau mengatur izin atau tidak memperbolehkan replikasi objek penyewa AAD silang. Interpretasi default berlaku untuk properti ini.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSharedKeyAccess
Menunjukkan apakah akun penyimpanan mengizinkan permintaan untuk diotorisasi dengan kunci akses akun melalui Kunci Bersama. Jika false, semua permintaan, termasuk tanda tangan akses bersama, harus diotorisasi dengan Azure Active Directory (Azure AD). Nilai defaultnya adalah null, yang setara dengan true.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Menjalankan cmdlet di latar belakang

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
Buat dan tetapkan identitas akun Storage baru untuk akun Storage ini untuk digunakan dengan layanan manajemen utama seperti Azure KeyVault.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultSharePermission
Izin berbagi default untuk pengguna yang menggunakan autentikasi Kerberos jika peran RBAC tidak ditetapkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: None, StorageFileDataSmbShareContributor, StorageFileDataSmbShareReader, StorageFileDataSmbShareElevatedContributor

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableActiveDirectoryDomainServicesForFile
Aktifkan Azure Files Autentikasi Layanan Domain Direktori Aktif untuk akun penyimpanan.

```yaml
Type: System.Boolean
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAzureActiveDirectoryDomainServicesForFile
Aktifkan Azure Files Autentikasi Layanan Domain Direktori Aktif untuk akun penyimpanan.

```yaml
Type: System.Boolean
Parameter Sets: StorageEncryption, KeyvaultEncryption
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHttpsTrafficOnly
Menunjukkan apakah akun Storage hanya mengaktifkan lalu lintas HTTPS atau tidak.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLargeFileShare
Menunjukkan apakah akun penyimpanan dapat mendukung berbagi file berukuran besar dengan kapasitas lebih dari 5 TiB atau tidak. Setelah akun diaktifkan, fitur tidak dapat dinonaktifkan. Saat ini hanya didukung untuk jenis replikasi LRS dan ZRS, maka konversi akun ke akun geo-redundant tidak akan dimungkinkan. Pelajari selengkapnya di https://go.microsoft.com/fwlink/?linkid=2086047

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

### -Paksa
Memaksa perubahan ditulis ke akun Storage.

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

### -IdentityType
Atur tipe Identitas Akun Storage baru, idenetitas digunakan dengan layanan manajemen utama seperti Azure KeyVault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssignedUserAssigned, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyExpirationPeriodInDay
Periode kunci kedaluwarsa akun ini, akurat hingga hari.

```yaml
Type: System.Int32
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
Menunjukkan apakah Menggunakan Microsoft KeyVault untuk kunci enkripsi atau tidak saat menggunakan Enkripsi Layanan Storage. Jika KeyName, KeyVersion, dan KeyVaultUri sudah siap, KeySource akan diatur ke Microsoft.Keyvault apakah parameter ini diatur atau tidak. 

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
Ketika menggunakan enkripsi Key Vault dengan menentukan parameter -KeyvaultEncryption, gunakan opsi ini untuk menentukan URI ke Key Vault.

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

### -KeyVaultUserAssignedIdentityId
Set resource id for user assigned Identity used to access Azure KeyVault of Storage Account Encryption, the id must in the storage account's UserAssignIdentityId.

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

### -KeyVersion
Saat menggunakan enkripsi Key Vault dengan menentukan parameter -KeyvaultEncryption, gunakan opsi ini untuk menentukan URI ke Versi Kunci.

```yaml
Type: System.String
Parameter Sets: KeyvaultEncryption
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTlsVersion
Versi TLS minimum yang akan diizinkan berdasarkan permintaan penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: TLS1_0, TLS1_1, TLS1_2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun Storage untuk diubah.

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
NetworkRuleSet digunakan untuk menentukan sekumpulan aturan konfigurasi untuk firewall dan jaringan virtual, serta untuk mengatur nilai untuk properti jaringan seperti layanan yang diizinkan untuk melewati aturan dan cara menangani permintaan yang tidak cocok dengan aturan yang ditentukan.

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

### -PublicNetworkAccess
Memperbolehkan atau tidak memperbolehkan akses jaringan publik ke Storage Akun.Nilai yang memungkinkan meliputi: 'Diaktifkan', 'Dinonaktifkan'.

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

### -PublishInternetEndpoint
Menunjukkan apakah titik akhir penyimpanan perutean internet akan diterbitkan

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublishMicrosoftEndpoint
Menunjukkan apakah titik akhir penyimpanan perutean microsoft akan diterbitkan

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk mengubah akun Storage.

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

### -RoutingChoice
Pilihan Perutean menentukan jenis perutean jaringan yang dipilih oleh pengguna. Nilai yang memungkinkan termasuk: 'MicrosoftRouting', 'InternetRouting'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: MicrosoftRouting, InternetRouting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasExpirationPeriod
Periode kedaluwarsa SAS dari akun ini, adalah rentang waktu dan akurat untuk detik.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Menentukan nama SKU akun Storage.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_LRS - Penyimpanan lokal yang berlebihan.
- Standard_ZRS - Penyimpanan zona berlebihan.
- Standard_GRS - Penyimpanan geo-redundan.
- Standard_RAGRS - Membaca penyimpanan geo-redundan akses.
- Premium_LRS - Premium penyimpanan lokal yang berlebihan.
- Standard_GZRS - Penyimpanan berlemak zona geo-redundan.
- Standard_RAGZRS - Membaca akses geo-redundan zona-redundan penyimpanan.
Anda tidak dapat mengubah tipe Standard_ZRS dan Premium_LRS ke tipe akun lain.
Anda tidak dapat mengubah tipe akun lain ke Standard_ZRS atau Premium_LRS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType, Type
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS, Standard_GZRS, Standard_RAGZRS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEncryption
Menunjukkan apakah enkripsi akun Storage diatur atau tidak untuk menggunakan kunci yang dikelola Microsoft.

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

### -UpgradeToStorageV2
Mutakhirkan akun Storage Jenis dari Storage atau BlobStorage ke StorageV2.

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

### -UserAssignedIdentityId
Atur id sumber daya untuk pengguna akun Storage baru yang ditetapkan Identitas, identitas akan digunakan dengan layanan manajemen utama seperti Azure KeyVault.

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

### -UseSubDomain
Menunjukkan apakah mengaktifkan validasi CName tidak langsung.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## CATATAN

## RELATED LINKS

[Get-AzStorageAccount](./Get-AzStorageAccount.md)

[New-AzStorageAccount](./New-AzStorageAccount.md)

[Hapus-AzStorageAccount](./Remove-AzStorageAccount.md)
