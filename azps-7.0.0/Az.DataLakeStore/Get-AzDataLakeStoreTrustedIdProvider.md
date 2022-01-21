---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeStore.dll-Help.xml
Module Name: Az.DataLakeStore
ms.assetid: D79080D5-2785-4C46-86FD-FDAA11117D17
online version: https://docs.microsoft.com/powershell/module/az.datalakestore/get-azdatalakestoretrustedidprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Get-AzDataLakeStoreTrustedIdProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeStore/DataLakeStore/help/Get-AzDataLakeStoreTrustedIdProvider.md
ms.openlocfilehash: 30e6eb8bf4704fb20f698e9a76d7307b1517f1ed
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136544789"
---
# Get-AzDataLakeStoreTrustedIdProvider

## SYNOPSIS
Mendapatkan penyedia identitas tepercaya yang ditentukan di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, daftar semua penyedia untuk akun tersebut.

## SYNTAX

```
Get-AzDataLakeStoreTrustedIdProvider [-Account] <String> [[-Name] <String>] [[-ResourceGroupName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataLakeStoreTrustedIdProvider** mendapatkan penyedia identitas tepercaya tertentu di Data Lake Store yang ditentukan.
Jika tidak ada penyedia yang ditentukan, daftar semua penyedia untuk akun tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan penyedia identitas tepercaya tertentu
```
PS C:\> Get-AzDataLakeStoreTrustedIdProvider -AccountName "ContosoADL" -Name MyProvider
```

Mengembalikan penyedia bernama "MyProvider" dari akun "ContosoADL"

### Contoh 2: Mencantumkan semua penyedia dalam akun
```
PS C:\> Get-AzDataLakeStoreTrustedIdProvider -AccountName "ContosoADL"
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeStore.Models.DataLakeStoreTrustedIdProvider

## CATATAN

## RELATED LINKS
