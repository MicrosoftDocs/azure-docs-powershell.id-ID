---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: BF5E3E1A-14B6-4630-8168-628057009D5E
online version: ''
schema: 2.0.0
ms.openlocfilehash: a280834b5efb01be6dba87936ec0acc88344aac3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428120"
---
# Get-AzureEnvironment

## SYNOPSIS
Mendapatkan lingkungan Azure

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureEnvironment [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureEnvironment** mendapatkan lingkungan Azure yang tersedia untuk Windows PowerShell.

Lingkungan Azure, penyebaran independen dari Microsoft Azure, seperti AzureCloud untuk global Azure dan AzureChinaCloud untuk Azure yang dioperasikan oleh 21Vianet di Tiongkok.
Anda juga bisa membuat lingkungan Azure lokal dengan menggunakan Paket Azure dan cmdlet WAPack.
Untuk informasi selengkapnya, lihat [Paket Azure](/previous-versions/azure/windows-server-azure-pack/)).

Cmdlet **Get-AzureEnvironment** mendapatkan lingkungan dari file data langganan Anda, bukan dari Azure.
Jika file data langganan usang, jalankan cmdlet **Add-AzureAccount** atau **Import-PublishSettingsFile** untuk merefreshnya.

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Dapatkan semua lingkungan
```
PS C:\> Get-AzureEnvironment

EnvironmentName               ServiceEndpoint               ResourceManagerEndpoint       PublishSettingsFileUrl
---------------               ---------------               -----------------------       ----------------------

AzureCloud                    https://management.core.wi... https://management.azure.com/ https://go.microsoft.com/fw...
AzureChinaCloud               https://management.core.ch... https://not-supported-serv... https://go.microsoft.com/fw...
```

Perintah ini memberikan semua lingkungan yang tersedia untuk Windows PowerShell.

### Contoh 2: Dapatkan lingkungan dengan nama
```
PS C:\> Get-AzureEnvironment -Name AzureCloud

Name                          : AzureCloud

PublishSettingsFileUrl        : https://go.microsoft.com/fwlink/?LinkID=301775

ServiceEndpoint               : https://management.core.windows.net/

ResourceManagerEndpoint       : https://management.azure.com/

ManagementPortalUrl           : https://go.microsoft.com/fwlink/?LinkId=254433

ActiveDirectoryEndpoint       : https://login.windows.net/

ActiveDirectoryCommonTenantId : common

StorageEndpointSuffix         : core.windows.net

StorageBlobEndpointFormat     : {0}://{1}.blob.core.windows.net/

StorageQueueEndpointFormat    : {0}://{1}.queue.core.windows.net/

StorageTableEndpointFormat    : {0}://{1}.table.core.windows.net/

GalleryEndpoint               : https://gallery.azure.com/
```

Contoh ini mendapatkan lingkungan AzureCloud.

### Contoh 3: Mendapatkan semua properti untuk semua lingkungan
```
PS C:\> Get-AzureEnvironment | ForEach-Object {Get-AzureEnvironment -Name $_.EnvironmentName}
```

Perintah ini mendapatkan semua properti untuk semua lingkungan.

Perintah tersebut menggunakan cmdlet **Get-AzureEnvironment** untuk mendapatkan semua lingkungan Azure untuk akun ini.
Lalu, perintah ini menggunakan cmdlet **Foreach-Object** untuk menjalankan perintah **Get-AzureEnvironment** dengan parameter **Name** di setiap lingkungan.
Nilai parameter **Name** adalah properti **EnvironmentName** dari setiap lingkungan.

Tanpa parameter, **Get-AzureEnvironment** hanya mendapatkan properti lingkungan yang dipilih.

## PARAMETERS

### -Nama
Hanya mendapatkan lingkungan tertentu.
Ketikkan nama lingkungan.
Nilai parameter peka huruf besar/kecil.
Karakter wildcard tidak diizinkan.

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### System.Management.Automation.PSCustomObject
Secara default, **Get-AzureEnvironment** akan mengembalikan objek kustom.

### Microsoft.WindowsAzure.Commands.Utilities.Common.WindowsAzureEnvironment
Ketika Anda **menjalankan Get-AzureEnvironment** dengan parameter **Nama,** parameter ini akan **mengembalikan objek WindowsAzureEnvironment.**

## CATATAN

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Add-AzureEnvironment](./Add-AzureEnvironment.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)

[Import-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Remove-AzureEnvironment](./Remove-AzureEnvironment.md)

[Set-AzureEnvironment](./Set-AzureEnvironment.md)


