---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/set-azkeyvaultmanagedstoragesasdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultManagedStorageSasDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Set-AzKeyVaultManagedStorageSasDefinition.md
ms.openlocfilehash: dc5a75abbb940dd6623667976536b0f8003054a6
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144656066"
---
# Set-AzKeyVaultManagedStorageSasDefinition

## SYNOPSIS
Mengatur definisi Tanda Tangan Akses Bersama (SAS) dengan Key Vault untuk Akun Azure Storage terkelola Key Vault tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/set-azkeyvaultmanagedstoragesasdefinition) untuk informasi terbaru.

## SYNTAX

### Default (Default)
```
Set-AzKeyVaultManagedStorageSasDefinition [-VaultName] <String> [-AccountName] <String> [-Name] <String>
 [-TemplateUri] <String> [-SasType] <String> [-Disable] [-Tag <Hashtable>] -ValidityPeriod <TimeSpan>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Set-AzKeyVaultManagedStorageSasDefinition [-InputObject] <PSKeyVaultManagedStorageAccountIdentityItem>
 [-Name] <String> [-TemplateUri] <String> [-SasType] <String> [-Disable] [-Tag <Hashtable>]
 -ValidityPeriod <TimeSpan> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Mengatur definisi Tanda Tangan Akses Bersama (SAS) dengan akun Azure Storage terkelola Key Vault tertentu. Ini juga menetapkan rahasia yang dapat digunakan untuk mendapatkan token SAS sesuai definisi SAS ini.
Token SAS dihasilkan menggunakan parameter ini dan kunci aktif akun Azure Storage yang dikelola Key Vault.

## EXAMPLES

### Contoh 1: Atur definisi SAS jenis akun, dan dapatkan token SAS saat ini berdasarkan definisi TERSEBUT
```powershell
$sa = Get-AzStorageAccount -Name mysa -ResourceGroupName myrg
$kv = Get-AzKeyVault -VaultName mykv
Add-AzKeyVaultManagedStorageAccount -VaultName $kv.VaultName -AccountName $sa.StorageAccountName -AccountResourceId $sa.Id -ActiveKeyName key1 -RegenerationPeriod ([System.Timespan]::FromDays(180))
$sctx = New-AzStorageContext -StorageAccountName $sa.StorageAccountName -Protocol Https -StorageAccountKey Key1
$start = [System.DateTime]::Now.AddDays(-1)
$end = [System.DateTime]::Now.AddMonths(1)
$at = New-AzStorageAccountSasToken -Service blob,file,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -StartTime $start -ExpiryTime $end -Context $sctx
$sas = Set-AzKeyVaultManagedStorageSasDefinition -AccountName $sa.StorageAccountName -VaultName $kv.VaultName -Name accountsas -TemplateUri $at -SasType 'account' -ValidityPeriod ([System.Timespan]::FromDays(30))
Get-AzKeyVaultSecret -VaultName $kv.VaultName -Name $sas.Sid.Substring($sas.Sid.LastIndexOf('/')+1)
```

Mengatur akun definisi SAS 'accountsas' pada akun penyimpanan yang dikelola KeyVault 'mysa' di vault 'mykv'. Secara khusus, urutan di atas melakukan hal berikut:
  - mendapatkan akun penyimpanan (yang sudah ada sebelumnya)
  - mendapatkan brankas kunci (yang sudah ada sebelumnya)
  - menambahkan akun penyimpanan yang dikelola KeyVault ke vault, mengatur Key1 sebagai kunci aktif, dan dengan periode regenerasi 180 hari
  - mengatur konteks penyimpanan untuk akun penyimpanan yang ditentukan, dengan Key1
  - membuat token SAS akun untuk layanan Blob, File, Tabel dan Antrean, untuk jenis sumber daya Layanan, Kontainer dan Objek, dengan semua izin, melalui https dan dengan tanggal mulai dan berakhir yang ditentukan
  - mengatur definisi SAS penyimpanan yang dikelola KeyVault di brankas, dengan uri templat sebagai token SAS yang dibuat di atas, dari jenis SAS 'akun' dan berlaku selama 30 hari
  - mengambil token akses aktual dari rahasia KeyVault yang sesuai dengan definisi SAS

## PARAMETERS

### -AccountName
Key Vault nama akun penyimpanan terkelola. Cmdlet membangun FQDN dari nama akun penyimpanan terkelola dari nama vault, lingkungan yang saat ini dipilih, dan nama akun penyimpanan terkelola.

```yaml
Type: System.String
Parameter Sets: Default
Aliases: StorageAccountName

Required: True
Position: 1
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

### -Nonaktifkan
Menonaktifkan penggunaan definisi sas untuk pembuatan token sas.

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

### -Name
Storage nama definisi sas. Cmdlet membangun FQDN dari definisi sas penyimpanan dari nama vault, lingkungan yang saat ini dipilih, nama akun penyimpanan, dan nama definisi sas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SasDefinitionName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasType
Storage jenis SAS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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

### -TemplateUri
Storage uri templat definisi SAS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidityPeriod
Periode validitas yang akan digunakan untuk mengatur waktu kedaluwarsa token sas sejak dihasilkan

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: (All)
Aliases:

Required: True
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
Parameter Sets: Default
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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultManagedStorageSasDefinition

## NOTES

## RELATED LINKS

[Azureâ €‹RM.â€‹Keyâ€‹Vault](/powershell/module/az.keyvault/)
