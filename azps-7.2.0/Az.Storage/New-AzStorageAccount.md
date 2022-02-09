---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A3DA1205-B8FB-4B4C-9C40-AD303D038EDF
online version: https://docs.microsoft.com/powershell/module/az.storage/new-azstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/New-AzStorageAccount.md
ms.openlocfilehash: ebc460b88cb1c133df143235e7094a0c73b23192
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138256204"
---
# New-AzStorageAccount

## SYNOPSIS
Membuat akun Storage Anda.

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
 [-ActiveDirectoryAzureStorageSid <String>] [-AsJob] [-EncryptionKeyTypeForTable <String>]
 [-EncryptionKeyTypeForQueue <String>] [-RequireInfrastructureEncryption] [-SasExpirationPeriod <TimeSpan>]
 [-KeyExpirationPeriodInDay <Int32>] [-AllowBlobPublicAccess <Boolean>] [-MinimumTlsVersion <String>]
 [-AllowSharedKeyAccess <Boolean>] [-EnableNfsV3 <Boolean>] [-AllowCrossTenantReplication <Boolean>]
 [-DefaultSharePermission <String>] [-EdgeZone <String>] [-PublicNetworkAccess <String>]
 [-EnableAccountLevelImmutability] [-ImmutabilityPeriod <Int32>] [-ImmutabilityPolicyState <String>]
 [-DefaultProfile <IAzureContextContainer>] [-RoutingChoice <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzStorageAccount** membuat akun Azure Storage Anda.

## EXAMPLES

### Contoh 1: Buat akun Storage Anda
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS
```

Perintah ini membuat akun Storage untuk nama grup sumber daya MyResourceGroup.

### Contoh 2: Buat akun Storage BlobStorage dengan Jenis BlobStorage dan hot AccessTier
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind BlobStorage -AccessTier Hot
```

Perintah ini membuat akun Storage BlobStorage dan hot AccessTier

### Contoh 3: Buat Storage dengan Kind StorageV2, lalu Buat dan Tetapkan Identitas untuk Azure KeyVault.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind StorageV2 -AssignIdentity
```

Perintah ini membuat akun Storage dengan Kind StorageV2.  Pernyataan ini juga menghasilkan dan menetapkan identitas yang dapat digunakan untuk mengelola kunci akun melalui Azure KeyVault.

### Contoh 4: Membuat Storage dengan NetworkRuleSet dari JSON
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -Type Standard_LRS -NetworkRuleSet (@{bypass="Logging,Metrics";
    ipRules=(@{IPAddressOrRange="20.11.0.0/16";Action="allow"},
            @{IPAddressOrRange="10.0.0.0/7";Action="allow"});
    virtualNetworkRules=(@{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet1/subnets/subnet1";Action="allow"},
                        @{VirtualNetworkResourceId="/subscriptions/s1/resourceGroups/g1/providers/Microsoft.Network/virtualNetworks/vnet2/subnets/subnet2";Action="allow"});
    defaultAction="Deny"})
```

Perintah ini akan membuat Storage pengguna yang memiliki properti NetworkRuleSet dari JSON

### Contoh 5: Buat Storage dengan Ruang Nama Hierarki diaktifkan.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "US West" -SkuName "Standard_GRS" -Kind StorageV2  -EnableHierarchicalNamespace $true
```

Perintah ini membuat akun Storage dengan Ruang Nama Hierarki diaktifkan.

### Contoh 6: Buat akun Storage dengan Azure Files AAD DS Authentication, dan aktifkan berbagi file berukuran besar.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EnableAzureActiveDirectoryDomainServicesForFile $true -EnableLargeFileShare
```

Perintah ini akan membuat Storage pengguna dengan Autentikasi Azure Files AAD DS, dan mengaktifkan berbagi file berukuran besar.

### Contoh 7: Buat akun Storage dengan aktifkan Autentikasi Layanan Domain Direktori Aktif File dan DefaultSharePermission.
```
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EnableActiveDirectoryDomainServicesForFile $true `
        -ActiveDirectoryDomainName "mydomain.com" `
        -ActiveDirectoryNetBiosDomainName "mydomain.com" `
        -ActiveDirectoryForestName "mydomain.com" `
        -ActiveDirectoryDomainGuid "12345678-1234-1234-1234-123456789012" `
        -ActiveDirectoryDomainSid "S-1-5-21-1234567890-1234567890-1234567890" `
        -ActiveDirectoryAzureStorageSid "S-1-5-21-1234567890-1234567890-1234567890-1234" `
        -DefaultSharePermission StorageFileDataSmbShareElevatedContributor
```

Perintah ini akan membuat Storage akun yang dapat dibagikan Autentikasi Layanan Domain Direktori Aktif dan DefaultSharePermission.

### Contoh 8: Membuat Storage dengan Queue and Table Service menggunakan kunci enkripsi akun yang scope, dan Memerlukan Enkripsi Infrastruktur.
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

Perintah ini membuat akun Storage dengan Layanan Antrean dan Tabel menggunakan kunci enkripsi akun yang scoped dan Perlu Enkripsi Infrastruktur, sehingga Queue dan Table akan menggunakan kunci enkripsi yang sama dengan layanan Blob dan File, dan layanan akan menerapkan lapisan enkripsi sekunder dengan kunci yang dikelola platform untuk data dalam media fisik.
Lalu dapatkan kunci Storage, dan tampilkan tipe kunci enkripsi Dari Queue and Table Service, dan nilai RequireInfrastructureEncryption.

### Contoh 9: Buat akun MinimumTlsVersion dan AllowBlobPublicAccess, dan nonaktifkan SharedKey Access
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2 -MinimumTlsVersion TLS1_1 -AllowBlobPublicAccess $false -AllowSharedKeyAccess $false

PS C:\> $account.MinimumTlsVersion
TLS1_1

PS C:\> $account.AllowBlobPublicAccess
False

PS C:\> $a.AllowSharedKeyAccess
False
```

Perintah membuat akun dengan MinimumTlsVersion, AllowBlobPublicAccess, dan menonaktifkan akses SharedKey ke akun, lalu memperlihatkan 3 properti dari akun yang dibuat 

### Contoh 10: Membuat Storage dengan pengaturan RoutingPreference
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

Perintah ini membuat akun Storage dengan pengaturan RoutingPreference: PublishMicrosoftEndpoint dan PublishInternetEndpoint sebagai true, dan RoutingChoice as MicrosoftRouting.

### Contoh 11: Buat akun Storage dengan EdgeZone dan AllowCrossTenantReplication
```powershell
PS C:\>$account = New-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -SkuName Premium_LRS -Location westus -EdgeZone "microsoftlosangeles1" -AllowCrossTenantReplication $false

PS C:\>$account.ExtendedLocation

Name                 Type    
----                 ----    
microsoftlosangeles1 EdgeZone

PS C:\> $account.AllowCrossTenantReplication
False
```

Perintah ini membuat akun Storage dengan EdgeZone sebagai "microsoftlosangeles1" dan AllowCrossTenantReplication sebagai false, lalu memperlihatkan properti yang terkait dengan akun yang dibuat.

### Contoh 12: Buat akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod
```powershell
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -SkuName Premium_LRS -Location eastus -KeyExpirationPeriodInDay 5 -SasExpirationPeriod "1.12:05:06"

PS C:\> $$account.KeyPolicy.KeyExpirationPeriodInDays
5

PS C:\> $$account.SasPolicy.SasExpirationPeriod
1.12:05:06
```

Perintah ini akan membuat akun Storage dengan KeyExpirationPeriod dan SasExpirationPeriod, lalu memperlihatkan properti terkait akun yang dibuat.

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

Perintah ini terlebih dahulu membuat keyvault dan identitas yang ditetapkan pengguna, lalu membuat akun penyimpanan dengan enkripsi keyvault (keyvault akses penyimpanan dengan identitas yang ditetapkan pengguna).

### Contoh 13: Buat akun dengan EnableNfsV3
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -EnableNfsV3 $true -EnableHierarchicalNamespace $true -EnableHttpsTrafficOnly $false -NetworkRuleSet (@{bypass="Logging,Metrics";
        virtualNetworkRules=(@{VirtualNetworkResourceId="$vnet1";Action="allow"});
        defaultAction="deny"}) 
PS C:\> $account.EnableNfsV3
True
```

Perintah membuat akun dengan EnableNfsV3 sebagai true, lalu memperlihatkan properti EnableNfsV3 dari akun yang dibuat 

### Contoh 14: Buat akun dengan nonaktifkan PublicNetworkAccess
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -PublicNetworkAccess Disabled

PS C:\> $account.PublicNetworkAccess
Disabled
```

Perintah membuat akun dengan menonaktifkan PublicNetworkAccess akun.

### Contoh 15: Membuat akun dengan kebijakan penggunaan mmutability tingkat akun
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName Standard_LRS  -Location centraluseuap -Kind StorageV2 -EnableAccountLevelImmutability -ImmutabilityPeriod 1 -ImmutabilityPolicyState Unlocked

PS C:\> $account.ImmutableStorageWithVersioning.Enabled
True

PS C:\> $account.ImmutableStorageWithVersioning.ImmutabilityPolicy

ImmutabilityPeriodSinceCreationInDays State    
------------------------------------- -----    
                                    1 Unlocked 
```

Perintah membuat akun dan mengaktifkan kemutasi tingkat akun dengan penerapan versi dengan '-EnableAccountLevelImmutability', lalu semua wadah di bawah akun ini akan mengaktifkan kemutasi tingkat objek secara default.
Akun juga dibuat dengan kebijakan keberlangsungan tingkat akun default yang diwariskan dan diterapkan ke objek yang tidak memiliki kebijakan akses eksplisit di tingkat objek. 

## PARAMETERS

### -AccessTier
Menentukan tingkatan akses akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Hot dan Cool.
Jika Anda menentukan nilai BlobStorage untuk parameter *Kind* , Anda harus menentukan nilai untuk parameter *AccessTier* . Jika Anda menetapkan nilai Storage untuk parameter *Kind* ini, jangan tentukan parameter *AccessTier*.

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
Menentukan domain utama yang akan menjadi tujuan otoritatif server AD DNS. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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
Menentukan hutan Active Directory yang akan didabatkan. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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

### -ActiveDirectoryNetDomainsDomainName
Menentukan nama domain Net ADMINISTRATOR. Parameter ini harus diatur ketika -EnableActiveDirectoryDomainServicesForFile diatur ke true.

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
Perbolehkan akses publik ke semua blob atau wadah di akun penyimpanan. Interpretasi default berlaku untuk properti ini.

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
Mendapatkan atau mengatur yang memperbolehkan atau tidak memperbolehkan AAD objek penyewa yang sama. Interpretasi default berlaku untuk properti ini.

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
Menunjukkan apakah akun penyimpanan mengizinkan permintaan untuk diotorisasi dengan kunci akses akun melalui Kunci Bersama. Jika salah, maka semua permintaan, termasuk tanda tangan akses bersama, harus diotorisasi dengan Azure Active Directory (Azure AD). Nilai default adalah null, yang setara dengan true.

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
Tetapkan nama lokasi yang diperluas untuk EdgeZone. Jika tidak diatur, akun penyimpanan akan dibuat di kawasan utama Azure. Jika tidak, file akan dibuat di lokasi diperluas yang ditentukan

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
Mengaktifkan keterbacaan tingkat akun, lalu semua wadah di bawah akun ini akan memiliki kemukaan tingkat objek yang diaktifkan secara default.

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
Aktifkan Autentikasi Layanan Domain Azure Files Active Directory untuk akun penyimpanan.

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
Aktifkan Azure Files Azure Active Directory Domain Service Authentication untuk akun penyimpanan.

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
Menunjukkan apakah akun Storage mengaktifkan Ruang Nama Hierarki.

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
Menunjukkan apakah akun Storage hanya mengaktifkan lalu lintas HTTPS.

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
Menunjukkan apakah akun penyimpanan dapat mendukung berbagi file besar atau tidak dengan lebih dari 5 kapasitas TiB. Setelah akun diaktifkan, fitur tersebut tidak bisa dinonaktifkan. Saat ini hanya didukung untuk tipe replikasi LRS dan ZRS, sehingga konversi akun ke akun geo-redundan tidak dimungkinkan. Pelajari selengkapnya di https://go.microsoft.com/fwlink/?linkid=2086047

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
Mengaktifkan dukungan protokol NFS 3.0 jika diset ke true

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
Atur Encryption KeyType untuk Antre. Nilai defaultnya adalah Layanan.
-Akun: Antrean akan dienkripsi dengan kunci enkripsi akun yang scope. -Layanan: Antrean akan selalu dienkripsi dengan Service-Managed kunci. 

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
Atur Enkripsi KeyType untuk Tabel. Nilai defaultnya adalah Layanan.
- Akun: Tabel akan dienkripsi dengan kunci enkripsi akun yang scoped. 
- Layanan: Tabel akan selalu dienkripsi dengan Service-Managed kunci. 

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
Set the new Storage Account Identity type, the idenetity is for use with key management services like Azure KeyVault.

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
Periode ketermukaan untuk blob dalam wadah sejak pembuatan kebijakan dalam hari. Properti ini hanya dapat ditentukan dengan '-EnableAccountLevelImmutability'.

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
Mode kebijakan. Kemungkinan nilai termasuk: 'Tidak terkunci', 'Dinonaktifkan. Status nonaktif menonaktifkan kebijakan. Status tidak terkunci memungkinkan menambah dan mengurangi waktu penyimpanan yang tetap dan memungkinkan untuk mengaktifkan properti AllowProtectedAppendWrites. Kebijakan hanya bisa dibuat dalam status Dinonaktifkan atau Tidak Terkunci dan bisa dialihkan di antara kedua status tersebut.
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
Periode kedaluwarsa utama akun ini, akurat untuk hari-hari.

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
Storage kunci enkripsi AkunSource KeyVault KeyName

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
Storage Kunci enkripsi AkunSource KeyVaultVaultUri

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
Set resource id for user assigned Identity used to access Azure KeyVault of Storage Account Encryption, the id must in UserAssignIdentityId.

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
Storage kunci enkripsi AkunSource KeyVault KeyVersion

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

### -Kind
Menentukan jenis akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Storage. Akun tujuan Storage yang mendukung penyimpanan Blob, Tabel, Antrean, File dan Disk.
- StorageV2. Akun Storage Tujuan Umum Versi 2 (GPv2) yang mendukung Blob, Tabel, Antrean, File, dan Disk, dengan fitur tingkat lanjut seperti tingkatan data.
- BlobStorage. Akun Storage Blob yang mendukung penyimpanan Blob saja.
- BlockBlobStorage. Blokir akun Storage Blob yang mendukung penyimpanan Blokir Blob saja.
- FileStorage. Akun Storage file yang mendukung penyimpanan File saja.
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
Menentukan lokasi akun Storage untuk dibuat.

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
Versi TLS minimal akan diizinkan pada permintaan ke penyimpanan. Interpretasi defaultnya adalah TLS 1.0 untuk properti ini.

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
Menentukan nama akun Storage dibuat.

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
NetworkRuleSet digunakan untuk menetapkan serangkaian aturan konfigurasi untuk firewall dan jaringan virtual, serta untuk mengatur nilai untuk properti jaringan seperti layanan yang diperbolehkan untuk melewati aturan dan cara menangani permintaan yang tidak cocok dengan aturan yang ditetapkan.

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
Memperbolehkan atau tidak memperbolehkan akses jaringan publik ke akun Storage.Nilai yang mungkin meliputi: 'Diaktifkan', 'Dinonaktifkan'.

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
Menunjukkan apakah titik akhir penyimpanan perutean Microsoft akan diterbitkan

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
Layanan akan menerapkan lapisan enkripsi sekunder dengan kunci terkelola platform untuk data yang tidak digunakan.

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
Menentukan nama grup sumber daya untuk menambahkan Storage tersebut.

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
Routing Choice menentukan jenis perutean jaringan yang diikutsertakan oleh pengguna. Kemungkinan nilai termasuk: 'MicrosoftRouting', 'InternetRouting'

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
Periode kedaluwarsa SAS akun ini, merupakan jangka waktu dan akurat ke detik.

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
Menentukan nama SKU pengguna Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_LRS. Penyimpanan lokal yang berlebihan.
- Standard_ZRS. Penyimpanan tidak berlebihan zona.
- Standard_GRS. Penyimpanan geo berlebihan.
- Standard_RAGRS. Baca mengakses penyimpanan geo berlebihan.
- Premium_LRS. Premium yang berlebihan secara lokal.
- Premium_ZRS. Premium berlebihan zona.
- Standard_GZRS - Penyimpanan tak ada zona berlebihan geo.
- Standard_RAGZRS - Membaca akses yang tidak berlebihan dalam zona penyimpanan yang berlebihan.

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
Pasangan nilai kunci dalam bentuk tabel hash yang diatur sebagai tag di server. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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
Set resource ids for the new Storage Account user assigned Identity, the identity will be used with key management services like Azure KeyVault.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## CATATAN

## RELATED LINKS

[Get-AzStorageAccount](./Get-AzStorageAccount.md)

[Remove-AzStorageAccount](./Remove-AzStorageAccount.md)

[Set-AzStorageAccount](./Set-AzStorageAccount.md)
