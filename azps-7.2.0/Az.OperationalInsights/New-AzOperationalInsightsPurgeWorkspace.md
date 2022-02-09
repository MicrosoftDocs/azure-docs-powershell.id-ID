---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/New-AzOperationalInsightsPurgeWorkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsPurgeWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsPurgeWorkspace.md
ms.openlocfilehash: 19bc32b0627ecec3e26ef7fc91b60d6887cc67be
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138162255"
---
# New-AzOperationalInsightsPurgeWorkspace

## SYNOPSIS
Membersihkan data di ruang kerja Analitik Log dengan serangkaian filter yang ditentukan pengguna

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
Membersihkan data di ruang kerja Analitik Log dengan serangkaian filter yang ditentukan pengguna

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzOperationalInsightsPurgeWorkspace -ResourceGroupName dabenham-dev -WorkspaceName dabenham-troubleShootingE2E -Column "Column_Name" -OperatorProperty "Operator" -Value "Value" -key "Key" -Table "Table_Name"
```

Membersihkan data di tabel ruang kerja Analitik Log

## PARAMETERS

### -Column
Kolom tabel tempat kueri akan dijalankan

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
Jangan minta konfirmasi.

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

### -Key
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
Operator yang didukung adalah ==, =~, in, in~, \>, \>=, \<, \<=, between, dan memiliki perilaku yang sama seperti dalam kueri KQL.

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

### -Purge Body
Menentukan tabel dan filter yang akan di membersihkan.

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

### -Table
Nama tabel untuk membersihkan data.

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

### -Value
nilai untuk operator agar berfungsi.
Dapat juga angka (misalnya, \> 100), string (timestamp \>= '2017-09-01') atau array nilai.

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
Nama ruang kerja untuk membersihkan.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Object

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurge Body

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspacePurgeResponse

## CATATAN

## RELATED LINKS
