---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewscanresultscanhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewScanResultScanHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewScanResultScanHistory.md
ms.openlocfilehash: 2a98d5e9e1ecb45fc87a54af9711096ea4250053
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145656455"
---
# Get-AzPurviewScanResultScanHistory

## SYNOPSIS
Mencantumkan riwayat pemindaian pemindaian

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewscanresultscanhistory) untuk informasi terbaru.

## SYNTAX

```
Get-AzPurviewScanResultScanHistory -Endpoint <String> -DataSourceName <String> -ScanName <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan riwayat pemindaian pemindaian

## EXAMPLES

### Contoh 1: Mencantumkan semua eksekusi pemindaian dalam instans pemindaian sumber data
```powershell
PS C:\> Get-AzPurviewScanResultScanHistory -Endpoint 'https://parv-brs-2.purview.azure.com/' -DataSourceName 'DataScanTestData-Parv' -ScanName 'Scan1ForDemo' | fl

AssetsClassified            : 62
AssetsDiscovered            : 97
Code                        :
DataSourceType              : AzureStorage
Detail                      :
DiagnosticExceptionCountMap : {
                              }
DiagnosticNotification      : {}
EndTime                     : 2/15/2022 2:42:22 PM
ErrorMessage                :
Id                          : 758a0499-b45e-40e3-9c06-408e2f3ac050
Message                     :
ParentId                    :
PipelineStartTime           : 2/15/2022 2:36:21 PM
QueuedTime                  : 2/15/2022 2:34:06 PM
ResourceId                  : /subscriptions/xxxxxxxx-ffc5-465d-b5dd-xxxxxxxx/resourceGroups/datascan-dev-tests/providers/Microsoft.Storage/storageAccounts/datascan
RunType                     : Manual
ScanLevelType               : Full
ScanRulesetType             : System
ScanRulesetVersion          : 4
StartTime                   : 2/15/2022 2:34:06 PM
Status                      : Succeeded
Target                      :

AssetsClassified            : 62
AssetsDiscovered            : 97
Code                        :
DataSourceType              : AzureStorage
Detail                      :
DiagnosticExceptionCountMap : {
                              }
DiagnosticNotification      : {}
EndTime                     : 2/13/2022 3:23:53 PM
ErrorMessage                :
Id                          : a81d7a0f-149b-4c57-80ae-0f4640ee5a29
Message                     :
ParentId                    :
PipelineStartTime           : 2/13/2022 3:17:02 PM
QueuedTime                  : 2/13/2022 3:16:34 PM
ResourceId                  : /subscriptions/xxxxxxxx-ffc5-465d-b5dd-xxxxxxxx/resourceGroups/datascan-dev-tests/providers/Microsoft.Storage/storageAccounts/datascan
RunType                     : Manual
ScanLevelType               : Full
ScanRulesetType             : System
ScanRulesetVersion          : 4
StartTime                   : 2/13/2022 3:16:34 PM
Status                      : Succeeded
Target                      :
```

Mencantumkan semua eksekusi pemindaian dalam instans pemindaian sumber data

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IScanResult

## NOTES

ALIAS

## RELATED LINKS
