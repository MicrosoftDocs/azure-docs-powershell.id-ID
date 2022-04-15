---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackupinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupInstance.md
ms.openlocfilehash: 76f58d62cb8db6c8a4d4c695adcdc4288479d035
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142432771"
---
# New-AzDataProtectionBackupInstance

## SYNOPSIS
Mengonfigurasi Pencadangan untuk sumber daya azure yang didukung

## SYNTAX

```
New-AzDataProtectionBackupInstance -BackupInstance <IBackupInstanceResource> -ResourceGroupName <String>
 -VaultName <String> [-AsJob] [-DefaultProfile <PSObject>] [-NoWait] [-SubscriptionId <String>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengonfigurasi Pencadangan untuk sumber daya azure yang didukung

## EXAMPLES

### Contoh 1: Mengonfigurasi cadangan disk azure dalam kubah cadangan.
```powershell
$sub = "xxxx-xxx-xx"
$DiskId = "/subscriptions/{subscription}/resourceGroups/{resourcegroup}/providers/Microsoft.Compute/disks/{diskname}"
$policy = Get-AzDataProtectionBackupPolicy -SubscriptionId $sub -ResourceGroupName sarath-rg -VaultName sarath-vault -Name "MyPolicy"
$instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDisk -DatasourceLocation $vault.Location -PolicyId $policy.Id -DatasourceId $DiskId 
$instance.Property.PolicyInfo.PolicyParameter.DataStoreParametersList[0].ResourceGroupId = "/subscriptions/{subscription}/resourceGroups/{resourceGroup}"
New-AzDataProtectionBackupInstance -SubscriptionId $sub -ResourceGroupName sarath-rg -VaultName sarath-vault -BackupInstance $instance
```

```output
Name                                                       Type                                                  BackupInstanceName
----                                                       ----                                                  ------------------
sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166 Microsoft.DataProtection/backupVaults/backupInstances sarathdisk-sarathdisk-3df6ac08-9496-4839-8fb5-8b78e594f166
```

Perintah ketiga mendapatkan kebijakan dengan disk mana yang akan dicadangkan.
Perintah keempat menginisialisasi permintaan instans cadangan.
Perintah terakhir mengonfigurasi cadangan disk azure tertentu dalam kubah cadangan.

### Contoh 2: Mengonfigurasi proteksi untuk database AzureDatabaseForPostgreSQL dalam kubah cadangan (menggunakan autentikasi secret store).
```powershell
$sub = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
$dataSourceId = "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupName/providers/Microsoft.DBforPostgreSQL/servers/OssServerName/databases/DBName"
$secretURI = "https://oss-keyvault.vault.azure.net/secrets/oss-secret"
$vault = Get-AzDataProtectionBackupVault -SubscriptionId $sub -ResourceGroupName "ResourceGroupName"  -VaultName  $vaultName
$policy = Get-AzDataProtectionBackupPolicy -SubscriptionId $sub -ResourceGroupName "ResourceGroupName" -VaultName "vaultName" -Name "MyPolicy"
$instance = Initialize-AzDataProtectionBackupInstance -DatasourceType AzureDatabaseForPostgreSQL -DatasourceLocation $vault.Location -PolicyId $policy.Id -DatasourceId $dataSourceId -SecretStoreURI $secretURI -SecretStoreType AzureKeyVault
New-AzDataProtectionBackupInstance -SubscriptionId $sub -ResourceGroupName "ResourceGroupName" -VaultName "vaultName" -BackupInstance $instance
```

```output
Name                                                                Type                                                  BackupInstanceName
----                                                                ----                                                  ------------------
xyz-postgresql-wus-empdb10-xxxxxxxx-xxxx-xxxx-a3ba-be75108d8b21 Microsoft.DataProtection/backupVaults/backupInstances xyz-postgresql-wus-empdb10-xxxxxxxx-xxxx-xxxx-a3ba-be75108d8b21

```

Perintah ketiga menginisialisasi secretURI untuk autentikasi secret store.

Perintah kelima mendapatkan kebijakan yang akan dilindungi database.
Perintah keenam menginisialisasi objek permintaan instans cadangan.
Perintah terakhir mengonfigurasi cadangan $dataSourceId yang diberikan dalam kubah cadangan.

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
Objek permintaan instans cadangan yang akan digunakan untuk mengonfigurasi cadangan Untuk membangun, lihat bagian CATATAN untuk properti BACKUPINSTANCE dan membuat tabel hash.

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
Grup Sumber Daya dari kubah cadangan

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

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


BACKUPINSTANCE <IBackupInstanceResource>: Objek permintaan instans cadangan yang akan digunakan untuk mengonfigurasi cadangan
  - `[Property <IBackupInstance>]`: Properti BackupInstanceResource
    - `DataSourceInfo <IDatasource>`: Mendapatkan atau mengatur informasi sumber data.
      - `ResourceId <String>`: ARM LENGKAP ID sumber daya. Untuk sumber daya azure, ini adalah ID ARM. Untuk sumber daya non azure, id ini akan dibuat oleh layanan cadangan melalui Fabric/Vault.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Datasource.
      - `[ResourceUri <String>]`: Uri sumber daya.
      - `[Type <String>]`: DatasourceType sumber daya.
    - `ObjectType <String>`: 
    - `PolicyInfo <IPolicyInfo>`: Mendapatkan atau mengatur informasi kebijakan.
      - `PolicyId <String>`: 
      - `[PolicyParameter <IPolicyParameters>]`: Parameter kebijakan untuk instans cadangan
        - `[DataStoreParametersList <IDataStoreParameters[]>]`: Mendapatkan atau mengatur Parameter DataStore
          - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive
          - `ObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
    - `[DataSourceSetInfo <IDatasourceSet>]`: Mendapatkan atau mengatur informasi kumpulan sumber data.
      - `ResourceId <String>`: ARM LENGKAP ID sumber daya. Untuk sumber daya azure, ini adalah ID ARM. Untuk sumber daya non azure, id ini akan dibuat oleh layanan cadangan melalui Fabric/Vault.
      - `[DatasourceType <String>]`: DatasourceType sumber daya.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Datasource.
      - `[ResourceUri <String>]`: Uri sumber daya.
    - `[DatasourceAuthCredentials <IAuthCredentials>]`: Kredensial yang digunakan untuk mengautentikasi dengan penyedia sumber data.
      - `ObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
    - `[FriendlyName <String>]`: Mendapatkan atau mengatur nama yang mudah dikenali Instans Cadangan.

## RELATED LINKS

