---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 022BBF5F-AFF1-45D5-9153-872779FFBAF4
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/restore-azapimanagement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Restore-AzApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Restore-AzApiManagement.md
ms.openlocfilehash: 79f662039b9656f29a7cf31a74132e5e67858a24
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145561790"
---
# Restore-AzApiManagement

## SYNOPSIS

Memulihkan Layanan API Management dari blob Azure Storage yang ditentukan.

## SYNTAX

```
Restore-AzApiManagement -ResourceGroupName <String> -Name <String> [-StorageContext] <IStorageContext>
 -SourceContainerName <String> -SourceBlobName <String> [-AccessType <String>] [-IdentityClientId <String>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Restore-AzApiManagement** memulihkan Layanan API Management dari cadangan yang ditentukan yang berada dalam blob Azure Storage.

## EXAMPLES

### Contoh 1: Memulihkan layanan API Management

```powershell
New-AzStorageAccount -StorageAccountName "ContosoStorage" -Location $location -ResourceGroupName "ContosoGroup02" -Type Standard_LRS
$storageKey = (Get-AzStorageAccountKey -ResourceGroupName "ContosoGroup02" -StorageAccountName "ContosoStorage")[0].Value
$storageContext = New-AzStorageContext -StorageAccountName "ContosoStorage" -StorageAccountKey $storageKey
Restore-AzApiManagement -ResourceGroupName "ContosoGroup" -Name "RestoredContosoApi" -StorageContext $StorageContext -SourceContainerName "ContosoBackups" -SourceBlobName "ContosoBackup.apimbackup"
```

Perintah ini memulihkan layanan API Management dari blob penyimpanan Azure.

### Contoh 2: Memulihkan layanan API Management menggunakan Kredensial Identitas Terkelola

``` powershell
PS D:> $storageContext=New-AzStorageContext -StorageAccountName apimbackupmsi
PS D:> $resourceGroupName="ContosoGroup02";
PS D:> $apiManagementName="contosoapi";
PS D:> $containerName="apimbackupcontainer";
PS D:> $backupName="test-sdk-backup-1";
PS D:> $msiClientId="a6270d0c-7d86-478b-8cbe-dc9047ba54f7"

PS D:> Restore-AzApiManagement -ResourceGroupName $resourceGroupName -Name $apiManagementName -StorageContext $storageContext -SourceContainerName $containerName -SourceBlobName $backupName -AccessType "UserAssignedManagedIdentity" -IdentityClientId $msiClientId -PassThru


PublicIPAddresses                     : {52.143.79.150}
PrivateIPAddresses                    :
Id                                    : /subscriptions/4f5285a3-9fd7-40ad-91b1-d8fc3823983d/resourceGroups/ContosoGroup02/providers/Microsoft.ApiManagement/service/contosoapi
Name                                  : contosoapi
Location                              : West US 2
Sku                                   : Premium
Capacity                              : 1
CreatedTimeUtc                        : 10/13/2021 5:49:32 PM
ProvisioningState                     : Succeeded
RuntimeUrl                            : https://contosoapi.azure-api.net
RuntimeRegionalUrl                    : https://contosoapi-westus2-01.regional.azure-api.net
PortalUrl                             : https://contosoapi.portal.azure-api.net
DeveloperPortalUrl                    : https://contosoapi.developer.azure-api.net
ManagementApiUrl                      : https://contosoapi.management.azure-api.net
ScmUrl                                : https://contosoapi.scm.azure-api.net
PublisherEmail                        : foobar@microsoft.com
OrganizationName                      : fsdfsdfs
NotificationSenderEmail               : apimgmt-noreply@mail.windowsazure.com
VirtualNetwork                        :
VpnType                               : None
PortalCustomHostnameConfiguration     :
ProxyCustomHostnameConfiguration      : {contosoapi.azure-api.net}
ManagementCustomHostnameConfiguration :
ScmCustomHostnameConfiguration        :
DeveloperPortalHostnameConfiguration  :
SystemCertificates                    :
Tags                                  : {}
AdditionalRegions                     : {}
SslSetting                            : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSslSetting
Identity                              : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentity
EnableClientCertificate               :
Zone                                  :
DisableGateway                        : False
MinimalControlPlaneApiVersion         :
PublicIpAddressId                     :
PlatformVersion                       : stv2
PublicNetworkAccess                   : Enabled
PrivateEndpointConnections            :
ResourceGroupName                     : ContosoGroup02
```

Perintah ini memulihkan layanan API Management menggunakan kredensial Identitas Terkelola APIM yang diizinkan sebagai StorageBlobContributor di Akun Azure Storage`apimbackupmsi`

## PARAMETERS

### -AccessType

Jenis akses yang akan digunakan untuk akun penyimpanan. Nilai defaultnya adalah AccessKey.

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

### -IdentityClientId

ID Klien identitas terkelola yang ditetapkan pengguna. Diperlukan hanya jika accessType diatur ke UserAssignedManagedIdentity.

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

### -Name

Menentukan nama instans API Management yang akan dipulihkan dengan cadangan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Mengembalikan objek yang mewakili item tempat Anda bekerja.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

Menentukan nama grup sumber daya tempat API Management ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceBlobName

Menentukan nama blob sumber cadangan penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceContainerName

Menentukan nama kontainer sumber cadangan penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext

Menentukan konteks koneksi penyimpanan.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Backup-AzApiManagement](./Backup-AzApiManagement.md)

[Get-AzApiManagement](./Get-AzApiManagement.md)

[New-AzApiManagement](./New-AzApiManagement.md)

[Remove-AzApiManagement](./Remove-AzApiManagement.md)
