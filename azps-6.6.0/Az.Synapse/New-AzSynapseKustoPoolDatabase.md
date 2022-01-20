---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsekustopooldatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKustoPoolDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKustoPoolDatabase.md
ms.openlocfilehash: 2b7ad3df94be6f728d581e5f9b66ce3d494b6805
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136367147"
---
# New-AzSynapseKustoPoolDatabase

## SYNOPSIS
Membuat atau memperbarui database.

## SYNTAX

```
New-AzSynapseKustoPoolDatabase -DatabaseName <String> -KustoPoolName <String> -ResourceGroupName <String>
 -WorkspaceName <String> -Kind <Kind> [-SubscriptionId <String>] [-HotCachePeriod <TimeSpan>]
 [-Location <String>] [-SoftDeletePeriod <TimeSpan>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui database.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui database kusto baru dalam ruang kerja
```powershell
PS C:\> New-AzSynapseKustoPoolDatabase -ResourceGroupName "testrg" -WorkspaceName "testws" -KustoPoolName "testkustopool" -DatabaseName "mykustodatabase" -Kind "ReadWrite" -Location "East US 2"

Kind      Location  Name                                                                                   
----      --------  ----                              
ReadWrite East US 2 testws/testkustopool/mykustodatabase
```

Membuat atau memperbarui database kusto "mykustodatabase" di Kusto Pool "testkustopool" di ruang kerja "testws" yang ditemukan dalam grup sumber daya "testrg".

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -DatabaseName
Nama database di dalam kolam Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

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

### -HotCachePeriod
Waktu data harus disimpan dalam cache untuk kueri cepat dalam TimeSpan.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kind
Jenis database

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.Kind
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KustoPoolName
Nama pool Kusto.

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

### -Lokasi
Lokasi sumber daya.

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

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -SoftDeletePeriod
Waktu yang harus disimpan sebelum data berhenti dapat diakses ke kueri di TimeSpan.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IDatabase

## CATATAN

ALIAS

## RELATED LINKS

