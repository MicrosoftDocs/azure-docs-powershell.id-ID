---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewsystemscanruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewSystemScanRuleset.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewSystemScanRuleset.md
ms.openlocfilehash: e6e94791e42594ac43e2227993f6b2471927b219
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144725418"
---
# Get-AzPurviewSystemScanRuleset

## SYNOPSIS
Mendapatkan aturan pemindaian sistem untuk sumber data

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewsystemscanruleset) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzPurviewSystemScanRuleset -Endpoint <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get1
```
Get-AzPurviewSystemScanRuleset -Endpoint <String> [-DataSourceType <DataSourceType>] -Version <Int32>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzPurviewSystemScanRuleset -Endpoint <String> -DataSourceType <DataSourceType> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan aturan pemindaian sistem untuk sumber data

## EXAMPLES

### Contoh 1: Mendapatkan semua scanruleset sistem
```powershell
PS C:\> Get-AzPurviewSystemScanRuleset -Endpoint https://parv-brs-2.purview.azure.com/

Id                : systemscanrulesets/AmazonMySql
Kind              : AmazonMySql
Name              : AmazonMySql
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 2

Id                : systemscanrulesets/AzureMySql
Kind              : AzureMySql
Name              : AzureMySql
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 2

Id                : systemscanrulesets/AmazonPostgreSql
Kind              : AmazonPostgreSql
Name              : AmazonPostgreSql
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 2

Id                : systemscanrulesets/Teradata
Kind              : Teradata
Name              : Teradata
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 1
```

Mendapatkan semua scanruleset sistem

### Contoh 2: Mendapatkan scanruleset sistem untuk jenis sumber data
```powershell
PS C:\> Get-AzPurviewSystemScanRuleset -Endpoint https://parv-brs-2.purview.azure.com/  -DataSourceType 'AdlsGen2'

Id                : systemscanrulesets/AdlsGen2
Kind              : AdlsGen2
Name              : AdlsGen2
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 3
```

Mendapatkan scanruleset sistem untuk jenis sumber data

### Contoh 2: Mendapatkan scanruleset sistem untuk jenis sumber data dan versi tertentu
```powershell
PS C:\>  Get-AzPurviewSystemScanRuleset -Endpoint https://parv-brs-2.purview.azure.com/  -DataSourceType 'AdlsGen2' -Version 2

Id                : systemscanrulesets/AdlsGen2
Kind              : AdlsGen2
Name              : AdlsGen2
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 2
```

Mendapatkan scanruleset sistem untuk jenis sumber data dan versi tertentu

## PARAMETERS

### -DataSourceType
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DataSourceType
Parameter Sets: Get1
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DataSourceType
Parameter Sets: Get
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

### -Versi
.

```yaml
Type: System.Int32
Parameter Sets: Get1
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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.ISystemScanRuleset

## NOTES

ALIAS

## RELATED LINKS
