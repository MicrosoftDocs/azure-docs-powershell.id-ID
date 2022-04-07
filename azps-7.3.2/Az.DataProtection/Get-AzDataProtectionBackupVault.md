---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionbackupvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupVault.md
ms.openlocfilehash: 9fe4aaf355410d63ee3afe3346cbbe8d6c1d122f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140381782"
---
# Get-AzDataProtectionBackupVault

## SYNOPSIS
Mengembalikan kumpulan sumber daya milik grup sumber daya.

## SYNTAX

### Get1 (Default)
```
Get-AzDataProtectionBackupVault -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get2
```
Get-AzDataProtectionBackupVault -ResourceGroupName <String> -VaultName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataProtectionBackupVault -InputObject <IDataProtectionIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan kumpulan sumber daya milik grup sumber daya.

## EXAMPLES

### Contoh 1: Mendapatkan semua vault cadangan dalam langganan tertentu
```powershell
PS C:\> Get-AzDataProtectionBackupVault

ETag IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location      Name                          Type
---- -------------------                  ----------------                     ------------   --------      ----                          ----
     2a21f108-07bc-4c22-a221-f26c9de554ba 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned westus        adigupt-backupcenter-ga-Vault Microsoft.DataProtection/backupV�
     34237b3f-8f2c-4ae7-bbff-2896491976fb 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned westcentralus BC-Usability-Vault-WCUS       Microsoft.DataProtection/backupV�
     41155247-420f-4052-a894-84814f0b983c 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned centraluseuap NilayBackupVault              Microsoft.DataProtection/backupV�
     26da260b-e232-419c-8586-9157e4f6260e 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned centraluseuap dpprunnervaultus              Microsoft.DataProtection/backupV�
```

Perintah ini mendapatkan semua vault cadangan dalam konteks langganan saat ini.
Sediakan parameter SubscriptionId untuk mengambil vault cadangan di langganan yang berbeda.

### Contoh 2: Dapatkan semua vault cadangan dalam Grup sumber daya yang diberikan.
```powershell
PS C:\> Get-AzDataProtectionBackupVault -SubscriptionId "xxxx-xxx-xxxx" -ResourceGroupName sarath-rg

ETag IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location      Name            Type
---- -------------------                  ----------------                     ------------   --------      ----            ----
     05400379-2551-4dc9-86e0-cf59ab05405a 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned centraluseuap sarath-dppvault Microsoft.DataProtection/backupVaults
     2ca1d5f7-38b3-4b61-aa45-8147d7e0edbc 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned centraluseuap sarath-vault    Microsoft.DataProtection/backupVaults
```

Perintah ini menyimpan semua vault cadangan dalam grup sumber daya yang ada.

### Contoh 3: Dapatkan vault tertentu.
```powershell
PS C:\> Get-AzDataProtectionBackupVault -SubscriptionId "xxxx-xxx-xxxx" -ResourceGroupName sarath-rg -VaultName sarath-vault

ETag IdentityPrincipalId                  IdentityTenantId                     IdentityType   Location      Name            Type
---- -------------------                  ----------------                     ------------   --------      ----            ----
     2ca1d5f7-38b3-4b61-aa45-8147d7e0edbc 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned centraluseuap sarath-vault    Microsoft.DataProtection/backupVaults
```

Perintah ini mendapatkan vault tertentu dengan nama vault tertentu.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
Nama grup sumber daya tempat vault cadangan ada.

```yaml
Type: System.String
Parameter Sets: Get1, Get2
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
Parameter Sets: Get1, Get2
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama vault cadangan.

```yaml
Type: System.String
Parameter Sets: Get2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.IDataProtectionIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupVaultResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDataProtectionIdentity>: Parameter Identitas
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

