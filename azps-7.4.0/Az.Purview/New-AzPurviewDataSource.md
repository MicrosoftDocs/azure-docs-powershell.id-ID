---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/new-azpurviewdatasource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewDataSource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewDataSource.md
ms.openlocfilehash: dad9da7be6e88572055250b36df9596eb7ef9218
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142175417"
---
# New-AzPurviewDataSource

## SYNOPSIS
Membuat atau Memperbarui sumber data

## SYNTAX

```
New-AzPurviewDataSource -Endpoint <String> -Name <String> -Body <IDataSource> [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui sumber data

## EXAMPLES

### Contoh 1: Membuat sumber data
```powershell
PS C:\> $obj = New-AzPurviewAzureStorageDataSourceObject -Kind 'AzureStorage' -CollectionReferenceName parv-brs-2 -CollectionType 'CollectionReference' -Endpoint https://datascantest.blob.core.windows.net/
New-AzPurviewDataSource -Endpoint 'https://parv-brs-2.purview.azure.com/' -Name 'NewDataSource' -Body $obj

CollectionLastModifiedAt : 2/15/2022 10:36:25 AM
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                : 2/15/2022 10:36:25 AM
Endpoint                 : https://datascantest.blob.core.windows.net/
Id                       : datasources/NewDataSource
Kind                     : AzureStorage
LastModifiedAt           : 2/15/2022 10:36:25 AM
Location                 :
Name                     : NewDataSource
ResourceGroup            :
ResourceName             :
Scan                     :
SubscriptionId           :
```

Membuat sumber data bernama 'NewDataSource'

## PARAMETERS

### -Isi
.
Untuk membangun, lihat bagian CATATAN untuk properti BODY dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IDataSource
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -Nama
.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DataSourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IDataSource

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IDataSource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TUBUH <IDataSource>: .
  - `Kind <DataSourceType>`: 

## RELATED LINKS
