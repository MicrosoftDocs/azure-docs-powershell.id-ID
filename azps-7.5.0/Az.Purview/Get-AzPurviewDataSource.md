---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewdatasource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewDataSource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewDataSource.md
ms.openlocfilehash: db0b25896c6e999a1c2893e11d801090e8834af0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144231066"
---
# Get-AzPurviewDataSource

## SYNOPSIS
Mendapatkan sumber data

## SYNTAX

### Daftar (Default)
```
Get-AzPurviewDataSource -Endpoint <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzPurviewDataSource -Endpoint <String> -Name <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan sumber data

## EXAMPLES

### Contoh 1: Mendapatkan sumber data berdasarkan nama
```powershell
PS C:\> Get-AzPurviewDataSource -Endpoint 'https://brs-2.purview.azure.com/' -Name 'NewDataSource'

CollectionLastModifiedAt : 2/9/2022 2:49:14 AM
CollectionReferenceName  : brs-2
CollectionType           : CollectionReference
CreatedAt                : 2/9/2022 2:49:14 AM
Endpoint                 : https://data123scantest.blob.core.windows.net/
Id                       : datasources/NewDataSource
Kind                     : AzureStorage
LastModifiedAt           : 2/9/2022 3:02:56 AM
Location                 : westus
Name                     : NewDataSource
ResourceGroup            : rg
ResourceName             : datascantest
Scan                     :
SubscriptionId           : 4348d67b-ffc5-465d-b5dd-xxxxxxxxx
```

Mendapatkan sumber data bernama 'NewDataSource'

### Contoh 2: Mendapatkan semua sumber data
```powershell
PS C:\>  Get-AzPurviewDataSource -Endpoint 'https://brs-2.purview.azure.com/'

CollectionLastModifiedAt : 1/31/2022 10:28:16 AM
CollectionReferenceName  : brs-2
CollectionType           : CollectionReference
CreatedAt                : 1/31/2022 10:28:16 AM
Endpoint                 : https://0cb22aa692584b54b09files.file.core.windows.net/
Id                       : datasources/AzureFileStorage-f1B
Kind                     : AzureFileService
LastModifiedAt           : 1/31/2022 10:28:16 AM
Location                 : westus2
Name                     : AzureFileStorage-f1B
ResourceGroup            : scanning-wus2-df-files
ResourceName             : 0cb22aa692584b54b09files
Scan                     :
SubscriptionId           : aa41bbd9-a6aa-44a8-b5cb-xxxxxxxxx

CollectionLastModifiedAt : 2/9/2022 2:49:14 AM
CollectionReferenceName  : brs-2
CollectionType           : CollectionReference
CreatedAt                : 2/9/2022 2:49:14 AM
Endpoint                 : https://datascan123test.blob.core.windows.net/
Id                       : datasources/NewDataSource
Kind                     : AzureStorage
LastModifiedAt           : 2/9/2022 3:02:56 AM
Location                 : westus
Name                     : NewDataSource
ResourceGroup            : rg
ResourceName             : datascantest
Scan                     :
SubscriptionId           : 4348d67b-ffc5-465d-b5dd-xxxxxxxxx
```

Mendapatkan semua sumber data

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Titik akhir pemindaian akun purview Anda.
Contoh: https://{accountName}.purview.azure.com

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

### -Name
.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DataSourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IDataSource

## NOTES

ALIAS

## RELATED LINKS
