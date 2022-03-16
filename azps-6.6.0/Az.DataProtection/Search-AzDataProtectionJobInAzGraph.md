---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/search-azdataprotectionjobinazgraph
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Search-AzDataProtectionJobInAzGraph.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Search-AzDataProtectionJobInAzGraph.md
ms.openlocfilehash: ad2dc8017fe9896915b342ce6e9d13189faeba22
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139940884"
---
# Search-AzDataProtectionJobInAzGraph

## SYNOPSIS
Mencari Pekerjaan Cadangan di Sumber Daya Azure Graph dan mengambil entri yang diharapkan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.dataprotection/search-azdataprotectionjobinazgraph) untuk informasi terkini.

## SYNTAX

```
Search-AzDataProtectionJobInAzGraph -DatasourceType <DatasourceTypes> -Subscription <String[]>
 [-EndTime <DateTime>] [-Operation <JobOperation[]>] [-ResourceGroup <String[]>] [-StartTime <DateTime>]
 [-Status <JobStatus[]>] [-Vault <String[]>] [<CommonParameters>]
```

## DESCRIPTION
Mencari Pekerjaan Cadangan di Sumber Daya Azure Graph dan mengambil entri yang diharapkan

## EXAMPLES

### Contoh 1: Mendapatkan semua pekerjaan dalam rentang waktu tertentu
```powershell
PS C:\> $endtime = get-date
PS C:\> $starttime = $endtime.AddHours(-5)
PS C:\> Search-AzDataProtectionJobInAzGraph -Subscription "xxx-xxx-xxx" -ResourceGroup sarath-rg -Vault sarath-vault -DatasourceType AzureDisk -StartTime $starttime -EndTime $endtime

Name                                 Type
----                                 ----
1c1d56c2-b21a-4038-ba46-3c1a0089e66a microsoft.dataprotection/backupvaults/backupjobs
79f2804d-a39d-487e-91b5-f2eceffcbb7a microsoft.dataprotection/backupvaults/backupjobs
96238abd-6ff3-48e0-8c07-0eabd6928a17 microsoft.dataprotection/backupvaults/backupjobs
```

Perintah ini mendapatkan semua pekerjaan di vault dalam 5 jam terakhir.

### Contoh 2: Mendapatkan semua pekerjaan tipe operasi tertentu
```powershell
PS C:\> Search-AzDataProtectionJobInAzGraph -Subscription "xxxx-xxx-xxx" -ResourceGroup sarath-rg -Vault sarath-vault -DatasourceType AzureDisk -Operation OnDemandBackup

Name                                 Type
----                                 ----
11bc277d-9448-446a-9e79-4721858524d6 microsoft.dataprotection/backupvaults/backupjobs
16d7b56a-e169-41d1-aa10-cafcc19c8e12 microsoft.dataprotection/backupvaults/backupjobs
1b0b17e3-398f-4265-9d03-ffc1e21fa73a microsoft.dataprotection/backupvaults/backupjobs
```

Perintah ini mendapatkan semua pekerjaan cadangan yang harus dilakukan dalam vault.

## PARAMETERS

### -DatasourceType
Tipe SumberData

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DatasourceTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Filter Waktu Selesai untuk Pekerjaan Cadangan

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operasi
Filter operasi untuk pekerjaan pencadangan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.JobOperation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroup
Grup Sumber Daya Vault

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Filter Waktu Mulai untuk cadangan Pekerjaan

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Filter status untuk pekerjaan pencadangan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.JobStatus[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Langganan
Langganan Vault

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Nama vault

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

ALIAS

## RELATED LINKS

