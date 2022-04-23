---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
Module Name: AzureRM.DataLakeStore
ms.assetid: ECA70C6C-E0B0-445D-BCAD-041625FAC632
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datalakestore/get-azurermdatalakestoreitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataLakeStore/Commands.DataLakeStore/help/Get-AzureRmDataLakeStoreItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataLakeStore/Commands.DataLakeStore/help/Get-AzureRmDataLakeStoreItem.md
ms.openlocfilehash: a1e70286364fea53062a75b7ac886834803c3674
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143108261"
---
# Get-AzureRmDataLakeStoreItem

## SYNOPSIS
Mendapatkan detail file atau folder di Data Lake Store.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmDataLakeStoreItem [-Account] <String> [-Path] <DataLakeStorePathInstance>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDataLakeStoreItem** mendapatkan detail file atau folder di Data Lake Store.

## EXAMPLES

### Contoh 1: Mendapatkan detail file dari Data Lake Store
```
PS C:\>Get-AzureRmDataLakeStoreItem -AccountName "ContosoADL" -Path "/MyFiles/Test.csv"
```

Perintah ini mendapatkan detail file Test.csv dari Data Lake Store.

## PARAMETERS

### -Akun
Menentukan nama akun Penyimpanan Data Lake.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Jalur
Menentukan jalur Penyimpanan Data Lake untuk mendapatkan detail item, dimulai dengan direktori akar (/).

```yaml
Type: Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStorePathInstance

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreItem

## NOTES

## RELATED LINKS

[Ekspor-AzureRmDataLakeStoreItem](./Export-AzureRmDataLakeStoreItem.md)

[Get-AzureRmDataLakeStoreChildItem](./Get-AzureRmDataLakeStoreChildItem.md)

[Import-AzureRmDataLakeStoreItem](./Import-AzureRmDataLakeStoreItem.md)

[Join-AzureRmDataLakeStoreItem](./Join-AzureRmDataLakeStoreItem.md)

[Move-AzureRmDataLakeStoreItem](./Move-AzureRmDataLakeStoreItem.md)

[New-AzureRmDataLakeStoreItem](./New-AzureRmDataLakeStoreItem.md)

[Hapus-AzureRmDataLakeStoreItem](./Remove-AzureRmDataLakeStoreItem.md)

[Uji-AzureRmDataLakeStoreItem](./Test-AzureRmDataLakeStoreItem.md)


