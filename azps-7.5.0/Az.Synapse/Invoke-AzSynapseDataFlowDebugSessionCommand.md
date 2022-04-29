---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/invoke-azsynapsedataflowdebugsessioncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseDataFlowDebugSessionCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseDataFlowDebugSessionCommand.md
ms.openlocfilehash: 62d5b14115490f13a679efede0bb2bab757e8f1a
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144247415"
---
# Invoke-AzSynapseDataFlowDebugSessionCommand

## SYNOPSIS
Panggil tindakan debug dalam sesi debug aliran data.

## SYNTAX

### InvokeByName (Default)
```
Invoke-AzSynapseDataFlowDebugSessionCommand -WorkspaceName <String> -SessionId <String> -Command <String>
 -StreamName <String> [-RowLimit <Int32>] [-Expression <String>]
 [-Column <System.Collections.Generic.List`1[System.String]>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InvokeByObject
```
Invoke-AzSynapseDataFlowDebugSessionCommand -WorkspaceObject <PSSynapseWorkspace> -SessionId <String>
 -Command <String> -StreamName <String> [-RowLimit <Int32>] [-Expression <String>]
 [-Column <System.Collections.Generic.List`1[System.String]>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini menjalankan pratinjau data/pratinjau statistik/pratinjau ekspresi untuk aliran data yang berbeda dalam sesi debug. Urutan perintah PowerShell untuk alur kerja debug aliran data harus:

Start-AzSynapseDataFlowDebugSession  
Add-AzSynapseDataFlowDebugSessionPackage  
Invoke-AzSynapseDataFlowDebugSessionCommand (ulangi langkah ini untuk perintah/target yang berbeda, atau ulangi langkah 2-3 untuk mengubah file paket)  
Stop-AzSynapseDataFlowDebugSession  

## EXAMPLES

### Contoh 1
```powershell
$result = Invoke-AzSynapseDataFlowDebugSessionCommand -WorkspaceName ContosoWorkspace -Command executePreviewQuery -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc -StreamName source1 -RowLimit 100 -AsJob
$result | ft -wrap

Id     Name                       PSJobTypeName          State         HasMoreData     Location         Command
--     ----                       -------------          -----         -----------     --------         -------
1      Long Running Operation     AzureLongRunningJob`1  Completed     True            localhost        Invoke-AzSynapseDataFlowDebugSessionCommand
       for 'Invoke-AzSynapseD                                                             
       ataFlowDebugSessionCommand'            

$output = ConvertFrom-Json($result.Output.Data)
$output.output

    {
      "schema": "output(ResourceAgencyNum as string, PublicName as string)" ,
      "data": [["4445679354", "Syrian Refugee Information", 1], ["44456793", "Syrian Refugee Information", 1]]
    }
```

Contoh ini memanggil perintah pratinjau data untuk sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di ruang kerja Synapse "ContosoWorkspace" dan kemudian mengonversi output JSON menjadi string yang dapat dibaca.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Invoke-AzSynapseDataFlowDebugSessionCommand -Command executePreviewQuery -SessionId 3afb278e-ac5f-469f-a0b6-2f04c3ab59bc -StreamName source1 -RowLimit 100
```

Contoh ini memanggil perintah pratinjau data untuk sesi debug "3afb278e-ac5f-469f-a0b6-2f04c3ab59bc" di ruang kerja Synapse "ContosoWorkspace" melalui alur. 

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

### -Kolom
Daftar kolom untuk pratinjau statistik aliran data.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Perintah
Perintah debug aliran data.
Opsional adalah executePreviewQuery, executeStatisticsQuery, dan executeExpressionQuery.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ekspresi
Ekspresi untuk pratinjau ekspresi aliran data.

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

### -RowLimit
Batas baris untuk pratinjau data aliran data.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionId
Pengidentifikasi untuk sesi debug aliran data Synapse.

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

### -StreamName
Nama aliran aliran data untuk penelusuran kesalahan.

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

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: InvokeByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: InvokeByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSDataFlowDebugCommandResponse

## NOTES

## RELATED LINKS
