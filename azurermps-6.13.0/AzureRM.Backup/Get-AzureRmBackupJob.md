---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 331F32CB-7777-401C-A42A-23098944CFBE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJob.md
ms.openlocfilehash: cbdb60fb4ec139b1dae92b7dd8e2e54675ae1f90
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426336"
---
# Get-AzureRmBackupJob

## SYNOPSIS
Mendapatkan pekerjaan Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### FiltersSet (Default)
```
Get-AzureRmBackupJob -Vault <AzureRMBackupVault> [-JobId <String>] [-From <DateTime>] [-To <DateTime>]
 [-Status <String>] [-Type <String>] [-Operation <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### JobsListFilter
```
Get-AzureRmBackupJob -Job <AzureRMBackupJob> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupJob** mendapatkan pekerjaan Azure Backup untuk vault tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan semua pekerjaan di vault Backup
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> Get-AzureRmBackupJob -Vault $Vault
WorkloadName    Operation       Status          StartTime              EndTime
------------    ---------       ------          ---------              -------
co03-vm         Backup          InProgress      26-Aug-15 12:24:01 PM  01-Jan-01 12:00:00 AM
co03-vm         ConfigureBackup Completed       26-Aug-15 12:19:49 PM  26-Aug-15 12:19:54 PM
co03-vm         Register        Completed       25-Aug-15 3:23:53 PM   25-Aug-15 3:25:00 PM
```

Perintah pertama mengambil vault bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault.**
Perintah menyimpan objek tersebut dalam $Vault variabel.
Perintah kedua mendapatkan semua pekerjaan untuk vault di $Vault.

### Contoh 2: Mendapatkan pekerjaan yang telah selesai
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -Status Completed
WorkloadName    Operation       Status          StartTime              EndTime
------------    ---------       ------          ---------              -------
co03-vm         Register        Completed       25-Aug-15 3:23:53 PM   25-Aug-15 3:25:00 PM
```

Perintah ini menyelesaikan pekerjaan dari vault di $Vault.

### Contoh 3: Mendapatkan pekerjaan yang gagal untuk minggu lalu
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -From (Get-Date).AddDays(-7) -Status Failed
```

Perintah ini gagal dari minggu lalu dari penyimpanan di $Vault.
Parameter *Dari* menentukan waktu tujuh hari sebelumnya.
Perintah tidak menentukan nilai untuk parameter *To.*
Oleh karena itu, menggunakan nilai default waktu saat ini.

### Contoh 4: Cadangan Polling untuk pekerjaan yang sedang berlangsung yang selesai
```
PS C:\>$Jobs = Get-AzureRmBackupJob -Vault $Vault -Status InProgress
$Job = $Jobs[0] 
while ( $Job.Status -ne Completed ) 
{
   Write-Host "Waiting for completion..." 
   Start-Sleep -Seconds 10
   $job = Get-AzureRmBackupJob -Vault $Vault -Job $Job
}
Write-Host "Done!"
Waiting for completion... 
Waiting for completion... 
Waiting for completion... 
Done!
```

Skrip ini menjajaki pekerjaan pertama yang saat ini sedang berlangsung hingga pekerjaan selesai.
Baris pertama skrip mendapatkan semua pekerjaan di $Vault yang sedang berlangsung, lalu menyimpan pekerjaan tersebut di $Jobs array baru.
Baris kedua menyimpan pekerjaan pertama dari $Jobs larik di $Job baru.
Baris ketiga dimulai **pengulangan** sementara yang memeriksa status pekerjaan saat ini hingga pekerjaan selesai.
Untuk informasi tentang kata **kunci** sementara, ketik `Get-Help about_While` .
The **while** loop writes a message to the console, sleeps for ten seconds, and then updates the $Job variable.
Skrip memperbarui $Job variabel dengan menggunakan nilai pekerjaan yang sudah $Job dan cmdlet saat ini untuk mendapatkan status pekerjaan saat ini.
Untuk informasi tentang cmdlet Windows PowerShell, ketik `Get-Help Write-Host` dan `Get-Help Start-Sleep` .
Baris terakhir skrip memberi tahu Anda bahwa skrip telah selesai.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dari
Menentukan mulai, sebagai objek **DateTime,** rentang waktu untuk pekerjaan yang cmdlet ini dapatkan.
Untuk mendapatkan objek **DateTime,** gunakan cmdlet Get-Date.
Untuk informasi selengkapnya tentang **objek DateTime,** ketik `Get-Help Get-Date` .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: FiltersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan pekerjaan yang akan dilakukan cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupJob,** gunakan cmdlet Get-AzureRmBackupJob cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob
Parameter Sets: JobsListFilter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang akan dapatkan cmdlet ini.
ID adalah properti **InstanceId** dari objek **AzureRmBackupJob.**
Untuk mendapatkan objek **AzureRmBackupJob,** gunakan Get-AzureRmBackupJob.

```yaml
Type: System.String
Parameter Sets: FiltersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operasi
Menentukan operasi pekerjaan yang akan dilakukan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Pencadangan 
- ConfigureBackup 
- DeleteBackupData 
- Daftar 
- Pulihkan 
- Buka Proteksi 
- Pisahkan pendaftaran

```yaml
Type: System.String
Parameter Sets: FiltersSet
Aliases:
Accepted values: Backup, ConfigureBackup, DeleteBackupData, Register, Restore, UnProtect, Unregister

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status pekerjaan yang cmdlet ini dapatkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- InProgress
- Gagal
- Dibatalkan
- Membatalkan
- Selesai
- CompletedWithWarnings Anda bisa menentukan parameter ini untuk menemukan semua pekerjaan yang sedang berlangsung atau semua pekerjaan yang gagal.

```yaml
Type: System.String
Parameter Sets: FiltersSet
Aliases:
Accepted values: Cancelled, Cancelling, Completed, CompletedWithWarnings, Failed, InProgress

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ke
Menentukan akhir, sebagai objek **DateTime,** rentang waktu untuk pekerjaan yang cmdlet ini dapatkan.
Nilai default adalah waktu sistem saat ini.
Jika Anda menentukan parameter ini, Anda juga harus menentukan parameter *From.*

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: FiltersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe wadah di mana cmdlet ini mendapatkan pekerjaan pencadangan.
Saat ini, satu-satunya nilai yang didukung adalah AzureVM.

```yaml
Type: System.String
Parameter Sets: FiltersSet
Aliases:
Accepted values: AzureVM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan pekerjaan cmdlet pencadangan seperti yang dilakukan cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupVault,** gunakan cmdlet Get-AzureRmBackupVault cmdlet.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: FiltersSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter: Vault (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## CATATAN
* Tidak ada

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Stop-AzureRmBackupJob](./Stop-AzureRmBackupJob.md)

[Wait-AzureRmBackupJob](./Wait-AzureRmBackupJob.md)


