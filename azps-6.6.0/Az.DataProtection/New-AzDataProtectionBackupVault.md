---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupVault.md
ms.openlocfilehash: 9f77afd67a2923fd23215818b6b8043d32c29f6e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142271059"
---
# New-AzDataProtectionBackupVault

## SYNOPSIS
Membuat atau memperbarui sumber daya BackupVault milik grup sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionbackupvault) untuk informasi terbaru.

## SYNTAX

```
New-AzDataProtectionBackupVault -Location <String> -ResourceGroupName <String>
 -StorageSetting <IStorageSetting[]> -VaultName <String> [-AsJob] [-DefaultProfile <PSObject>]
 [-ETag <String>] [-IdentityType <String>] [-NoWait] [-SubscriptionId <String>] [-Tag <Hashtable>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui sumber daya BackupVault milik grup sumber daya.

## EXAMPLES

### Contoh 1: Membuat kubah cadangan baru
```powershell
PS C:\> $sub = "xxxx-xxxx-xxxxx"
PS C:\> $storagesetting = New-AzDataProtectionBackupVaultStorageSettingObject -DataStoreType VaultStore -Type LocallyRedundant
PS C:\> New-AzDataProtectionBackupVault -SubscriptionId $sub -ResourceGroupName sarath-rg -VaultName "MyVault" -StorageSetting $storagesetting -Location westus

ETag IdentityPrincipalId IdentityTenantId IdentityType Location Name    Type
---- ------------------- ---------------- ------------ -------- ----    ----
                                                       westus   MyVault Microsoft.DataProtection/backupVaults
```

Perintah ini membuat kubah cadangan baru.

## PARAMETERS

### -AsJob


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

### -DefaultProfile


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

### -ETag
ETag Opsional.

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

### -IdentityType
IdentityType yang dapat berupa SystemAssigned atau None.

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

### -Lokasi
Lokasi sumber daya.

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

### -NoWait


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
Nama Grup Sumber Daya dari kubah cadangan

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

### -StorageSetting
Storage Pengaturan kubah.
Gunakan Cmdlet New-AzDataProtectionBackupVaultStorageSetting untuk Membuat.
Untuk membangun, lihat bagian CATATAN untuk properti STORAGESETTING dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IStorageSetting[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan kubah

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

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama kubah cadangan

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


STORAGESETTING <IStorageSetting[]>: Storage Pengaturan kubah. Gunakan Cmdlet New-AzDataProtectionBackupVaultStorageSetting untuk Membuat.
  - `[DatastoreType <StorageSettingStoreTypes?>]`: Mendapatkan atau mengatur tipe datastore.
  - `[Type <StorageSettingTypes?>]`: Mendapatkan atau mengatur tipe.

## RELATED LINKS

