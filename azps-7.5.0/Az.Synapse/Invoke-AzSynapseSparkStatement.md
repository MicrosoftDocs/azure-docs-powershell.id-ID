---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/invoke-azsynapsesparkstatement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseSparkStatement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseSparkStatement.md
ms.openlocfilehash: 637cb809cb2e9223765e75a129012aa6ca5b1c68
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144185071"
---
# Invoke-AzSynapseSparkStatement

## SYNOPSIS
Memanggil pernyataan Synapse Analytics Spark.

## SYNTAX

### RunSparkStatementByCodePathParameterSet (Default)
```
Invoke-AzSynapseSparkStatement -WorkspaceName <String> -SparkPoolName <String> -Language <String>
 -SessionId <Int32> -FilePath <String> [-Response] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RunSparkStatementByCodeParameterSet
```
Invoke-AzSynapseSparkStatement -WorkspaceName <String> -SparkPoolName <String> -Language <String>
 -SessionId <Int32> -Code <String> [-Response] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RunSparkStatementByCodeAndInputObjectParameterSet
```
Invoke-AzSynapseSparkStatement -Language <String> -SessionObject <PSSynapseSparkSession> [-SessionId <Int32>]
 -Code <String> [-Response] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RunSparkStatementByCodePathAndInputObjectParameterSet
```
Invoke-AzSynapseSparkStatement -Language <String> -SessionObject <PSSynapseSparkSession> [-SessionId <Int32>]
 -FilePath <String> [-Response] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzSynapseSparkStatement** memanggil pernyataan Synapse Analytics Spark.

## EXAMPLES

### Contoh 1
```powershell
$session = Start-AzSynapseSparkSession -WorkspaceName ContosoWorkspace -SparkPoolName ContosoSparkPool -Name ContosoSessionName -ExecutorCount 3 -ExecutorSize Small
$session.Language = 'Spark' 
$session | Invoke-AzSynapseSparkStatement -Code '
 print("Hello world\n")
 '
```

Perintah ini memulai sesi Spark lalu memanggil pernyataan Spark sebaris melalui alur.

### Contoh 2
```powershell
Invoke-AzSynapseSparkStatement -SessionId 324 -Language 'Spark' -Code '
 print("Hello world\n")
 '
```

Perintah ini memulai sesi Spark lalu memanggil pernyataan Spark sebaris.

### Contoh 3
```powershell
$session = Start-AzSynapseSparkSession -WorkspaceName ContosoWorkspace -SparkPoolName ContosoSparkPool -Name ContosoSessionName -ExecutorCount 3 -ExecutorSize Small
$session.Language = 'Spark' 
$session | Invoke-AzSynapseSparkStatement -FilePath C:\path\to\code.sc
```

Perintah ini memulai sesi Spark lalu memanggil pernyataan Spark dalam file.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -Kode
Kode eksekusi.

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodeParameterSet, RunSparkStatementByCodeAndInputObjectParameterSet
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Menentukan jalur file lokal yang berisi kode eksekusi.

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodePathParameterSet, RunSparkStatementByCodePathAndInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bahasa
Bahasa kode eksekusi.

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodePathParameterSet, RunSparkStatementByCodeParameterSet
Aliases:
Accepted values: Spark, Scala, PySpark, Python, SparkDotNet, CSharp, SQL

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodeAndInputObjectParameterSet, RunSparkStatementByCodePathAndInputObjectParameterSet
Aliases:
Accepted values: Spark, Scala, PySpark, Python, SparkDotNet, CSharp, SQL

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Respons
Menunjukkan respons penuh harus dikembalikan.

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

### -SessionId
Pengidentifikasi sesi Spark.

```yaml
Type: System.Int32
Parameter Sets: RunSparkStatementByCodePathParameterSet, RunSparkStatementByCodeParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.Int32
Parameter Sets: RunSparkStatementByCodeAndInputObjectParameterSet, RunSparkStatementByCodePathAndInputObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionObject
Objek input sesi Spark, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseSparkSession
Parameter Sets: RunSparkStatementByCodeAndInputObjectParameterSet, RunSparkStatementByCodePathAndInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SparkPoolName
Nama kumpulan Synapse Spark.

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodePathParameterSet, RunSparkStatementByCodeParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: RunSparkStatementByCodePathParameterSet, RunSparkStatementByCodeParameterSet
Aliases:

Required: True
Position: Named
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSparkSession

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseExtendedSparkStatement

## NOTES

## RELATED LINKS
