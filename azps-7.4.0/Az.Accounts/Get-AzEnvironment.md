---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azenvironment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzEnvironment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzEnvironment.md
ms.openlocfilehash: 996f841fde24a2cae9ff17df173b53c940df2d72
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142170427"
---
# Get-AzEnvironment

## SYNOPSIS
Dapatkan titik akhir dan metadata untuk contoh layanan Azure.

## SYNTAX

```
Get-AzEnvironment [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEnvironment mendapatkan titik akhir dan metadata untuk contoh layanan Azure.

## EXAMPLES

### Contoh 1: Mendapatkan semua lingkungan Azure
```powershell
Get-AzEnvironment 
```

```Output
Name              Resource Manager Url                  ActiveDirectory Authority          Type
----              --------------------                  -------------------------          ----
AzureUSGovernment https://management.usgovcloudapi.net/ https://login.microsoftonline.us/  Built-in
AzureGermanCloud  https://management.microsoftazure.de/ https://login.microsoftonline.de/  Built-in
AzureCloud        https://management.azure.com/         https://login.microsoftonline.com/ Built-in
AzureChinaCloud   https://management.chinacloudapi.cn/  https://login.chinacloudapi.cn/    Built-in
```

Contoh ini memperlihatkan cara mendapatkan titik akhir dan metadata untuk lingkungan AzureCloud (default).

### Contoh 2: Mendapatkan lingkungan AzureCloud
```powershell
Get-AzEnvironment -Name AzureCloud
```

```Output
Name       Resource Manager Url          ActiveDirectory Authority          Type
----       --------------------          -------------------------          ----
AzureCloud https://management.azure.com/ https://login.microsoftonline.com/ Built-in
```

Contoh ini memperlihatkan cara mendapatkan titik akhir dan metadata untuk lingkungan AzureCloud (default).

### Contoh 3: Mendapatkan lingkungan AzureChinaCloud
```powershell
Get-AzEnvironment -Name AzureChinaCloud | Format-List
```

```Output
Name                                              : AzureChinaCloud
Type                                              : Built-in
EnableAdfsAuthentication                          : False
OnPremise                                         : False
ActiveDirectoryServiceEndpointResourceId          : https://management.core.chinacloudapi.cn/
AdTenant                                          : Common
GalleryUrl                                        : https://gallery.azure.com/
ManagementPortalUrl                               : https://go.microsoft.com/fwlink/?LinkId=301902
ServiceManagementUrl                              : https://management.core.chinacloudapi.cn/
PublishSettingsFileUrl                            : https://go.microsoft.com/fwlink/?LinkID=301776
ResourceManagerUrl                                : https://management.chinacloudapi.cn/
SqlDatabaseDnsSuffix                              : .database.chinacloudapi.cn
StorageEndpointSuffix                             : core.chinacloudapi.cn
ActiveDirectoryAuthority                          : https://login.chinacloudapi.cn/
GraphUrl                                          : https://graph.chinacloudapi.cn/
GraphEndpointResourceId                           : https://graph.chinacloudapi.cn/
TrafficManagerDnsSuffix                           : trafficmanager.cn
AzureKeyVaultDnsSuffix                            : vault.azure.cn
DataLakeEndpointResourceId                        : 
AzureDataLakeStoreFileSystemEndpointSuffix        : 
AzureDataLakeAnalyticsCatalogAndJobEndpointSuffix : 
AzureKeyVaultServiceEndpointResourceId            : https://vault.azure.cn
ContainerRegistryEndpointSuffix                   : azurecr.cn
AzureOperationalInsightsEndpointResourceId        : 
AzureOperationalInsightsEndpoint                  : 
AzureAnalysisServicesEndpointSuffix               : asazure.chinacloudapi.cn
AnalysisServicesEndpointResourceId                : https://region.asazure.chinacloudapi.cn
AzureAttestationServiceEndpointSuffix             : 
AzureAttestationServiceEndpointResourceId         : 
AzureSynapseAnalyticsEndpointSuffix               : dev.azuresynapse.azure.cn
AzureSynapseAnalyticsEndpointResourceId           : https://dev.azuresynapse.azure.cn
```

Contoh ini memperlihatkan cara mendapatkan titik akhir dan metadata untuk lingkungan AzureChinaCloud.

### Contoh 4: Mendapatkan lingkungan AzureUSGovernment
```powershell
Get-AzEnvironment -Name AzureUSGovernment
```

```Output
Name              Resource Manager Url                  ActiveDirectory Authority         Type
----              --------------------                  -------------------------         ----
AzureUSGovernment https://management.usgovcloudapi.net/ https://login.microsoftonline.us/ Built-in
```

Contoh ini memperlihatkan cara mendapatkan titik akhir dan metadata untuk lingkungan AzureUSGovernment.

## PARAMETERS

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

### -Nama
Menentukan nama instans Azure yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAzureEnvironment

## CATATAN

## RELATED LINKS

[Add-AzEnvironment](./Add-AzEnvironment.md)

[Hapus-AzEnvironment](./Remove-AzEnvironment.md)

[Set-AzEnvironment](./Set-AzEnvironment.md)

