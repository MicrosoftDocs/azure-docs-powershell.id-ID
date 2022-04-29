---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultmanagedstorageaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultManagedStorageAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultManagedStorageAccount.md
ms.openlocfilehash: adab7d7bb3e3f6cd8aa7cf7a9df352b89dba653f
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144197811"
---
# Update-AzKeyVaultManagedStorageAccount

## SYNOPSIS
Perbarui atribut yang dapat diedit dari Akun Azure Storage terkelola Key Vault.

## SYNTAX

### ByDefinitionName (Default)
```
Update-AzKeyVaultManagedStorageAccount [-VaultName] <String> [-AccountName] <String> [-ActiveKeyName <String>]
 [-AutoRegenerateKey <Boolean>] [-RegenerationPeriod <TimeSpan>] [-Enable <Boolean>] [-Tag <Hashtable>]
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Update-AzKeyVaultManagedStorageAccount [-InputObject] <PSKeyVaultManagedStorageAccountIdentityItem>
 [-ActiveKeyName <String>] [-AutoRegenerateKey <Boolean>] [-RegenerationPeriod <TimeSpan>] [-Enable <Boolean>]
 [-Tag <Hashtable>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Perbarui atribut yang dapat diedit dari Akun Azure Storage terkelola Key Vault.

## EXAMPLES

### Contoh 1: Perbarui kunci aktif ke 'key2' pada Akun Azure Storage yang dikelola Key Vault.
```powershell
Update-AzKeyVaultManagedStorageAccount -VaultName 'myvault' -AccountName 'mystorageaccount' -ActiveKeyName 'key2'
```

```output
Id                  : https://myvault.vault.azure.net:443/storage/mystorageaccount
Vault Name          : myvault
AccountName         : mystorageaccount
Account Resource Id : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx/resourceGroups/myrg/providers/Microsoft.St
                      orage/storageAccounts/mystorageaccount
Active Key Name     : key2
Auto Regenerate Key : True
Regeneration Period : 90.00:00:00
Enabled             : True
Created             : 5/21/2018 11:55:58 PM
Updated             : 5/21/2018 11:55:58 PM
Tags                :
```

Memperbarui kunci aktif Akun Azure Storage terkelola Key Vault ke 'key2'. 'key2' akan digunakan untuk menghasilkan token SAS setelah pembaruan ini.

### Contoh 2

Perbarui atribut yang dapat diedit dari Akun Azure Storage terkelola Key Vault. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Update-AzKeyVaultManagedStorageAccount -AccountName 'mystorageaccount' -AutoRegenerateKey $false -RegenerationPeriod $regenerationPeriod -VaultName 'myvault'
```

## PARAMETERS

### -AccountName
Key Vault nama akun penyimpanan terkelola. Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih, dan nama akun penyimpanan terkelola.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases: StorageAccountName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveKeyName
Nama kunci aktif.
Jika tidak ditentukan, nilai yang ada dari nama kunci aktif akun penyimpanan terkelola tetap tidak berubah

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

### -AutoRegenerateKey
Kunci regenerasi otomatis.
Jika tidak ditentukan, nilai kunci regenerasi otomatis akun penyimpanan terkelola yang ada tetap tidak berubah

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Aktifkan
Jika ada, memungkinkan penggunaan kunci akun penyimpanan terkelola untuk pembuatan token sas jika nilainya benar. Menonaktifkan penggunaan kunci akun penyimpanan terkelola untuk pembuatan token sas jika nilainya salah. Jika tidak ditentukan, nilai yang ada dari status akun penyimpanan yang diaktifkan/dinonaktifkan tetap tidak berubah.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek ManagedStorageAccount.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Cmdlet tidak mengembalikan objek secara default. Jika sakelar ini ditentukan, kembalikan objek akun penyimpanan terkelola.

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

### -RegenerationPeriod
Periode regenerasi. Jika kunci regenerasi otomatis diaktifkan, nilai ini menentukan rentang waktu setelah kunci tidak aktif akun penyimpanan terkelola diregenerasi secara otomatis dan menjadi kunci aktif. Jika tidak ditentukan, nilai periode regenerasi kunci akun penyimpanan terkelola yang ada tetap tidak berubah

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Pasangan kunci-nilai dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama vault.
Cmdlet membangun FQDN vault berdasarkan nama dan lingkungan yang saat ini dipilih.

```yaml
Type: System.String
Parameter Sets: ByDefinitionName
Aliases:

Required: True
Position: 0
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccountIdentityItem

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageAccount

## NOTES

## RELATED LINKS

[Az.KeyVault](/powershell/module/az.keyvault)
