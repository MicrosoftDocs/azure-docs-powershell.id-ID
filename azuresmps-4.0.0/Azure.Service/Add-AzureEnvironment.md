---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 6C435518-06EA-41B7-9585-44107B026FF1
online version: ''
schema: 2.0.0
ms.openlocfilehash: d38477f94c97f484aba85b041deba748f12405ac
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044523"
---
# Add-AzureEnvironment

## SYNOPSIS
Membuat lingkungan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureEnvironment -Name <String> [-PublishSettingsFileUrl <String>] [-ServiceEndpoint <String>]
 [-ManagementPortalUrl <String>] [-StorageEndpoint <String>] [-ActiveDirectoryEndpoint <String>]
 [-ResourceManagerEndpoint <String>] [-GalleryEndpoint <String>]
 [-ActiveDirectoryServiceEndpointResourceId <String>] [-GraphEndpoint <String>]
 [-AzureKeyVaultDnsSuffix <String>] [-AzureKeyVaultServiceEndpointResourceId <String>]
 [-TrafficManagerDnsSuffix <String>] [-SqlDatabaseDnsSuffix <String>] [-EnableAdfsAuthentication]
 [-AdTenant <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureEnvironment** membuat lingkungan akun Azure kustom baru dan menyimpannya di profil pengguna jelajah Anda.
Cmdlet mengembalikan objek yang mewakili lingkungan baru.
Setelah perintah selesai, Anda dapat menggunakan lingkungan dalam Windows PowerShell.

Lingkungan Azure merupakan penyebaran independen Microsoft Azure, seperti AzureCloud untuk Azure global dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga dapat membuat lingkungan Azure lokal dengan menggunakan cmdlet Azure Pack dan WAPack.
Untuk informasi selengkapnya, lihat [Azure Pack](/previous-versions/azure/windows-server-azure-pack/).

Hanya parameter **Nama** cmdlet ini yang wajib.
Jika Anda menghilangkan parameter, nilainya adalah null ($Null), dan layanan yang menggunakan titik akhir tersebut mungkin tidak berfungsi dengan baik.
Untuk menambahkan atau mengubah nilai properti lingkungan, gunakan cmdlet **Set-AzureEnvironment** .

CATATAN: Mengubah lingkungan Anda dapat menyebabkan akun Anda gagal.
Biasanya, lingkungan ditambahkan hanya untuk pengujian atau pemecahan masalah.

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Menambahkan lingkungan Azure
```
PS C:\> Add-AzureEnvironment -Name ContosoEnv -PublishSettingsFileUrl https://contoso.com/fwlink/?LinkID=101 -ServiceEndpoint https://contoso.com/fwlink/?LinkID=102

Name                          : ContosoEnv

PublishSettingsFileUrl        : https://contoso.com/fwlink/?LinkID=101

ServiceEndpoint               : https://contoso.com/fwlink/?LinkID=102

ResourceManagerEndpoint       :

ManagementPortalUrl           :

ActiveDirectoryEndpoint       :

ActiveDirectoryCommonTenantId :

StorageEndpointSuffix         :

StorageBlobEndpointFormat     :

StorageQueueEndpointFormat    :

StorageTableEndpointFormat    :

GalleryEndpoint               :
```

Perintah ini membuat lingkungan Azure ContosoEnv.

## PARAMETERS

### -ActiveDirectoryEndpoint
Menentukan titik akhir untuk autentikasi Azure Active Directory di lingkungan baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AdEndpointUrl, ActiveDirectory, ActiveDirectoryAuthority

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ActiveDirectoryServiceEndpointResourceId
Menentukan ID sumber daya api manajemen yang aksesnya dikelola oleh Azure Active Directory.

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

### -AdTenant
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

### -AzureKeyVaultDnsSuffix
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

### -AzureKeyVaultServiceEndpointResourceId
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

### -EnableAdfsAuthentication
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: OnPremise

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GalleryEndpoint
Menentukan titik akhir untuk galeri Azure Resource Manager, yang menyimpan templat galeri grup sumber daya.
Untuk informasi selengkapnya tentang grup sumber daya Azure dan templat galeri, lihat topik bantuan untuk Get-AzureResourceGroupGalleryTemplatehttps://go.microsoft.com/fwlink/?LinkID=393052.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Gallery, GalleryUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GraphEndpoint
```yaml
Type: String
Parameter Sets: (All)
Aliases: Graph, GraphUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagementPortalUrl
Menentukan URL Portal Manajemen Azure di lingkungan baru.

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

### -Nama
Menentukan nama untuk lingkungan.
Parameter ini diperlukan.
Jangan gunakan nama lingkungan default, AzureCloud, dan AzureChinaCloud.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublishSettingsFileUrl
Menentukan URL file pengaturan penerbitan untuk akun Anda.
File pengaturan penerbitan Azure adalah file XML yang berisi informasi tentang akun Anda dan sertifikat manajemen yang memungkinkan Windows PowerShell masuk ke akun Azure atas nama Anda.

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

### -ResourceManagerEndpoint
Menentukan titik akhir untuk data Azure Resource Manager, termasuk data tentang grup sumber daya yang terkait dengan akun tersebut.
Untuk informasi selengkapnya tentang Azure Resource Manager, lihat [Cmdlet Azure Resource Manager](https://go.microsoft.com/fwlink/?LinkID=394765) (https://go.microsoft.com/fwlink/?LinkID=394765) dan [Menggunakan Windows PowerShell dengan Resource Manager](https://go.microsoft.com/fwlink/?LinkID=394767) (https://go.microsoft.com/fwlink/?LinkID=394767).

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceManager, ResourceManagerUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceEndpoint
Menentukan URL titik akhir layanan Azure.
Titik akhir layanan Azure menentukan apakah aplikasi Anda dikelola oleh platform Azure global, Azure yang dioperasikan oleh 21Vianet di Tiongkok, atau instalasi Azure pribadi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceManagement, ServiceManagementUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SqlDatabaseDnsSuffix
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

### -StorageEndpoint
Menentukan titik akhir default layanan penyimpanan di lingkungan baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageEndpointSuffix

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerDnsSuffix
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Common.WindowsAzureEnvironment

## NOTES

## RELATED LINKS

[Get-AzureEnvironment](./Get-AzureEnvironment.md)

[Hapus AzureEnvironment](./Remove-AzureEnvironment.md)

[Set-AzureEnvironment](./Set-AzureEnvironment.md)


