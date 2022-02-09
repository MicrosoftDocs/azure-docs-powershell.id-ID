---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdblocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBLocation.md
ms.openlocfilehash: 879245ab5dfa22c4b98ce8179afa1f04eb7458d8
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138168102"
---
# Get-AzCosmosDBLocation

## SYNOPSIS
Mencantumkan lokasi DB Azure Cosmos dan propertinya.
Dapatkan properti lokasi Azure Cosmos DB untuk lokasi tertentu.

## SYNTAX

```
Get-AzCosmosDBLocation [-Location <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
List Azure Cosmos DB lokasi dengan properti lokasi mereka. Fitur ini menyertakan Id Lokasi, Nama, Tipe, SupportsAvailabilityZone, IsBacacyRestricted dan BackupStorageRedundancies.

## EXAMPLES

### Contoh 1
```powershell
Get Azure Cosmos DB Account Location Properties for Given Location

PS C:\> Get-AzCosmosDBLocation -Location "Central US"

Id                                                                                                      Name       Type                           Properties
--                                                                                                      ----       ----                           ----------
subscriptionId/subscriptionId/providers/Microsoft.DocumentDB/locations/centralus/ Central US Microsoft.DocumentDB/locations Microsoft.Azure.Commands.CosmosDB.Models.PSLocationP...


PS C:\> Get-AzCosmosDBLocation -Location "Central US" | ConvertTo-Json
{
    "Id":  "subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/centralus/",
    "Name":  "Central US",
    "Type":  "Microsoft.DocumentDB/locations",
    "Properties":  {
                       "SupportsAvailabilityZone":  true,
                       "IsResidencyRestricted":  false,
                       "BackupStorageRedundancies":  [
                                                         "Geo",
                                                         "Zone",
                                                         "Local"
                                                     ]
                   }
}
```

### Contoh 2
```powershell
List Azure Cosmos DB Account Locations and their properties

PS C:\> Get-AzCosmosDBLocation

Id                                                                                                               Name                 Type                           Properties
--                                                                                                               ----                 ----                           ----------
subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/brazilsoutheast/    Brazil Southeast     Microsoft.DocumentDB/locations Microsoft.Azure.Commands.CosmosDB...
subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/centralus/          Central US           Microsoft.DocumentDB/locations Microsoft.Azure.Commands.CosmosDB...
....


PS C:\> Get-AzCosmosDBLocation | ConvertTo-Json
[
    {
        "Id":  "subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/brazilsoutheast/",
        "Name":  "Brazil Southeast",
        "Type":  "Microsoft.DocumentDB/locations",
        "Properties":  {
                           "SupportsAvailabilityZone":  true,
                           "IsResidencyRestricted":  false,
                           "BackupStorageRedundancies":  "Geo Local"
                       }
    },
    {
        "Id":  "subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/centralus/",
        "Name":  "Central US",
        "Type":  "Microsoft.DocumentDB/locations",
        "Properties":  {
                           "SupportsAvailabilityZone":  true,
                           "IsResidencyRestricted":  false,
                           "BackupStorageRedundancies":  "Geo Zone Local"
                       }
    },
    {
        "Id":  "subscriptionId/<subscriptionId>/providers/Microsoft.DocumentDB/locations/australiasoutheast/",
        "Name":  "Australia Southeast",
        "Type":  "Microsoft.DocumentDB/locations",
        "Properties":  {
                           "SupportsAvailabilityZone":  false,
                           "IsResidencyRestricted":  false,
                           "BackupStorageRedundancies":  "Geo Local"
                       }
    }
]
```

## PARAMETERS

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

### -Lokasi
-Nama Lokasi dalam string.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSLocationGetResult

## CATATAN

## RELATED LINKS
