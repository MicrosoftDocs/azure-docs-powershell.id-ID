---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionBackupInstance.md
ms.openlocfilehash: eb9e14b4d71543673d54391810bc6c513c8938ae
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142874062"
---
# Get-AzDataProtectionBackupInstance

## SYNOPSIS
Mendapatkan instans cadangan dengan nama dalam vault cadangan

## SYNTAX

### Daftar (Default)
```
Get-AzDataProtectionBackupInstance -ResourceGroupName <String> -VaultName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDataProtectionBackupInstance -Name <String> -ResourceGroupName <String> -VaultName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDataProtectionBackupInstance -InputObject <IDataProtectionIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan instans cadangan dengan nama dalam vault cadangan

## EXAMPLES

### Contoh 1: Dapatkan semua instans cadangan yang dilindungi dalam vault cadangan tertentu.
```powershell
Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault"
```

```output
Name                                                         Type                                                  BackupInstanceName
----                                                         ----                                                  ------------------
sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166   Microsoft.DataProtection/backupVaults/backupInstances sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f
sarathdisk2-sarathdisk2-74b127dc-7bf0-48ef-bcef-dab186cc6f10 Microsoft.DataProtection/backupVaults/backupInstances sarathdisk2-sarathdisk2-74b127dc-7bf0-48ef-bcef-dab186c

```

Perintah ini mendapatkan semua instans cadangan dalam vault.

### Contoh 2: Dapatkan instans cadangan berdasarkan nama.
```powershell
Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "MyResourceGroup" -VaultName "MyVault" -Name "BackupInstanceName"
```

```output
Name                                                       Type                                                  BackupInstanceName
----                                                       ----                                                  ------------------
sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166 Microsoft.DataProtection/backupVaults/backupInstances sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166
```

Perintah ini mendapatkan instans cadangan tertentu yang dilindungi dalam vault cadangan.

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

### -Name
Nama instans cadangan

```yaml
Type: System.String
Parameter Sets: Get
Aliases: BackupInstanceName

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

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupInstanceResource

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

