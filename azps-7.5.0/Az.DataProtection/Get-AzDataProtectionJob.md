---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionJob.md
ms.openlocfilehash: 543088f8ba5b118dcbb349beb3f562ca1e955bb2
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145749196"
---
# Get-AzDataProtectionJob

## SYNOPSIS
Mendapatkan pekerjaan dengan id di brankas cadangan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/get-azdataprotectionjob) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDataProtectionJob -ResourceGroupName <String> -VaultName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDataProtectionJob -Id <String> -ResourceGroupName <String> -VaultName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataProtectionJob -InputObject <IDataProtectionIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan pekerjaan dengan id di brankas cadangan

## EXAMPLES

### Contoh 1: Dapatkan Semua Pekerjaan pencadangan dalam vault cadangan
```powershell
Get-AzDataProtectionjob -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault
```

```output
Name                                 Type
----                                 ----
a6a4879d-f914-4174-b129-0e27da8a4fb0 Microsoft.DataProtection/backupVaults/backupJobs
1a402664-a245-4a9d-8bb5-a6bafbb40d26 Microsoft.DataProtection/backupVaults/backupJobs
672564f7-1f91-46e2-a0ca-4fb1dc977a1c Microsoft.DataProtection/backupVaults/backupJobs
1653a7b4-8ce4-457e-8084-dc1c9d9e4106 Microsoft.DataProtection/backupVaults/backupJobs
9f21c438-ca0d-45c1-88fe-79f08a8342c7 Microsoft.DataProtection/backupVaults/backupJobs
736bab4d-480f-49f8-92ea-57c5ff203c33 Microsoft.DataProtection/backupVaults/backupJobs
```

Perintah ini mendapatkan semua pekerjaan pencadangan dalam vault cadangan tertentu.

### Contoh 2: Mendapatkan satu Pekerjaan 
```powershell
Get-AzDataProtectionjob -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault -Id 4abaea8c-f53a-4bb1-9963-59f96b597165
```

```output
Name                                 Type
----                                 ----
4abaea8c-f53a-4bb1-9963-59f96b597165 Microsoft.DataProtection/backupVaults/backupJobs
```

Perintah ini mengembalikan satu entitas pekerjaan dengan Id yang diberikan.

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

### -Id
ID Pekerjaan.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000).

```yaml
Type: System.String
Parameter Sets: Get
Aliases: JobId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupJobResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataProtectionIdentity>: Parameter Identitas
  - `[BackupInstanceName <String>]`: Nama instans cadangan
  - `[BackupPolicyName <String>]`: 
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobId <String>]`: ID Pekerjaan. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000).
  - `[Location <String>]`: Lokasi di mana keunikan akan diverifikasi.
  - `[OperationId <String>]`: 
  - `[RecoveryPointId <String>]`: 
  - `[RequestName <String>]`: 
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat vault cadangan ada.
  - `[ResourceGuardsName <String>]`: Nama ResourceGuard
  - `[SubscriptionId <String>]`: Id langganan.
  - `[VaultName <String>]`: Nama brankas cadangan.

## RELATED LINKS

