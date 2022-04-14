---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
Module Name: AzureRM.HDInsight
ms.assetid: 2B7C1B83-EEEA-4BD1-9E9B-1F3070295995
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.hdinsight/get-azurermhdinsightpersistedscriptaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/Get-AzureRmHDInsightPersistedScriptAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/Get-AzureRmHDInsightPersistedScriptAction.md
ms.openlocfilehash: 6305e9a312eb5ebb34de56bcef8a8894b1bd7dd0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142097842"
---
# Get-AzureRmHDInsightPersistedScriptAction

## SYNOPSIS
Mendapatkan tindakan skrip tetap untuk sebuah kluster dan mencantumkannya dalam urutan kronologis, atau mendapatkan detail untuk tindakan skrip tetap tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmHDInsightPersistedScriptAction [-ClusterName] <String> [[-Name] <String>]
 [-ResourceGroupName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmHDInsistedScriptAction** mendapatkan tindakan skrip tetap untuk kluster Azure HDInsight dan mencantumkannya dalam urutan kronologis, atau mendapatkan detail untuk tindakan skrip tetap tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan tindakan skrip yang tetap di kluster
```
PS C:\>Get-AzureRmHDInsightPersistedScriptAction -ClusterName "your-hadoop-001"
```

Perintah ini mendapatkan tindakan skrip tetap pada kluster bernama your-hadoop-001.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama aksi skrip yang tetap.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightRuntimeScriptAction

## CATATAN

## RELATED LINKS

[Remove-AzureRmHDInsightPersistedScriptAction](./Remove-AzureRmHDInsightPersistedScriptAction.md)

[Set-AzureRmHDInsightPersistedScriptAction](./Set-AzureRmHDInsightPersistedScriptAction.md)


