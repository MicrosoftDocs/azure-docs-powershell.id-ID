---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: 331F32CB-7777-401C-A42A-23098944CFBE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupJob.md
ms.openlocfilehash: cbdb60fb4ec139b1dae92b7dd8e2e54675ae1f90
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142664722"
---
# Get-AzureRmBackupJob

## SYNOPSIS
Mendapatkan pekerjaan Pencadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### FilterSet (Default)
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
Cmdlet **Get-AzureRmBackupJob** mendapatkan pekerjaan Azure Backup untuk kubah tertentu.

## EXAMPLES

### Contoh 1: Dapatkan semua pekerjaan dalam kubah Cadangan
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> Get-AzureRmBackupJob -Vault $Vault
WorkloadName    Operation       Status          StartTime              EndTime
------------    ---------       ------          ---------              -------
co03-vm         Backup          InProgress      26-Aug-15 12:24:01 PM  01-Jan-01 12:00:00 AM
co03-vm         ConfigureBackup Completed       26-Aug-15 12:19:49 PM  26-Aug-15 12:19:54 PM
co03-vm         Register        Completed       25-Aug-15 3:23:53 PM   25-Aug-15 3:25:00 PM
```

Perintah pertama mendapatkan kubah bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault** .
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan semua pekerjaan untuk brankas dalam $Vault.

### Contoh 2: Dapatkan pekerjaan yang sudah selesai
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -Status Completed
WorkloadName    Operation       Status          StartTime              EndTime
------------    ---------       ------          ---------              -------
co03-vm         Register        Completed       25-Aug-15 3:23:53 PM   25-Aug-15 3:25:00 PM
```

Perintah ini akan menyelesaikan pekerjaan dari brankas di $Vault.

### Contoh 3: Dapatkan pekerjaan yang gagal untuk minggu lalu
```
PS C:\>Get-AzureRmBackupJob -Vault $Vault -From (Get-Date).AddDays(-7) -Status Failed
```

Perintah ini mendapatkan pekerjaan yang gagal dari minggu lalu dari lemari besi di $Vault.
Parameter *Dari* menentukan waktu tujuh hari di masa lalu.
Perintah tidak menentukan nilai untuk parameter *Kepada* .
Oleh karena itu, aplikasi ini menggunakan nilai default dari waktu saat ini.

### Contoh 4: Pencadangan Polling untuk pekerjaan yang sedang berlangsung yang selesai
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
Baris pertama skrip mendapatkan semua pekerjaan dalam $Vault yang sedang berlangsung, lalu menyimpan pekerjaan tersebut dalam variabel array $Jobs.
Baris kedua menyimpan pekerjaan pertama dari array $Jobs dalam variabel $Job.
Baris ketiga dimulai **beberapa saat** pengulangan yang memeriksa status pekerjaan saat ini hingga pekerjaan selesai.
Untuk informasi tentang **kata kunci saat ini**, ketik .`Get-Help about_While`
**Saat** pengulangan menulis pesan ke konsol, tidur selama sepuluh detik, lalu memperbarui variabel $Job.
Skrip memperbarui variabel $Job dengan menggunakan nilai $Job yang sudah ada dan cmdlet saat ini untuk mendapatkan status pekerjaan saat ini.
Untuk informasi tentang cmdlet Windows PowerShell, ketik `Get-Help Write-Host` dan `Get-Help Start-Sleep`.
Baris terakhir skrip memberi tahu Anda bahwa skrip telah selesai.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Menentukan mulai, sebagai objek **DateTime** , dari rentang waktu untuk pekerjaan yang didapat cmdlet ini.
Untuk mendapatkan objek **DateTime** , gunakan cmdlet Get-Date.
Untuk informasi selengkapnya tentang objek **DateTime**, ketik .`Get-Help Get-Date`

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
Menentukan pekerjaan yang didapat cmdlet ini.
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan cmdlet Get-AzureRmBackupJob.

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
Menentukan ID pekerjaan yang didapat cmdlet ini.
ID adalah properti **InstanceId** dari objek **AzureRmBackupJob** .
Untuk mendapatkan objek **AzureRmBackupJob** , gunakan Get-AzureRmBackupJob.

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
Menentukan operasi pekerjaan yang didapat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- Cadangan 
- Mengonfigurasi Kembali 
- DeleteBackupData 
- Daftar 
- Mengembalikan 
- Buka Proteksi 
- Batalkan pendaftaran

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
Menentukan status pekerjaan yang didapat cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- InProgress
- Gagal
- Dibatalkan
- Membatalkan
- Selesai
- CompletedWithWarnings Anda dapat menentukan parameter ini untuk menemukan semua pekerjaan yang sedang berlangsung atau semua pekerjaan yang gagal.

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

### -Kepada
Menentukan akhir, sebagai objek **DateTime** , dari rentang waktu untuk pekerjaan yang didapat cmdlet ini.
Nilai default adalah waktu sistem saat ini.
Jika menentukan parameter ini, Anda juga harus menentukan parameter *Dari* .

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
Menentukan tipe kontainer di mana cmdlet ini mendapatkan pekerjaan cadangan.
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
Menentukan kubah Cadangan tempat cmdlet ini mendapatkan pekerjaan.
Untuk mendapatkan objek **AzureRmBackupVault** , gunakan cmdlet Get-AzureRmBackupVault.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter: Vault (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupJob

## NOTES
* Tidak

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Stop-AzureRmBackupJob](./Stop-AzureRmBackupJob.md)

[Tunggu-AzureRmBackupJob](./Wait-AzureRmBackupJob.md)


