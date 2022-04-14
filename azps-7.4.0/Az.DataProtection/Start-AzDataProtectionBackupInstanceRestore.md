---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/start-azdataprotectionbackupinstancerestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Start-AzDataProtectionBackupInstanceRestore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Start-AzDataProtectionBackupInstanceRestore.md
ms.openlocfilehash: 2dcf8cac7f2b3503cc2a5073365cb355e13ec960
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141998238"
---
# Start-AzDataProtectionBackupInstanceRestore

## SYNOPSIS
Pemulihan pemicu untuk BackupInstance

## SYNTAX

### Pemicu (Default)
```
Start-AzDataProtectionBackupInstanceRestore -BackupInstanceName <String> -ResourceGroupName <String>
 -VaultName <String> -Parameter <IAzureBackupRestoreRequest> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### TriggerExpanded
```
Start-AzDataProtectionBackupInstanceRestore -BackupInstanceName <String> -ResourceGroupName <String>
 -VaultName <String> -ObjectType <String> -RestoreTargetInfo <IRestoreTargetInfoBase>
 -SourceDataStoreType <SourceDataStoreType> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Pemulihan pemicu untuk BackupInstance

## EXAMPLES

### Contoh 1: Memicu pemulihan untuk disk azure yang dilindungi.
```powershell
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault"
$rp = Get-AzDataProtectionRecoveryPoint -SubscriptionId "xxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault" -BackupInstanceName $instance.Name
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureDisk -SourceDataStore OperationalStore -RestoreLocation "westus"  -RestoreType AlternateLocation -TargetResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.Compute/disks/{DiskName}" -RecoveryPoint $rp[0].name
Start-AzDataProtectionBackupInstanceRestore -BackupInstanceName $instance.BackupInstanceName -ResourceGroupName sarath-rg -VaultName sarath-vault -SubscriptionId "xxx-xxx-xxx" -Parameter $restorerequest

```



### Contoh 2: Pemulihan pemicu sebagai DB untuk AzureDatabaseForPostgreSQL yang dilindungi menggunakan secret store.
```powershell
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName"
$rp = Get-AzDataProtectionRecoveryPoint -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName" -BackupInstanceName $instance.Name
$targetResourceId = "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/resourceGroupName/providers/Microsoft.DBforPostgreSQL/servers/serverName/databases/targetDbName"
$secretURI = "https://oss-keyvault.vault.azure.net/secrets/oss-secret"
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureDatabaseForPostgreSQL -SourceDataStore VaultStore -RestoreLocation "westus" -RestoreType AlternateLocation -TargetResourceId $targetResourceId -RecoveryPoint $rp[0].Property.RecoveryPointId -SecretStoreURI $secretURI -SecretStoreType AzureKeyVault
$restoreJob = Start-AzDataProtectionBackupInstanceRestore -BackupInstanceName $instance.BackupInstanceName -ResourceGroupName resourceGroupName -VaultName vaultName -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Parameter $restorerequest
$jobid = $restoreJob.JobId.Split("/")[-1]
$jobstatus = "InProgress"
while($jobstatus -ne "Completed")
{
    Start-Sleep -Seconds 10
    $currentjob = Get-AzDataProtectionJob -Id $jobid -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName"
    $jobstatus = $currentjob.Status
}

```

Perintah pertama dan kedua mengambil contoh dan titik pemulihan untuk instans.
Perintah ketiga menginisialisasi $targetResourceId dengan Id database postgre target (targetDbName harus berupa nama database baru).
Perintah keempat menginisialisasi URI rahasia.
Perintah kelima keenam menginisialisasi dan memicu permintaan pemulihan AzureDatabaseForPostgreSQL dengan secret store.
Perintah ketujuh, delapan, kesembilan melacak pekerjaan pemulihan untuk diselesaikan.

### Contoh 3: Memicu pemulihan sebagai File untuk AzureDatabaseForPostgreSQL yang dilindungi.
```powershell
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName"
$rp = Get-AzDataProtectionRecoveryPoint -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName" -BackupInstanceName $instance.Name
$targetContainerURI = ""https://targetStorageAccount.blob.core.windows.net/targetContainerName""
$fileNamePrefix = "restore_as_files_12345"
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureDatabaseForPostgreSQL -SourceDataStore VaultStore -RestoreLocation "westus" -RestoreType RestoreAsFiles -RecoveryPoint $rp[0].Property.RecoveryPointId -TargetContainerURI $targetContainerURI -FileNamePrefix $fileNamePrefix
$restoreJob = Start-AzDataProtectionBackupInstanceRestore -BackupInstanceName $instance.BackupInstanceName -ResourceGroupName resourceGroupName -VaultName vaultName -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Parameter $restorerequest
$jobid = $restoreJob.JobId.Split("/")[-1]
$jobstatus = "InProgress"
while($jobstatus -ne "Completed")
{
    Start-Sleep -Seconds 10
    $currentjob = Get-AzDataProtectionJob -Id $jobid -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName"
    $jobstatus = $currentjob.Status
}

```

Perintah pertama dan kedua mengambil contoh dan titik pemulihan untuk instans.
Perintah ketiga menginisialisasi $targetContainerURI dengan id kontainer akun penyimpanan target.
Perintah keempat menginisialisasi prefiks nama file untuk pemulihan.
Perintah kelima keenam menginisialisasi dan memicu permintaan pemulihan AzureDatabaseForPostgreSQL dengan secret store.
Perintah ketujuh, delapan, kesembilan melacak pekerjaan pemulihan untuk diselesaikan.

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

### -NoWait
Jalankan perintah secara asinkron

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

### -ObjectType
.

```yaml
Type: System.String
Parameter Sets: TriggerExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter
Permintaan pemulihan cadangan Azure Untuk membangun, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupRestoreRequest
Parameter Sets: Trigger
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat kubah cadangan ada.

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

### -RestoreTargetInfo
Mendapatkan atau mengatur informasi target pemulihan.
Untuk membangun, lihat bagian CATATAN untuk properti RESTORETARGETINFO dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IRestoreTargetInfoBase
Parameter Sets: TriggerExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDataStoreType
Mendapatkan atau mengatur tipe penyimpanan data sumber.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.SourceDataStoreType
Parameter Sets: TriggerExpanded
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Nama kubah cadangan.

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

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupRestoreRequest

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IOperationJobExtendedInfo

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PARAMETER <IAzureBackupRestoreRequest>: Permintaan pemulihan cadangan Azure
  - `ObjectType <String>`: 
  - `RestoreTargetInfo <IRestoreTargetInfoBase>`: Mendapatkan atau mengatur informasi target pemulihan.
    - `ObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
    - `[RestoreLocation <String>]`: Wilayah Pemulihan Target
  - `SourceDataStoreType <SourceDataStoreType>`: Mendapatkan atau mengatur tipe penyimpanan data sumber.

RESTORETARGETINFO <IRestoreTargetInfoBase>: Mendapatkan atau mengatur informasi target pemulihan.
  - `ObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
  - `[RestoreLocation <String>]`: Wilayah Pemulihan Target

## RELATED LINKS

