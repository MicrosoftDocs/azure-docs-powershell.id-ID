---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
Module Name: AzureRM.DataLakeStore
ms.assetid: D79080D5-2785-4C46-86FD-FDAA11117D17
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datalakestore/get-azurermdatalakestoretrustedidprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataLakeStore/Commands.DataLakeStore/help/Get-AzureRmDataLakeStoreTrustedIdProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataLakeStore/Commands.DataLakeStore/help/Get-AzureRmDataLakeStoreTrustedIdProvider.md
ms.openlocfilehash: 28b38ed27306619404caf1c1a963a77b421f591ea3871100054ba631e5914c05
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140857412"
---
# Get-AzureRmDataLakeStoreTrustedIdProvider

## SYNOPSIS
Mendapatkan penyedia identitas tepercaya yang ditentukan di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, daftar semua penyedia untuk akun tersebut.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmDataLakeStoreTrustedIdProvider [-Account] <String> [[-Name] <String>]
 [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDataLakeStoreTrustedIdProvider** mendapatkan penyedia identitas tepercaya tertentu di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, daftar semua penyedia untuk akun tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan penyedia identitas tepercaya tertentu
```
PS C:\> Get-AzureRmDataLakeStoreTrustedIdProvider -AccountName "ContosoADL" -Name MyProvider
```

Mengembalikan penyedia bernama "MyProvider" dari akun "ContosoADL"

### Contoh 2: Mencantumkan semua penyedia dalam akun
```
PS C:\> Get-AzureRmDataLakeStoreTrustedIdProvider -AccountName "ContosoADL"
```

Daftar semua penyedia di bawah akun "ContosoADL"

## PARAMETERS

### -Akun
Akun Data Lake Store untuk mengambil penyedia identitas tepercaya dari

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama penyedia identitas tepercaya untuk diambil

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya di mana Anda ingin mengambil penyedia identitas tepercaya yang ditentukan oleh akun tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreTrustedIdProvider

## CATATAN

## RELATED LINKS
