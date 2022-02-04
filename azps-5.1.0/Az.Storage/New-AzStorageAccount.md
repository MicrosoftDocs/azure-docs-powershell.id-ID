---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
ms.assetid: A3DA1205-B8FB-4B4C-9C40-AD303D038EDF
online version: https://docs.microsoft.com/en-us/powershell/module/az.storage/new-azstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/New-AzStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Storage/Storage.Management/help/New-AzStorageAccount.md
ms.openlocfilehash: 022c27b3eec589e395e1044f165ee9f8f17d1cad
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136032044"
---
# New-AzStorageAccount

## SYNOPSIS
Membuat akun Storage Anda.

## SINTAKS

### AzureActiveDirectoryDomainServicesForFile (Default)
```
New-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String> [-Location] <String>
 [-Kind <String>] [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>]
 [-Tag <Hashtable>] [-EnableHttpsTrafficOnly <Boolean>] [-AssignIdentity] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-EnableHierarchicalNamespace <Boolean>] [-EnableAzureActiveDirectoryDomainServicesForFile <Boolean>]
 [-EnableLargeFileShare] [-AsJob] [-EncryptionKeyTypeForTable <String>] [-EncryptionKeyTypeForQueue <String>]
 [-RequireInfrastructureEncryption] [-AllowBlobPublicAccess <Boolean>] [-MinimumTlsVersion <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ActiveDirectoryDomainServicesForFile
```
New-AzStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String> [-Location] <String>
 [-Kind <String>] [-AccessTier <String>] [-CustomDomainName <String>] [-UseSubDomain <Boolean>]
 [-Tag <Hashtable>] [-EnableHttpsTrafficOnly <Boolean>] [-AssignIdentity] [-NetworkRuleSet <PSNetworkRuleSet>]
 [-EnableHierarchicalNamespace <Boolean>] [-EnableLargeFileShare]
 [-EnableActiveDirectoryDomainServicesForFile <Boolean>] [-ActiveDirectoryDomainName <String>]
 [-ActiveDirectoryNetBiosDomainName <String>] [-ActiveDirectoryForestName <String>]
 [-ActiveDirectoryDomainGuid <String>] [-ActiveDirectoryDomainSid <String>]
 [-ActiveDirectoryAzureStorageSid <String>] [-AsJob] [-EncryptionKeyTypeForTable <String>]
 [-EncryptionKeyTypeForQueue <String>] [-RequireInfrastructureEncryption] [-AllowBlobPublicAccess <Boolean>]
 [-MinimumTlsVersion <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzStorageAccount** membuat Azure Storage Anda.

## CONTOH

### Contoh 1: Buat akun Storage Anda
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS
```

Perintah ini membuat akun Storage untuk nama grup sumber daya MyResourceGroup.

### Contoh 2: Create a Blob Storage account with BlobStorage Kind and hot AccessTier
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind BlobStorage -AccessTier Hot
```

Perintah ini akan membuat akun Storage BlobStorage dan hot AccessTier

### Contoh 3: Buat akun Storage dengan Kind StorageV2, lalu Buat dan Tetapkan Identitas untuk Azure KeyVault.
```powershell
PS C:\>New-AzStorageAccount -ResourceGroupName MyResourceGroup -AccountName mystorageaccount -Location westus -SkuName Standard_GRS -Kind StorageV2 -AssignIdentity
```

Perintah ini membuat akun Storage dengan Kind StorageV2.  Pernyataan ini juga menghasilkan dan menetapkan identitas yang dapat digunakan untuk mengelola kunci akun melalui Azure KeyVault.

### Contoh 4: Membuat akun Storage dengan NetworkRuleSet dari JSON
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

Perintah ini akan membuat akun Storage dengan Autentikasi DS Azure Files AAD, dan mengaktifkan berbagi file berukuran besar.

### Contoh 7: Buat akun Storage dengan aktifkan Autentikasi Layanan Domain Direktori Aktif File.
```
PS C:\>New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2  -EnableActiveDirectoryDomainServicesForFile $true `
        -ActiveDirectoryDomainName "mydomain.com" `
        -ActiveDirectoryNetBiosDomainName "mydomain.com" `
        -ActiveDirectoryForestName "mydomain.com" `
        -ActiveDirectoryDomainGuid "12345678-1234-1234-1234-123456789012" `
        -ActiveDirectoryDomainSid "S-1-5-21-1234567890-1234567890-1234567890" `
        -ActiveDirectoryAzureStorageSid "S-1-5-21-1234567890-1234567890-1234567890-1234"
```

Perintah ini akan membuat Storage akun dengan Autentikasi Layanan Domain Direktori Aktif File yang dapat digunakan.

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

Perintah ini akan membuat akun Storage dengan Layanan Antrean dan Tabel menggunakan kunci enkripsi akun yang scoped dan Perlu Enkripsi Infrastruktur, sehingga Queue dan Table akan menggunakan kunci enkripsi yang sama dengan layanan Blob dan File, dan layanan akan menerapkan lapisan enkripsi sekunder dengan kunci yang dikelola platform untuk data dalam media fisik.
Lalu dapatkan kunci Storage, dan tampilkan tipe kunci enkripsi Dari Queue and Table Service, dan nilai RequireInfrastructureEncryption.

### Contoh 9: Buat akun MinimumTlsVersion dan AllowBlobPublicAccess
```
PS C:\> $account = New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "eastus2euap" -SkuName "Standard_LRS" -Kind StorageV2 -MinimumTlsVersion TLS1_1 -AllowBlobPublicAccess $false

PS C:\> $account.MinimumTlsVersion
TLS1_1

PS C:\> $account.AllowBlobPublicAccess
False
```

Perintah membuat akun dengan MinimumTlsVersion dan AllowBlobPublicAccess, lalu memperlihatkan 2 properti akun yang dibuat 

## PARAMETERS

### -AccessTier
Menentukan tingkatan akses akun Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah: Hot dan Cool.
Jika Anda menentukan nilai BlobStorage untuk parameter *Kind,* Anda harus menentukan nilai untuk parameter *AccessTier.* Jika Anda menentukan nilai yang Storage untuk parameter *Kind* ini, jangan tentukan parameter *AccessTier.*

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
Nilai defaultnya Storage.

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
Menentukan nama grup sumber daya untuk menambahkan akun Storage tersebut.

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
Menentukan nama SKU pengguna Storage yang dibuat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_LRS. Penyimpanan lokal yang berlebihan.
- Standard_ZRS. Penyimpanan tidak berlebihan zona.
- Standard_GRS. Penyimpanan geo berlebihan.
- Standard_RAGRS. Baca mengakses penyimpanan geo berlebihan.
- Premium_LRS. Premium lokal berlebihan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## CATATAN

## LINK TERKAIT

[Get-AzStorageAccount](./Get-AzStorageAccount.md)

[Remove-AzStorageAccount](./Remove-AzStorageAccount.md)

[Set-AzStorageAccount](./Set-AzStorageAccount.md)
