---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupInstance.md
ms.openlocfilehash: 8f2ff951e93ebd4541c220cc1292c02e1766273d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140001141"
---
# New-AzDataProtectionBackupInstance

## SYNOPSIS
Mengonfigurasi Pencadangan untuk sumber daya Azure yang didukung

## SYNTAX

```
New-AzDataProtectionBackupInstance -BackupInstance <IBackupInstanceResource> -ResourceGroupName <String>
 -VaultName <String> [-AsJob] [-DefaultProfile <PSObject>] [-NoWait] [-SubscriptionId <String>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengonfigurasi Pencadangan untuk sumber daya Azure yang didukung

## EXAMPLES

### Contoh 1: Konfigurasi cadangan disk azure di vault cadangan.
```powershell
PS C:\> $sub = "xxxx-xxx-xx"
PS C:\> $DiskId = "/subscriptions/{subscription}/resourceGroups/{resourcegroup}/providers/Microsoft.Compute/disks/{diskname}"
PS C:\> $policy = Get-AzDataProtectionBackupPolicy -SubscriptionId $sub -ResourceGroupName sarath-rg -VaultName sarath-vault -Name "MyPolicy"
PS C:\> $instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDisk -DatasourceLocation $vault.Location -PolicyId $policy.Id -DatasourceId $DiskId 
PS C:\> $instance.Property.PolicyInfo.PolicyParameter.DataStoreParametersList[0].ResourceGroupId = "/subscriptions/{subscription}/resourceGroups/{resourceGroup}"
PS C:\> New-AzDataProtectionBackupInstance -SubscriptionId $sub -ResourceGroupName sarath-rg -VaultName sarath-vault -BackupInstance $instance


Name                                                       Type                                                  BackupInstanceName
----                                                       ----                                                  ------------------
sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166 Microsoft.DataProtection/backupVaults/backupInstances sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166
```

Perintah ketiga mendapatkan kebijakan di mana disk akan dicadangkan.
Perintah keempat memulai permintaan contoh cadangan.
Perintah terakhir mengonfigurasi cadangan disk Azure yang diberikan di vault cadangan.

### Contoh 2: Konfigurasi proteksi untuk database AzureDatabaseForPostgreSQL di vault cadangan (menggunakan autentikasi penyimpanan rahasia).
```powershell
PS C:\> $sub = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
PS C:\> $dataSourceId = "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupName/providers/Microsoft.DBforPostgreSQL/servers/OssServerName/databases/DBName"
PS C:\> $secretURI = "https://oss-keyvault.vault.azure.net/secrets/oss-secret"
PS C:\> $vault = Get-AzDataProtectionBackupVault -SubscriptionId $sub -ResourceGroupName "ResourceGroupName"  -VaultName  $vaultName
PS C:\> $policy = Get-AzDataProtectionBackupPolicy -SubscriptionId $sub -ResourceGroupName "ResourceGroupName" -VaultName "vaultName" -Name "MyPolicy"
PS C:\> $instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDatabaseForPostgreSQL -DatasourceLocation $vault.Location -PolicyId $policy.Id -DatasourceId $dataSourceId -SecretStoreURI $secretURI -SecretStoreType AzureKeyVault
PS C:\> New-AzDataProtectionBackupInstance -SubscriptionId $sub -ResourceGroupName "ResourceGroupName" -VaultName "vaultName" -BackupInstance $instance

Name                                                                Type                                                  BackupInstanceName
----                                                                ----                                                  ------------------
xyz-postgresql-wus-empdb10-xxxxxxxx-xxxx-xxxx-a3ba-be75108d8b21 Microsoft.DataProtection/backupVaults/backupInstances xyz-postgresql-wus-empdb10-xxxxxxxx-xxxx-xxxx-a3ba-be75108d8b21

```

Perintah ketiga memulai rahasiaURI untuk autentikasi penyimpanan rahasia.

Perintah kelima mendapatkan kebijakan untuk database mana yang akan dilindungi.
Perintah keenam memulai objek permintaan instans cadangan.
Perintah terakhir mengonfigurasi cadangan perangkat yang $dataSourceId di vault cadangan.

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

### -BackupInstance
Objek permintaan instans cadangan yang akan digunakan untuk mengonfigurasi pencadangan Untuk dibuat, lihat bagian CATATAN untuk properti BACKUPINSTANCE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupInstanceResource
Parameter Sets: (All)
Aliases:

Required: True
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
Grup Sumber Daya vault cadangan

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

### -SubscriptionId
Id Langganan vault

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
Nama vault cadangan

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


BACKUPINSTANCE <IBackupInstanceResource>: Backup instance request object which will be used to configure backup
  - `[Property <IBackupInstance>]`: Properti BackupInstanceResource
    - `DataSourceInfo <IDatasource>`: Mendapatkan atau mengatur informasi sumber data.
      - `ResourceId <String>`: ID ARM penuh dari sumber daya. Untuk sumber daya Azure, ini adalah ID ARM. For non azure resources, this will be the ID created by backup service via Fabric/Vault.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Sumber Data.
      - `[ResourceUri <String>]`: Uri dari sumber daya.
      - `[Type <String>]`: TipeData sumber daya.
    - `ObjectType <String>`: 
    - `PolicyInfo <IPolicyInfo>`: Mendapatkan atau mengatur informasi kebijakan.
      - `PolicyId <String>`: 
      - `[PolicyParameter <IPolicyParameters>]`: Parameter kebijakan untuk instans cadangan
        - `[DataStoreParametersList <IDataStoreParameters[]>]`: Mendapatkan atau mengatur Parameter DataStore
          - `DataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
          - `ObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `[DataSourceSetInfo <IDatasourceSet>]`: Mendapatkan atau mengatur informasi kumpulan sumber data.
      - `ResourceId <String>`: ID ARM penuh dari sumber daya. Untuk sumber daya Azure, ini adalah ID ARM. For non azure resources, this will be the ID created by backup service via Fabric/Vault.
      - `[DatasourceType <String>]`: TipeData sumber daya.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Sumber Data.
      - `[ResourceUri <String>]`: Uri dari sumber daya.
    - `[DatasourceAuthCredentials <IAuthCredentials>]`: Kredensial yang digunakan untuk mengautentikasi dengan penyedia sumber data.
      - `ObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `[FriendlyName <String>]`: Mendapatkan atau mengatur nama cadangan yang mudah digunakan.

## RELATED LINKS

