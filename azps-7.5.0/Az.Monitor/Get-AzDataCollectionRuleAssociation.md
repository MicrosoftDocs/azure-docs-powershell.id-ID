---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azdatacollectionruleassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzDataCollectionRuleAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzDataCollectionRuleAssociation.md
ms.openlocfilehash: e3f9d24d7f92778aa833355619eac4d7eeaed968
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145776325"
---
# Get-AzDataCollectionRuleAssociation

## SYNOPSIS
Mendapatkan asosiasi aturan pengumpulan data.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/get-azdatacollectionruleassociation) untuk informasi terbaru.

## SYNTAX

### ByAssociatedResource (Default)
```
Get-AzDataCollectionRuleAssociation 
   -TargetResourceId <string> 
   [-DefaultProfile <IAzureContextContainer>]
   [<CommonParameters>]
```

### ByName
```
Get-AzDataCollectionRuleAssociation 
   -TargetResourceId <string> 
   -AssociationName <string> 
   [-DefaultProfile <IAzureContextContainer>] 
   [<CommonParameters>]
```

### ByRule
```
Get-AzDataCollectionRuleAssociation 
   -ResourceGroupName <string> 
   -RuleName <string> 
   [-DefaultProfile <IAzureContextContainer>]
   [<CommonParameters>]
```

### ByInputObject
```
Get-AzDataCollectionRuleAssociation 
   -InputObject <PSDataCollectionRuleResource> 
   [-DefaultProfile <IAzureContextContainer>]
   [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataCollectionRuleAssociation** mendapatkan satu atau beberapa asosiasi aturan pengumpulan data (DCRA).

Untuk menerapkan DCR ke komputer virtual, Anda membuat asosiasi untuk komputer virtual. Komputer virtual mungkin memiliki asosiasi ke beberapa DCR, dan DCR mungkin memiliki beberapa komputer virtual yang terkait dengannya. Ini memungkinkan Anda untuk mendefinisikan satu set DCR, masing-masing cocok dengan persyaratan tertentu, dan menerapkannya hanya untuk komputer virtual yang menerapkannya. Berikut adalah artikel ["Mengonfigurasi pengumpulan data untuk agen Azure Monitor"](https://docs.microsoft.com/azure/azure-monitor/platform/data-collection-rule-azure-monitor-agent) menggunakan DCRA.

## EXAMPLES

### Contoh 1: Mendapatkan asosiasi aturan pengumpulan data berdasarkan ID sumber daya target (komputer virtual terkait)
```powershell
$vm = Get-AzVM -ResourceGroupName $rg -Name $vmName
Get-AzDataCollectionRuleAssociation -TargetResourceId $vm.Id
```

```output
Description          :
DataCollectionRuleId : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.I
                       nsights/dataCollectionRules/{dcrName}
ProvisioningState    :
Etag                 : "{etag}"
Id                   : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.C
                       ompute/virtualMachines/{vmName}/providers/Microsoft.Insights/dataCollectionRuleAssociations/{assocName}
Name                 : {assocName}
Type                 : Microsoft.Insights/dataCollectionRuleAssociations
```

Perintah ini mencantumkan semua aturan pengumpulan data untuk ID sumber daya target (komputer virtual) yang diberikan.

### Contoh 2: Mendapatkan asosiasi aturan pengumpulan data berdasarkan aturan (DCR)
```powershell
Get-AzDataCollectionRuleAssociation -ResourceGroup $rg -RuleName $dcrName
```

```output
Description          :
DataCollectionRuleId : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.I
                       nsights/dataCollectionRules/{dcrName}
ProvisioningState    :
Etag                 : "{etag}"
Id                   : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.C
                       ompute/virtualMachines/{vmName}/providers/Microsoft.Insights/dataCollectionRuleAssociations/{assocName}
Name                 : {assocName}
Type                 : Microsoft.Insights/dataCollectionRuleAssociations
```

Perintah ini mencantumkan asosiasi aturan pengumpulan data untuk grup sumber daya dan aturan (DCR) yang diberikan.

### Contoh 3: Mendapatkan asosiasi aturan pengumpulan data berdasarkan objek input (PSDataCollectionRuleResource)
```powershell
$dcr = Get-AzDataCollectionRule -ResourceGroupName $rg -RuleName $dcrName
$dcr | Get-AzDataCollectionRuleAssociation
```

```output
Description          :
DataCollectionRuleId : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.I
                       nsights/dataCollectionRules/{dcrName}
ProvisioningState    :
Etag                 : "{etag}"
Id                   : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.C
                       ompute/virtualMachines/{vmName}/providers/Microsoft.Insights/dataCollectionRuleAssociations/{assocName}
Name                 : {assocName}
Type                 : Microsoft.Insights/dataCollectionRuleAssociations
```

Perintah ini mencantumkan asosiasi aturan pengumpulan data untuk objek input yang diberikan.

### Contoh 4: Mendapatkan asosiasi aturan pengumpulan data berdasarkan ID sumber daya target (komputer virtual terkait) dan nama asosiasi
```powershell
Get-AzDataCollectionRuleAssociation -TargetResourceId $vm.Id -AssociationName $assocName
```

```output
Description          :
DataCollectionRuleId : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.I
                       nsights/dataCollectionRules/{dcrName}
ProvisioningState    :
Etag                 : "{etag}"
Id                   : /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.C
                       ompute/virtualMachines/{vmName}/providers/Microsoft.Insights/dataCollectionRuleAssociations/{assocName}
Name                 : {assocName}
Type                 : Microsoft.Insights/dataCollectionRuleAssociations
```

Perintah ini mencantumkan satu (daftar dengan satu elemen) asosiasi aturan pengumpulan data.

## PARAMETERS

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

### -TargetResourceId
ID sumber daya terkait

```yaml
Type: System.String
Parameter Sets: ByAssociatedResource (Default)
Aliases: ResourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: ResourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: ByRule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RuleName
Nama aturan pengumpulan data

```yaml
Type: System.String
Parameter Sets: ByRule
Aliases: DataCollectionRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek PSDataCollectionRuleResource

```yaml
Type: Microsoft.Azure.Commands.Insights.OutputClasses.PSDataCollectionRuleResource
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AssociationName
Nama asosiasi.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String
### Microsoft.Azure.Commands. Insights. OutputClasses.PSDataCollectionRuleResource

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSDataCollectionRuleAssociationProxyOnlyResource

## NOTES

## RELATED LINKS

[Remove-AzDataCollectionRuleAssociation](./Remove-AzDataCollectionRuleAssociation.md)
 [New-AzDataCollectionRuleAssociation](./New-AzDataCollectionRuleAssociation.md)
