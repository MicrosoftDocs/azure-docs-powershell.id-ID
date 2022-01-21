---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/backup-azdataprotectionbackupinstanceadhoc
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Backup-AzDataProtectionBackupInstanceAdhoc.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Backup-AzDataProtectionBackupInstanceAdhoc.md
ms.openlocfilehash: 88852aa80d2e46a498ee7d26bf1133ee47484abd
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136532117"
---
# Backup-AzDataProtectionBackupInstanceAdhoc

## SYNOPSIS
Memicu pencadangan adhoc

## SYNTAX

### BackupExpanded (Default)
```
Backup-AzDataProtectionBackupInstanceAdhoc -BackupInstanceName <String> -ResourceGroupName <String>
 -VaultName <String> -BackupRuleOptionRuleName <String> [-SubscriptionId <String>]
 [-TriggerOptionRetentionTagOverride <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### BackupViaIdentityExpanded
```
Backup-AzDataProtectionBackupInstanceAdhoc -InputObject <IDataProtectionIdentity>
 -BackupRuleOptionRuleName <String> [-TriggerOptionRetentionTagOverride <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memicu pencadangan adhoc

## EXAMPLES

### Contoh 1: Mencadangkan instans cadangan yang diproteksi
```powershell
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault"
PS C:\> Backup-AzDataProtectionBackupInstanceAdhoc -BackupInstanceName $instance.Name -ResourceGroupName "MyResourceGroup" -SubscriptionId "xxxx-xxx-xxxx" -VaultName "MyVault" -BackupRuleOptionRuleName "BackupWeekly" -TriggerOptionRetentionTagOverride "Default"

```

Perintah Ini Memicu Pencadangan untuk instans cadangan tertentu.

### Contoh 2: Mencadangkan instans cadangan yang diproteksi
```powershell
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault"
PS C:\> $policy = Get-AzDataProtectionBackupPolicy -SubscriptionId $sub -VaultName "MyVault" -ResourceGroupName "MyResourceGroup" | where {$_.Name -eq "policyName"}
PS C:\> $backupJob = Backup-AzDataProtectionBackupInstanceAdhoc -BackupInstanceName $instance.Name -ResourceGroupName "MyResourceGroup" -SubscriptionId "xxxx-xxx-xxxx" -VaultName "MyVault" -BackupRuleOptionRuleName $policy.Property.PolicyRule[0].Name -TriggerOptionRetentionTagOverride $policy.Property.PolicyRule[0].Trigger.TaggingCriterion[0].TagInfoTagName
PS C:\> $jobid = $backupJob.JobId.Split("/")[-1]
PS C:\> $jobstatus = "InProgress"
PS C:\> while($jobstatus -ne "Completed")
>> {
>>     Start-Sleep -Seconds 10
>>     $currentjob = Get-AzDataProtectionJob -Id $jobid -SubscriptionId $sub -ResourceGroupName $rgName -VaultName $vaultName
>>     $jobstatus = $currentjob.Status
>> }

```

Perintah Ini Memicu Pencadangan untuk instans cadangan tertentu yang menggunakan kebijakan proteksi yang digunakan untuk memproteksi instans cadangan.
Lalu kita lacak pekerjaan pencadangan itu secara berulang hingga selesai.

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

### -BackupInstanceName
Nama instans cadangan

```yaml
Type: System.String
Parameter Sets: BackupExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupRuleOptionRuleName
.

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.IDataProtectionIdentity
Parameter Sets: BackupViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Nama grup sumber daya tempat vault cadangan ada.

```yaml
Type: System.String
Parameter Sets: BackupExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id langganan.

```yaml
Type: System.String
Parameter Sets: BackupExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerOptionRetentionTagOverride
.

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

### -VaultName
Nama vault cadangan.

```yaml
Type: System.String
Parameter Sets: BackupExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.IDataProtectionIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IOperationJobExtendedInfo

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataProtectionIdentity> : Parameter Identitas
  - `[BackupInstanceName <String>]`: Nama instans cadangan
  - `[BackupPolicyName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobId <String>]`: ID Pekerjaan. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Location <String>]`: Lokasi di mana keunikan akan diverifikasi.
  - `[OperationId <String>]`: 
  - `[RecoveryPointId <String>]`: 
  - `[RequestName <String>]`: 
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat vault cadangan ada.
  - `[ResourceGuardsName <String>]`: Nama ResourceGuard
  - `[SubscriptionId <String>]`: Id langganan.
  - `[VaultName <String>]`: Nama vault cadangan.

## RELATED LINKS

