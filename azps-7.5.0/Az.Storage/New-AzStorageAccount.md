---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A3DA1205-B8FB-4B4C-9C40-AD303D038EDF
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccount.md
ms.openlocfilehash: 71e2e38360a9fff7781b5a0bafb8099fc3dfd17f
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144242067"
---
# New-AzStorageAccount

## SYNOPSIS
Membuat Akun penyimpanan.

## SYNTAX

### AzureActiveDirectoryDomainServicesForFile (Default)
```
New-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String> [-Location] <String>
 [-Kind <String>] [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>]
 [-Tag <Hashtable>] [-EnableHttpsTrafficOnly <Boolean>] [-AssignIdentity] [-UserAssignedIdentityId <String>]
 [-IdentityType <String>] [-KeyVaultUserAssignedIdentityId <String>] [-KeyName <String>] [-KeyVersion <String>]
 [-KeyVaultUri <String>] [-NetworkRuleSet <PSNetworkRuleSet>] [-EnableHierarchicalNamespace <Boolean>]
 [-EnableAzureActiveDirectoryDomainServicesForFile <Boolean>] [-EnableLargeFileShare]
 [-PublishMicrosoftEndpoint <Boolean>] [-PublishInternetEndpoint <Boolean>] [-AsJob]
 [-EncryptionKeyTypeForTable <String>] [-EncryptionKeyTypeForQueue <String>] [-RequireInfrastructureEncryption]
 [-SasExpirationPeriod <TimeSpan>] [-KeyExpirationPeriodInDay <Int32>] [-AllowBlobPublicAccess <Boolean>]
 [-MinimumTlsVersion <String>] [-AllowSharedKeyAccess <Boolean>] [-EnableNfsV3 <Boolean>]
 [-AllowCrossTenantReplication <Boolean>] [-DefaultSharePermission <String>] [-EdgeZone <String>]
 [-PublicNetworkAccess <String>] [-EnableAccountLevelImmutability] [-ImmutabilityPeriod <Int32>]
 [-ImmutabilityPolicyState <String>] [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>]
 [<CommonParameters>]
```

### ActiveDirectoryDomainServicesForFile
```
New-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String> [-Location] <String>
 [-Kind <String>] [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>]
 [-Tag <Hashtable>] [-EnableHttpsTrafficOnly <Boolean>] [-AssignIdentity] [-UserAssignedIdentityId <String>]
 [-IdentityType <String>] [-KeyVaultUserAssignedIdentityId <String>] [-KeyName <String>] [-KeyVersion <String>]
 [-KeyVaultUri <String>] [-NetworkRuleSet <PSNetworkRuleSet>] [-EnableHierarchicalNamespace <Boolean>]
 [-EnableLargeFileShare] [-PublishMicrosoftEndpoint <Boolean>] [-PublishInternetEndpoint <Boolean>]
 [-EnableActiveDirectoryDomainServicesForFile <Boolean>] [-ActiveDirectoryDomainName <String>]
 [-ActiveDirectoryNetBiosDomainName <String>] [-ActiveDirectoryForestName <String>]
 [-ActiveDirectoryDomainGuid <String>] [-ActiveDirectoryDomainSid <String>]
 [-ActiveDirectoryAzureStorageSid <String>] [-ActiveDirectorySamAccountName <String>]
 [-ActiveDirectoryAccountType <String>] [-AsJob] [-EncryptionKeyTypeForTable <String>]
 [-EncryptionKeyTypeForQueue <String>] [-RequireInfrastructureEncryption] [-SasExpirationPeriod <TimeSpan>]
 [-KeyExpirationPeriodInDay <Int32>] [-AllowBlobPublicAccess <Boolean>] [-MinimumTlsVersion <String>]
 [-AllowSharedKeyAccess <Boolean>] [-EnableNfsV3 <Boolean>] [-AllowCrossTenantReplication <Boolean>]
 [-DefaultSharePermission <String>] [-EdgeZone <String>] [-PublicNetworkAccess <String>]
 [-EnableAccountLevelImmutability] [-ImmutabilityPeriod <Int32>] [-ImmutabilityPolicyState <String>]
 [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageAccount** membuat akun Azure Storage.

## EXAMPLES

### Contoh 1: Membuat akun Storage
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS
```

Perintah ini membuat akun Storage untuk nama grup sumber daya MyResourceGroup.

### Contoh 2: Membuat akun blob Storage dengan BlobStorage Kind dan hot AccessTier
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind BlobStorage -AccessTier Hot
```

Perintah ini membuat akun blob Storage yang dengan BlobStorage Kind dan hot AccessTier

### Contoh 3: Buat akun Storage dengan Kind StorageV2, dan Buat dan Tetapkan Identitas untuk Azure KeyVault.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind StorageV2 -AssignIdentity
```

Perintah ini membuat akun Storage dengan Kind StorageV2.  Ini juga menghasilkan dan menetapkan identitas yang dapat digunakan untuk mengelola kunci akun melalui Azure KeyVault.

### Contoh 4: Membuat akun Storage dengan NetworkRuleSet dari JSON
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -Type Standard_LRS -NetworkRuleSet (@{bypass="Logging,Metrics";
    ipRules=(@{IPAddressOrRange="20.11.0.0/16";Action="allow"},
            @{IPAddressOrRange="10.0.0.0/7";Action="allow"});
    virtualNetworkRules=(@{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet1/subnets/subnet1";Action="allow"},
                        @{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet2/subnets/subnet2";Action="allow"});
    defaultAction="Deny"})
```

Perintah ini membuat akun Storage yang memiliki properti NetworkRuleSet dari JSON

### Contoh 5: Buat akun Storage dengan Namespace Hierarki diaktifkan.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "US West" -SkuName "Standard_GRS" -Kind StorageV2  -EnableHierarchicalNamespace $true
```

Perintah ini membuat akun Storage dengan Namespace Hierarki diaktifkan.

### Contoh 6: Buat akun Storage dengan Autentikasi Azure Files AAD DS, dan aktifkan berbagi file besar.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EnableAzureActiveDirectoryDomainServicesForFile $true -EnableLargeFileShare
```

Perintah ini membuat akun Storage dengan Autentikasi Azure Files AAD DS, dan mengaktifkan berbagi file besar.

### Contoh 7: Buat akun Storage dengan mengaktifkan Autentikasi Layanan Domain Direktori Aktif File dan DefaultSharePermission.
```
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EnableActiveDirectoryDomainServicesForFile $true `
        -ActiveDirectoryDomainName "mydomain.com" `
        -ActiveDirectoryNetBiosDomainName "mydomain.com" `
        -ActiveDirectoryForestName "mydomain.com" `
        -ActiveDirectoryDomainGuid "12345678-1234-1234-1234-123456789012" `
        -ActiveDirectoryDomainSid "S-1-5-21-1234567890-1234567890-1234567890" `
        -ActiveDirectoryAzureStorageSid "S-1-5-21-1234567890-1234567890-1234567890-1234" `
        -ActiveDirectorySamAccountName "samaccountname" `
        -ActiveDirectoryAccountType User `
        -DefaultSharePermission StorageFileDataSmbShareElevatedContributor
```

Perintah ini membuat akun Storage dengan File Active Directory Active Directory Domain Service Authentication dan DefaultSharePermission.

### Contoh 8: Buat akun Storage dengan Antrean dan Layanan Tabel menggunakan kunci enkripsi cakupan akun, dan Memerlukan Enkripsi Infrastruktur.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EncryptionKeyTypeForTable Account -EncryptionKeyTypeForQueue Account -RequireInfrastructureEncryption

PS C:\>$account = get-AzStorageAccount -ResourceGroupName $rgname -StorageAccountName $accountName

PS C:\>$account.Encryption.Services.Queue

Enabled LastEnabledTime     KeyType
------- ---------------     -------
   True 1/9/2020 6:09:11 AM Account

PS C:\>$account.Encryption.Services.Table

Enabled LastEnabledTime     KeyType
------- ---------------     -------
   True 1/9/2020 6:09:11 AM Account

PS C:\> $account.Encryption.RequireInfrastructureEncryption
True
```

Perintah ini membuat akun Storage dengan Antrean dan Layanan Tabel menggunakan kunci enkripsi cakupan akun dan Memerlukan Enkripsi Infrastruktur, sehingga Antrean dan Tabel akan menggunakan kunci enkripsi yang sama dengan layanan Blob dan File, dan layanan akan menerapkan lapisan enkripsi sekunder dengan kunci yang dikelola platform untuk data tidak aktif.
Kemudian dapatkan properti akun Storage, dan lihat keytype enkripsi Antrean dan Layanan Tabel, dan nilai RequireInfrastructureEncryption.

### Contoh 9: Buat akun MinimumTlsVersion dan AllowBlobPublicAccess, dan nonaktifkan Akses SharedKey
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2 -MinimumTlsVersion TLS1_1 -AllowBlobPublicAccess $false -AllowSharedKeyAccess $false

PS C:\> $account.MinimumTlsVersion
TLS1_1

PS C:\> $account.AllowBlobPublicAccess
False

PS C:\> $a.AllowSharedKeyAccess
False
```

Perintah membuat akun dengan MinimumTlsVersion, AllowBlobPublicAccess, dan menonaktifkan akses SharedKey ke akun, lalu menampilkan 3 properti akun yang dibuat 

### Contoh 10: Membuat akun Storage dengan pengaturan RoutingPreference
```powershell
PS C:\>$account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -PublishMicrosoftEndpoint $true -PublishInternetEndpoint $true -RoutingChoice MicrosoftRouting

PS C:\>$account.RoutingPreference

RoutingChoice    PublishMicrosoftEndpoints PublishInternetEndpoints
-------------    ------------------------- ------------------------
MicrosoftRouting                     True                     True

PS C:\>$account.PrimaryEndpoints

Blob               : https://mystorageaccount.blob.core.windows.net/
Queue              : https://mystorageaccount.queue.core.windows.net/
Table              : https://mystorageaccount.table.core.windows.net/
File               : https://mystorageaccount.file.core.windows.net/
Web                : https://mystorageaccount.z2.web.core.windows.net/
Dfs                : https://mystorageaccount.dfs.core.windows.net/
MicrosoftEndpoints : {"Blob":"https://mystorageaccount-microsoftrouting.blob.core.windows.net/","Queue":"https://mystorageaccount-microsoftrouting.queue.core.windows.net/","Table":"https://mystorageaccount-microsoftrouting.table.core.windows.net/","File":"ht
                     tps://mystorageaccount-microsoftrouting.file.core.windows.net/","Web":"https://mystorageaccount-microsoftrouting.z2.web.core.windows.net/","Dfs":"https://mystorageaccount-microsoftrouting.dfs.core.windows.net/"}
InternetEndpoints  : {"Blob":"https://mystorageaccount-internetrouting.blob.core.windows.net/","File":"https://mystorageaccount-internetrouting.file.core.windows.net/","Web":"https://mystorageaccount-internetrouting.z2.web.core.windows.net/","Dfs":"https://w
                     eirp3-internetrouting.dfs.core.windows.net/"}
```

Perintah ini membuat akun Storage dengan pengaturan RoutingPreference: PublishMicrosoftEndpoint dan PublishInternetEndpoint sebagai true, dan RoutingChoice sebagai MicrosoftRouting.

### Contoh 11: Membuat akun Storage dengan EdgeZone dan AllowCrossTenantReplication
```powershell
PS C:\>$account = New-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -SkuName Premium_LRS -Location westus -EdgeZone "microsoftlosangeles1" -AllowCrossTenantReplication $false

PS C:\>$account.ExtendedLocation

Name                 Type    
----                 ----    
microsoftlosangeles1 EdgeZone

PS C:\> $account.AllowCrossTenantReplication
False
```

Perintah ini membuat akun Storage dengan EdgeZone sebagai "microsoftlosangeles1" dan AllowCrossTenantReplication sebagai false, lalu menampilkan properti terkait akun yang dibuat.

### Contoh 12: Membuat akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod
```powershell
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -SkuName Premium_LRS -Location eastus -KeyExpirationPeriodInDay 5 -SasExpirationPeriod "1.12:05:06"

PS C:\> $$account.KeyPolicy.KeyExpirationPeriodInDays
5

PS C:\> $$account.SasPolicy.SasExpirationPeriod
1.12:05:06
```

Perintah ini membuat akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod, lalu menampilkan properti terkait akun yang dibuat.

### Contoh 12: Membuat akun Storage dengan enkripsi Keyvault (akses Keyvault dengan identitas yang ditetapkan pengguna)
```powershell
# Create KeyVault (no need if using exist keyvault)
PS C:\> $keyVault = New-AzKeyVault -VaultName $keyvaultName -ResourceGroupName $resourceGroupName -Location eastus2euap -EnablePurgeProtection
PS C:\> $key = Add-AzKeyVaultKey -VaultName $keyvaultName -Name $keyname -Destination 'Software'

# create user assigned identity and grant access to keyvault (no need if using exist user assigned identity)
PS C:\> $userId = New-AzUserAssignedIdentity -ResourceGroupName $resourceGroupName -Name $userIdName
PS C:\> Set-AzKeyVaultAccessPolicy -VaultName $keyvaultName -ResourceGroupName $resourceGroupName -ObjectId $userId.PrincipalId -PermissionsToKeys get,wrapkey,unwrapkey -BypassObjectIdValidation
PS C:\> $useridentityId= $userId.Id

# create Storage account with Keyvault encryption (access Keyvault with user assigned identity), then show properties
PS C:\> $account = New-AzStorageAccount -ResourceGroupName $resourceGroupName -Name $storageAccountName -Kind StorageV2 -SkuName Standard_LRS -Location eastus2euap `
                -IdentityType SystemAssignedUserAssigned  -UserAssignedIdentityId $useridentityId  `
                -KeyVaultUri $keyVault.VaultUri -KeyName $keyname -KeyVaultUserAssignedIdentityId $useridentityId

PS C:\> $account.Encryption.EncryptionIdentity

EncryptionUserAssignedIdentity                                                                                                                 
------------------------------ 
/subscriptions/{subscription-id}/resourceGroups/myresourcegroup/providers/Microsoft.ManagedIdentity/userAssignedIdentities/myuserid

PS C:\> $account.Encryption.KeyVaultProperties

KeyName                       : wrappingKey
KeyVersion                    : 
KeyVaultUri                   : https://mykeyvault.vault.azure.net:443
CurrentVersionedKeyIdentifier : https://mykeyvault.vault.azure.net/keys/wrappingKey/8e74036e0d534e58b3bd84b319e31d8f
LastKeyRotationTimestamp      : 4/12/2021 8:17:57 AM
```

Perintah ini pertama-tama membuat keyvault dan identitas yang ditetapkan pengguna, lalu membuat akun penyimpanan dengan enkripsi keyvault (keyvault akses penyimpanan dengan identitas yang ditetapkan pengguna).

### Contoh 13: Membuat akun dengan EnableNfsV3
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -EnableNfsV3 $true -EnableHierarchicalNamespace $true -EnableHttpsTrafficOnly $false -NetworkRuleSet (@{bypass="Logging,Metrics";
        virtualNetworkRules=(@{VirtualNetworkResourceId="$vnet1";Action="allow"});
        defaultAction="deny"}) 
PS C:\> $account.EnableNfsV3
True
```

Perintah buat akun dengan EnableNfsV3 sebagai true, lalu tampilkan properti EnableNfsV3 dari akun yang dibuat 

### Contoh 14: Membuat akun dengan menonaktifkan PublicNetworkAccess
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -PublicNetworkAccess Disabled

PS C:\> $account.PublicNetworkAccess
Disabled
```

Perintah membuat akun dengan menonaktifkan PublicNetworkAccess akun.

### Contoh 15: Membuat akun dengan kebijakan mmutability tingkat akun
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -EnableAccountLevelImmutability -ImmutabilityPeriod 1 -ImmutabilityPolicyState Unlocked

PS C:\> $account.ImmutableStorageWithVersioning.Enabled
True

PS C:\> $account.ImmutableStorageWithVersioning.ImmutabilityPolicy

ImmutabilityPeriodSinceCreationInDays State    
------------------------------------- -----    
                                    1 Unlocked 
```

Perintah membuat akun dan mengaktifkan kekekalan tingkat akun dengan penerapan versi oleh '-EnableAccountLevelImmutability', maka semua kontainer di bawah akun ini akan mengaktifkan kekekalan tingkat objek secara default.
Akun ini juga dibuat dengan kebijakan kekekalan tingkat akun default yang diwarisi dan diterapkan ke objek yang tidak memiliki kebijakan kekekalan eksplisit di tingkat objek. 

## PARAMETERS

### -AccessTier
Menentukan tingkat akses akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Panas dan Dingin.
Jika Anda menentukan nilai BlobStorage untuk parameter *Jenis* , Anda harus menentukan nilai untuk parameter *AccessTier* . Jika Anda menentukan nilai Storage untuk parameter *Jenis* ini, jangan tentukan parameter *AccessTier*.

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

### -ActiveDirectoryAccountType
Menentukan jenis akun Direktori Aktif untuk Azure Storage. Nilai yang mungkin termasuk: 'Pengguna', 'Komputer'.

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
Menentukan GUID domain. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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
Menentukan domain utama tempat server DNS AD berwenang. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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
Menentukan forest Direktori Aktif yang akan didapatkan. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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

### -ActiveDirectorySamAccountName
Menentukan SAMAccountName Direktori Aktif untuk Azure Storage.

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
Izinkan akses publik ke semua blob atau kontainer di akun penyimpanan. Interpretasi default adalah true untuk properti ini.

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
Mendapatkan atau mengatur mengizinkan atau melarang replikasi objek penyewa lintas AAD. Interpretasi default adalah true untuk properti ini.

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
Menentukan nama domain kustom akun Storage.
Nilai defaultnya adalah Storage.

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

### -EdgeZone
Atur nama lokasi yang diperluas untuk EdgeZone. Jika tidak diatur, akun penyimpanan akan dibuat di wilayah utama Azure. Jika tidak, itu akan dibuat di lokasi yang diperluas yang ditentukan

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

### -EnableAccountLevelImmutability
Mengaktifkan imutabilitas tingkat akun, maka semua kontainer di bawah akun ini akan mengaktifkan imutabilitas tingkat objek secara default.

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

### -EnableActiveDirectoryDomainServicesForFile
Aktifkan Azure Files Autentikasi Layanan Domain Direktori Aktif untuk akun penyimpanan.

```yaml
Type: System.Boolean
Parameter Sets: ActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAzureActiveDirectoryDomainServicesForFile
Aktifkan Azure Files Azure Active Directory Autentikasi Layanan Domain untuk akun penyimpanan.

```yaml
Type: System.Boolean
Parameter Sets: AzureActiveDirectoryDomainServicesForFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHierarchicalNamespace
Menunjukkan apakah akun Storage mengaktifkan Namespace Hierarkis atau tidak.

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
Menunjukkan apakah akun penyimpanan dapat mendukung berbagi file besar dengan kapasitas lebih dari 5 TiB atau tidak. Setelah akun diaktifkan, fitur tidak dapat dinonaktifkan. Saat ini hanya didukung untuk jenis replikasi LRS dan ZRS, oleh karena itu konversi akun ke akun geo-redundan tidak akan dimungkinkan. Pelajari lebih lanjut di https://go.microsoft.com/fwlink/?linkid=2086047

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

### -EnableNfsV3
Aktifkan dukungan protokol NFS 3.0 jika diatur ke true

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

### -EncryptionKeyTypeForQueue
Atur Encryption KeyType untuk Antrean. Nilai defaultnya adalah Layanan.
-Account: Antrean akan dienkripsi dengan kunci enkripsi cakupan akun. -Layanan: Antrean akan selalu dienkripsi dengan kunci Service-Managed. 

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Service, Account

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyTypeForTable
Atur Encryption KeyType untuk Tabel. Nilai defaultnya adalah Layanan.
- Akun: Tabel akan dienkripsi dengan kunci enkripsi cakupan akun. 
- Layanan: Tabel akan selalu dienkripsi dengan kunci Service-Managed. 

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Service, Account

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Atur jenis Identitas Akun Storage baru, idenetitasnya adalah untuk digunakan dengan layanan manajemen utama seperti Azure KeyVault.

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

### -ImmutabilityPeriod
Periode imutabilitas untuk blob dalam kontainer sejak pembuatan kebijakan dalam beberapa hari. Properti ini hanya dapat ditentukan dengan '-EnableAccountLevelImmutability'.

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

### -ImmutabilityPolicyState
Mode kebijakan. Nilai yang mungkin termasuk: 'Tidak Terkunci', 'Dinonaktifkan. Status dinonaktifkan menonaktifkan kebijakan. Status tidak terkunci memungkinkan peningkatan dan penurunan waktu retensi kekekalan dan juga memungkinkan pengalihan properti allowProtectedAppendWrites. Kebijakan hanya dapat dibuat dalam status Dinonaktifkan atau Tidak Terkunci dan dapat dialihkan di antara kedua status.
Properti ini hanya dapat ditentukan dengan '-EnableAccountLevelImmutability'.

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

### -KeyExpirationPeriodInDay
Periode kedaluwarsa kunci akun ini, akurat hingga berhari-hari.

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
Storage Kunci enkripsi AkunSource KeyVault KeyName

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

### -KeyVaultUri
Storage Kunci enkripsi akunSource KeyVault KeyVaultUri

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

### -KeyVaultUserAssignedIdentityId
Atur id sumber daya untuk Identitas yang ditetapkan pengguna yang digunakan untuk mengakses Azure KeyVault dari Enkripsi Akun Storage, id harus di UserAssignIdentityId.

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
Storage Kunci enkripsi akunSource KeyVault KeyVersion

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

### -Jenis
Menentukan jenis akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Penyimpanan. Tujuan umum Storage akun yang mendukung penyimpanan Blob, Tabel, Antrean, File, dan Disk.
- StorageV2. Akun Storage Tujuan Umum Versi 2 (GPv2) yang mendukung Blob, Tabel, Antrean, File, dan Disk, dengan fitur canggih seperti tingkatan data.
- BlobStorage. Akun blob Storage yang hanya mendukung penyimpanan Blob.
- BlockBlobStorage. Blokir akun blob Storage yang hanya mendukung penyimpanan Blob Blok.
- FileStorage. Akun Storage file yang hanya mendukung penyimpanan File.
Nilai defaultnya adalah StorageV2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Storage, StorageV2, BlobStorage, BlockBlobStorage, FileStorage

Required: False
Position: Named
Default value: StorageV2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi akun Storage yang akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumTlsVersion
Versi TLS minimum yang akan diizinkan berdasarkan permintaan ke penyimpanan. Interpretasi default adalah TLS 1.0 untuk properti ini.

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

### -Name
Menentukan nama akun Storage yang akan dibuat.

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
NetworkRuleSet digunakan untuk menentukan sekumpulan aturan konfigurasi untuk firewall dan jaringan virtual, serta untuk mengatur nilai untuk properti jaringan seperti layanan yang diizinkan untuk melewati aturan dan cara menangani permintaan yang tidak cocok dengan salah satu aturan yang ditentukan.

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
Mengizinkan atau melarang akses jaringan publik ke akun Storage.Nilai yang mungkin meliputi: 'Diaktifkan', 'Dinonaktifkan'.

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

### -RequireInfrastructureEncryption
Layanan ini akan menerapkan lapisan enkripsi sekunder dengan kunci yang dikelola platform untuk data tidak aktif.

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

### -ResourceGroupName
Menentukan nama grup sumber daya untuk menambahkan akun Storage.

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
Pilihan Perutean menentukan jenis perutean jaringan yang dipilih oleh pengguna. Nilai yang mungkin termasuk: 'MicrosoftRouting', 'InternetRouting'

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
Periode kedaluwarsa SAS akun ini, merupakan rentang waktu dan akurat hingga detik.

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
Menentukan nama SKU akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_LRS. Penyimpanan redundan lokal.
- Standard_ZRS. Penyimpanan zona-redundan.
- Standard_GRS. Penyimpanan geo-redundan.
- Standard_RAGRS. Membaca penyimpanan geo-redundan akses.
- Premium_LRS. Premium penyimpanan yang berlebihan secara lokal.
- Premium_ZRS. Premium penyimpanan zona redundan.
- Standard_GZRS - Penyimpanan redundansi zona geo-redundan.
- Standard_RAGZRS - Akses baca penyimpanan redundansi zona redundan secara geografis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType, Type
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS, Premium_ZRS, Standard_GZRS, Standard_RAGZRS

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan kunci-nilai dalam bentuk tabel hash yang ditetapkan sebagai tag di server. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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

### -UserAssignedIdentityId
Atur id sumber daya untuk Identitas yang ditetapkan pengguna Akun Storage baru, identitas akan digunakan dengan layanan manajemen utama seperti Azure KeyVault.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## NOTES

## RELATED LINKS

[Dapatkan-AkunPenyimpananAz](./Get-AzStorageAccount.md)

[Remove-AzStorageAccount](./Remove-AzStorageAccount.md)

[Set-AzStorageAccount](./Set-AzStorageAccount.md)
