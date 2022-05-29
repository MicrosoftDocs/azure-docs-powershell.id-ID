---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeStore.dll-Help.xml
Module Name: Az.DataLakeStore
ms.assetid: D79080D5-2785-4C46-86FD-FDAA11117D17
online version: https://docs.microsoft.com/powershell/module/az.datalakestore/get-azdatalakestoretrustedidprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Get-AzDataLakeStoreTrustedIdProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Get-AzDataLakeStoreTrustedIdProvider.md
ms.openlocfilehash: 07aa05947b5947ee8f768595b9938ee0bea22326
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145784836"
---
# Get-AzDataLakeStoreTrustedIdProvider

## SYNOPSIS
Mendapatkan IdP tepercaya yang ditentukan di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, maka daftar semua penyedia untuk akun tersebut.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datalakestore/get-azdatalakestoretrustedidprovider) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataLakeStoreTrustedIdProvider [-Account] <String> [[-Name] <String>] [[-ResourceGroupName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataLakeStoreTrustedIdProvider** mendapatkan IdP tepercaya yang ditentukan di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, maka daftar semua penyedia untuk akun tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan IdP tepercaya tertentu
```powershell
Get-AzDataLakeStoreTrustedIdProvider -AccountName "ContosoADL" -Name MyProvider
```

Mengembalikan penyedia bernama "MyProvider" dari akun "ContosoADL"

### Contoh 2: Mencantumkan semua penyedia dalam akun
```powershell
Get-AzDataLakeStoreTrustedIdProvider -AccountName "ContosoADL"
```

Mencantumkan semua penyedia di bawah akun "ContosoADL"

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Name
Nama IdP tepercaya yang akan diambil

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
Nama grup sumber daya di mana ingin mengambil idP tepercaya yang ditentukan dari akun yang ditentukan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreTrustedIdProvider

## NOTES

## RELATED LINKS
