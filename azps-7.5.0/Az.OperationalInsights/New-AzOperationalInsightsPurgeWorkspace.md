---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/New-AzOperationalInsightsPurgeWorkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsPurgeWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsPurgeWorkspace.md
ms.openlocfilehash: cd56f20dc7a02407aa8a9620d16b42dcedcb30d7
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144235431"
---
# New-AzOperationalInsightsPurgeWorkspace

## SYNOPSIS
Menghapus menyeluruh data di ruang kerja Analitik Log oleh sekumpulan filter yang ditentukan pengguna

## SYNTAX

### CreateByNameParameterSet (Default)
```
New-AzOperationalInsightsPurgeWorkspace [-ResourceGroupName] <String> [-WorkspaceName] <String>
 -Column <String> -OperatorProperty <String> [-Value <Object>] [-Key <String>] -Table <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateByObjectParameterSet
```
New-AzOperationalInsightsPurgeWorkspace [-ResourceGroupName] <String> [-WorkspaceName] <String>
 -PurgeBody <PSWorkspacePurgeBody> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Menghapus menyeluruh data di ruang kerja Analitik Log oleh sekumpulan filter yang ditentukan pengguna

## EXAMPLES

### Contoh 1
```powershell
New-AzOperationalInsightsPurgeWorkspace -ResourceGroupName dabenham-dev -WorkspaceName dabenham-troubleShootingE2E -Column "Column_Name" -OperatorProperty "Operator" -Value "Value" -key "Key" -Table "Table_Name"
```

Menghapus menyeluruh data dalam tabel ruang kerja Analitik Log

## PARAMETERS

### -Kolom
Kolom tabel tempat kueri yang diberikan harus dijalankan

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Jangan meminta konfirmasi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kunci
Saat memfilter dimensi kustom, kunci ini akan digunakan sebagai nama dimensi kustom.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OperatorProperty
Operator kueri untuk mengevaluasi kolom dan nilai yang disediakan.
Operator yang didukung adalah ==, =~, in, in~, \>, \>=, \<, \<=, between, dan memiliki perilaku yang sama seperti yang mereka lakukan dalam kueri KQL.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PurgeBody
Menentukan tabel dan filter yang akan dibersihkan.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurgeBody
Parameter Sets: CreateByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: CreateByObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tabel
Nama tabel untuk menghapus data secara menyeluruh.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nilai
nilai bagi operator untuk berfungsi.
Ini bisa berupa angka (misalnya, \> 100), string (tanda \>waktu = '2017-09-01') atau array nilai.

```yaml
Type: System.Object
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja yang akan dibersihkan.

```yaml
Type: System.String
Parameter Sets: CreateByNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: CreateByObjectParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Object

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurgeBody

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurgeResponse

## NOTES

## RELATED LINKS
