---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdblocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBLocation.md
ms.openlocfilehash: 60d5af8febc11575f5d53679ea6085c75a2b532e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143246645"
---
# Get-AzCosmosDBLocation

## SYNOPSIS
Daftar lokasi Azure Cosmos DB dan propertinya.
Dapatkan properti lokasi Azure Cosmos DB untuk lokasi tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdblocation) untuk informasi terbaru.

## SYNTAX

```
Get-AzCosmosDBLocation [-Location <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Daftar lokasi Azure Cosmos DB dengan properti lokasinya. Ini termasuk Id Lokasi, Nama, Tipe, DukunganAvailabilityZone, IsResidencyRestricted dan BackupStorageRedundancies.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSLocationGetResult

## NOTES

## RELATED LINKS
