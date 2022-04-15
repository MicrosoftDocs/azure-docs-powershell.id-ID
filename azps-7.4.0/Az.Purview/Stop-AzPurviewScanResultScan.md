---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/stop-azpurviewscanresultscan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Stop-AzPurviewScanResultScan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Stop-AzPurviewScanResultScan.md
ms.openlocfilehash: 220103207f29f6c9dcbb2acd574f2e92c73146d3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142430337"
---
# Stop-AzPurviewScanResultScan

## SYNOPSIS
Membatalkan pemindaian

## SYNTAX

```
Stop-AzPurviewScanResultScan -Endpoint <String> -DataSourceName <String> -RunId <String> -ScanName <String>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membatalkan pemindaian

## EXAMPLES

### Contoh 1: Menghentikan pemindaian yang dijalankan dengan menjalankan id
```powershell
PS C:\> Stop-AzPurviewScanResultScan -Endpoint 'https://parv-brs-2.purview.azure.com/' -DataSourceName 'DataScanTestData-Parv' -ScanName 'Scan1ForDemo' -RunId '663623f3-8728-4b10-b5c8-8ed8dbc2ae7e'

EndTime ScanResultId StartTime            Status
------- ------------ ---------            ------
                     2/15/2022 2:47:55 PM Accepted
```

Hentikan pemindaian dengan menjalankan id '663623f3-8728-4b10-b5c8-8ed8dbc2ae7e'

## PARAMETERS

### -DataSourceName
.

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

### -RunId
.

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

### -ScanName
.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IOperationResponse

## CATATAN

ALIAS

## RELATED LINKS
