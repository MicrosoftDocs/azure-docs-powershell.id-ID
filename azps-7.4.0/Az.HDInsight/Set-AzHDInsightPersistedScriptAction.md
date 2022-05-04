---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: 92F21752-4FB6-4162-B542-DA25ACA3340B
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/set-azhdinsightpersistedscriptaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Set-AzHDInsightPersistedScriptAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Set-AzHDInsightPersistedScriptAction.md
ms.openlocfilehash: f99d2dda1603492b5215eb348b27d0bdaecc8dfe
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144614048"
---
# Set-AzHDInsightPersistedScriptAction

## SYNOPSIS
Mengatur tindakan skrip yang dijalankan sebelumnya menjadi tindakan skrip yang dipertahankan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/set-azhdinsightpersistedscriptaction) untuk informasi terbaru.

## SYNTAX

```
Set-AzHDInsightPersistedScriptAction [-ClusterName] <String> [-ScriptExecutionId] <Int64>
 [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzHDInsightPersistedScriptAction** menetapkan tindakan skrip yang dijalankan sebelumnya menjadi tindakan skrip yang bertahan.
Tindakan skrip yang ditentukan sebelumnya harus berhasil.
Tindakan skrip akan berjalan setiap kali kluster Azure HDInsight ditingkatkan skalanya.

## EXAMPLES

### Contoh 1: Atur tindakan skrip yang berhasil sebelumnya untuk dipertahankan, atau jalankan pada peningkatan skala kluster
```powershell
Set-AzHDInsightPersistedScriptAction `
            -ClusterName "your-hadoop-001" `
            -ScriptExecutionId "<id>"
```

Perintah ini menetapkan tindakan skrip yang berhasil sebelumnya menjadi tindakan skrip yang bertahan.

## PARAMETERS

### -ClusterName
Menentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptExecutionId
Menentukan ID eksekusi tindakan skrip untuk dipromosikan ke bertahan.
Tindakan skrip ini harus berhasil untuk dipromosikan.
Anda dapat menemukan ID eksekusi tindakan skrip menggunakan Get-AzHDInsightScriptActionHistory.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzHDInsightPersistedScriptAction](./Get-AzHDInsightPersistedScriptAction.md)

[Remove-AzHDInsightPersistedScriptAction](./Remove-AzHDInsightPersistedScriptAction.md)


