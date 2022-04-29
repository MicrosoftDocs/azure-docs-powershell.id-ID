---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionbackuppolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupPolicy.md
ms.openlocfilehash: 605ddd672a4a9ddae7b00a0dd2516f7caade5a28
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144218987"
---
# Get-AzDataProtectionBackupPolicy

## SYNOPSIS
Mendapatkan kebijakan cadangan milik brankas cadangan

## SYNTAX

### Daftar (Default)
```
Get-AzDataProtectionBackupPolicy -ResourceGroupName <String> -VaultName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDataProtectionBackupPolicy -Name <String> -ResourceGroupName <String> -VaultName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataProtectionBackupPolicy -InputObject <IDataProtectionIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kebijakan cadangan milik brankas cadangan

## EXAMPLES

### Contoh 1: Dapatkan semua kebijakan pencadangan dalam brankas cadangan.
```powershell
Get-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault"
```

```output
Name              Type
----              ----
DiskPolicy1       Microsoft.DataProtection/backupVaults/backupPolicies
DiskDailyPolicy   Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah ini mendapatkan kebijakan pencadangan yang dibuat dalam vault cadangan tertentu.

### Contoh 2: Dapatkan kebijakan pencadangan berdasarkan Nama
```powershell
Get-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault" -Name "MyPolicy"
```

```output
Name        Type
----        ----
MyPolicy Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah ini mendapatkan kebijakan pencadangan berdasarkan nama.

## PARAMETERS

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.IDataProtectionIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: BackupPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat vault cadangan berada.

```yaml
Type: System.String
Parameter Sets: Get, List
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
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama brankas cadangan.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.IDataProtectionIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBaseBackupPolicyResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataProtectionIdentity>: Parameter Identitas
  - `[BackupInstanceName <String>]`: Nama instans cadangan
  - `[BackupPolicyName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobId <String>]`: ID Pekerjaan. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000).
  - `[Location <String>]`: Lokasi di mana keunikan akan diverifikasi.
  - `[OperationId <String>]`: 
  - `[RecoveryPointId <String>]`: 
  - `[RequestName <String>]`: 
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat vault cadangan berada.
  - `[ResourceGuardsName <String>]`: Nama ResourceGuard
  - `[SubscriptionId <String>]`: Id langganan.
  - `[VaultName <String>]`: Nama brankas cadangan.

## RELATED LINKS

