---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 1094497D-2CBE-41DF-9ED1-8E7D3F14B05A
online version: ''
schema: 2.0.0
ms.openlocfilehash: cb16e1e0ea965a820cd7fa6714a682f02840545c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915877"
---
# Set-AzureEnvironment

## SYNOPSIS
Mengubah properti lingkungan Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureEnvironment -Name <String> [-PublishSettingsFileUrl <String>] [-ServiceEndpoint <String>]
 [-ManagementPortalUrl <String>] [-StorageEndpoint <String>] [-ActiveDirectoryEndpoint <String>]
 [-ResourceManagerEndpoint <String>] [-GalleryEndpoint <String>]
 [-ActiveDirectoryServiceEndpointResourceId <String>] [-GraphEndpoint <String>]
 [-AzureKeyVaultDnsSuffix <String>] [-AzureKeyVaultServiceEndpointResourceId <String>]
 [-TrafficManagerDnsSuffix <String>] [-SqlDatabaseDnsSuffix <String>] [-EnableAdfsAuthentication]
 [-AdTenant <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureEnvironment** mengubah properti lingkungan Azure.
Mengembalikan objek yang mewakili lingkungan dengan nilai properti barunya.
Gunakan parameter **Nama** untuk mengidentifikasi lingkungan dan parameter lainnya untuk mengubah nilai properti.
Anda tidak dapat menggunakan **Set-AzureEnvironment** untuk mengubah nama lingkungan Azure.

Lingkungan Azure merupakan penyebaran independen Microsoft Azure, seperti AzureCloud untuk Azure global dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga dapat membuat lingkungan Azure lokal dengan menggunakan cmdlet Azure Pack dan WAPack.
Untuk informasi selengkapnya, lihat [Azure Pack](/previous-versions/azure/windows-server-azure-pack/).

CATATAN: Jangan ubah properti lingkungan AzureCloud atau AzureChinaCloud.
Gunakan cmdlet ini untuk mengubah nilai lingkungan privat yang Anda buat.

## EXAMPLES

### Contoh 1: Mengubah properti lingkungan
```
PS C:\> Set-AzureEnvironment -Name ContosoEnv -PublishSettingsFileUrl "https://contoso.com" -StorageEndpoint "contoso.com"
```

Perintah ini mengubah nilai properti **PublishSettingsFileUrl** dan **StorageEndpoint** lingkungan ContosoEnv.

## PARAMETERS

### -ActiveDirectoryEndpoint
Mengubah titik akhir untuk autentikasi Azure Active Directory ke nilai yang ditentukan.

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
Mengubah titik akhir galeri Resource Manager Azure ke nilai yang ditentukan.
Titik akhir galeri adalah lokasi untuk templat galeri grup sumber daya.
Untuk informasi selengkapnya tentang grup sumber daya Azure dan templat galeri, lihat topik bantuan untuk [Get-AzureResourceGroupGalleryTemplate](https://go.microsoft.com/fwlink/?LinkID=393052).

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
Mengubah URL Portal Manajemen Azure ke nilai yang ditentukan.

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
Mengidentifikasi lingkungan yang sedang diubah.
Parameter ini diperlukan.
Nilai parameter peka huruf besar kecil.
Karakter wildcard tidak diizinkan.

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
Mengubah URL untuk menerbitkan file pengaturan di lingkungan yang ditentukan.
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
Mengubah titik akhir untuk data Azure Resource Manager, termasuk data tentang grup sumber daya yang terkait dengan akun tersebut.
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
Mengubah URL titik akhir layanan Azure di lingkungan yang ditentukan.
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
Mengubah titik akhir default layanan penyimpanan di lingkungan yang ditentukan.

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

[Add-AzureEnvironment](./Add-AzureEnvironment.md)

[Get-AzureEnvironment](./Get-AzureEnvironment.md)

[Hapus AzureEnvironment](./Remove-AzureEnvironment.md)


