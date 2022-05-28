---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 5846BBB7-DA8E-41B5-A894-BA2B61C2212C
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/backup-azapimanagement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Backup-AzApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Backup-AzApiManagement.md
ms.openlocfilehash: 6f7b547b704fb82a2716de88de3d57aebc17d13e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145544021"
---
# Backup-AzApiManagement

## SYNOPSIS

Mencadangkan layanan API Management.

## SYNTAX

```
Backup-AzApiManagement -ResourceGroupName <String> -Name <String> -StorageContext <IStorageContext>
 -TargetContainerName <String> [-TargetBlobName <String>] [-AccessType <String>] [-IdentityClientId <String>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Backup-AzApiManagement** mencadangkan instans layanan Azure API Management.
Cmdlet ini menyimpan cadangan sebagai blob Azure Storage.

## EXAMPLES

### Contoh 1: Mencadangkan layanan API Management

```powershell
New-AzStorageAccount -StorageAccountName "ContosoStorage" -Location $location -ResourceGroupName "ContosoGroup02" -Type Standard_LRS
$storageKey = (Get-AzStorageAccountKey -ResourceGroupName "ContosoGroup02" -StorageAccountName "ContosoStorage")[0].Value
$storageContext = New-AzStorageContext -StorageAccountName "ContosoStorage" -StorageAccountKey $storageKey
Backup-AzApiManagement -ResourceGroupName "ContosoGroup02" -Name "ContosoApi" -StorageContext $StorageContext -TargetContainerName "ContosoBackups" -TargetBlobName "ContosoBackup.apimbackup"
```

### Contoh 2: Mencadangkan menggunakan Identitas Terkelola

```powershell
PS D:> $storageContext=New-AzStorageContext -StorageAccountName apimbackupmsi
PS D:> $resourceGroupName="contosogroup2";
PS D:> $apiManagementName="contosoapi";
PS D:> $containerName="apimbackupcontainer";
PS D:> $backupName="test-sdk-backup-1";
PS D:> $msiClientId="a6270d0c-7d86-478b-8cbe-dc9047ba54f7"
PS D:> Backup-AzApiManagement -ResourceGroupName $resourceGroupName -Name $apiManagementName -StorageContext $storageContext -TargetContainerName $containerName -TargetBlobName $backupName -AccessType "UserAssignedManagedIdentity" -IdentityClientId $msiClientId -PassThru

PublicIPAddresses                     : {52.143.79.150}
PrivateIPAddresses                    :
Id                                    : /subscriptions/4f5285a3-9fd7-40ad-91b1-d8fc3823983d/resourceGroups/contosogroup2/providers/Microsoft.ApiManagement/service/contosoapi
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
ResourceGroupName                     : contosogroup2
```

Perintah ini mencadangkan layanan API Management ke blob Storage menggunakan UserAssigned Managed Identity

## PARAMETERS

### -AccessType

Jenis akses yang akan digunakan untuk akun penyimpanan.

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

Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

Menentukan nama penyebaran API Management yang dicadangkan cmdlet ini.

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

Menunjukkan bahwa cmdlet ini mengembalikan objek **PsApiManagement** yang dicadangkan, jika operasi berhasil.

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

Menentukan nama grup sumber daya tempat penyebaran API Management berada.

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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetBlobName

Menentukan nama blob untuk cadangan.
Jika blob tidak ada, cmdlet ini akan membuatnya.
Cmdlet ini menghasilkan nilai default berdasarkan pola berikut: {Name}-{yyyy-MM-dd-HH-mm}.apimbackup

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

### -TargetContainerName

Menentukan nama kontainer blob untuk cadangan.
Jika kontainer tidak ada, cmdlet ini akan membuatnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Get-AzApiManagement](./Get-AzApiManagement.md)

[New-AzApiManagement](./New-AzApiManagement.md)

[Remove-AzApiManagement](./Remove-AzApiManagement.md)

[Restore-AzApiManagement](./Restore-AzApiManagement.md)
