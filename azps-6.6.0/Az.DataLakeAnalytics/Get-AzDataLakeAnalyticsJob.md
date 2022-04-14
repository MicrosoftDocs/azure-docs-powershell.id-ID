---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
ms.assetid: A0293D80-5935-4D2C-AF11-2837FEC95760
online version: https://docs.microsoft.com/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticsjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsJob.md
ms.openlocfilehash: 0d6668627f3ebfe708d80293c39c55c879a41c18
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142233991"
---
# Get-AzDataLakeAnalyticsJob

## SYNOPSIS
Mendapatkan pekerjaan Data Lake Analytics.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticsjob) untuk informasi terbaru.

## SYNTAX

### GetAllInResourceGroupAndAccount (Default)
```
Get-AzDataLakeAnalyticsJob [-Account] <String> [[-Name] <String>] [[-Submitter] <String>]
 [[-SubmittedAfter] <DateTimeOffset>] [[-SubmittedBefore] <DateTimeOffset>] [[-State] <JobState[]>]
 [[-Result] <JobResult[]>] [-Top <Int32>] [-PipelineId <Guid>] [-RecurrenceId <Guid>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetBySpecificJobInformation
```
Get-AzDataLakeAnalyticsJob [-Account] <String> [-JobId] <Guid> [[-Include] <ExtendedJobData>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataLakeAnalyticsJob** mendapatkan pekerjaan Azure Data Lake Analytics.
Jika Anda tidak menentukan pekerjaan, cmdlet ini mendapatkan semua pekerjaan.

## EXAMPLES

### Contoh 1: Dapatkan pekerjaan yang ditentukan
```
PS C:\>Get-AzDataLakeAnalyticsJob -Account "contosoadla" -JobId $JobID01
```

Perintah ini mendapatkan pekerjaan dengan ID yang ditentukan.

### Contoh 2: Mendapatkan pekerjaan yang dikirim dalam seminggu terakhir
```
PS C:\>Get-AzDataLakeAnalyticsJob -Account "contosoadla" -SubmittedAfter (Get-Date).AddDays(-7)
```

Perintah ini mendapatkan pekerjaan yang dikirimkan dalam seminggu terakhir.

## PARAMETERS

### -Akun
Menentukan nama akun Data Lake Analytics.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Sertakan
Menentukan opsi yang menunjukkan tipe informasi tambahan untuk mengambil pekerjaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak
- DebugInfo
- Statistik
- Semua

```yaml
Type: Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+ExtendedJobData
Parameter Sets: GetBySpecificJobInformation
Aliases:
Accepted values: None, All, DebugInfo, Statistics

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang akan didapatkan.

```yaml
Type: System.Guid
Parameter Sets: GetBySpecificJobInformation
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nama
Menentukan nama yang akan digunakan untuk memfilter hasil daftar pekerjaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak
- DebugInfo
- Statistik
- Semua

```yaml
Type: System.String
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PipelineId
ID opsional yang menunjukkan hanya sebagian pekerjaan dari pipeline yang ditentukan yang harus dikembalikan.

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecurrenceId
ID opsional yang menunjukkan hanya sebagian pekerjaan dari pengulangan yang ditentukan yang harus dikembalikan.

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Hasil
Menentukan filter hasil untuk hasil pekerjaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Tidak
- Dibatalkan
- Gagal
- Berhasil

```yaml
Type: Microsoft.Azure.Management.DataLake.Analytics.Models.JobResult[]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:
Accepted values: None, Succeeded, Cancelled, Failed

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan filter status untuk hasil pekerjaan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Diterima
- Baru
- Kompilasi
- Penjadwalan
- Antri
- Mulai
- Berhenti
- Menjalankan
- Berakhir

```yaml
Type: Microsoft.Azure.Management.DataLake.Analytics.Models.JobState[]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:
Accepted values: Accepted, Compiling, Ended, New, Queued, Running, Scheduling, Starting, Paused, WaitingForCapacity

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubmittedAfter
Menentukan filter tanggal.
Gunakan parameter ini untuk memfilter hasil daftar pekerjaan ke pekerjaan yang dikirim setelah tanggal yang ditentukan.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DikirimBefore
Menentukan filter tanggal.
Gunakan parameter ini untuk memfilter hasil daftar pekerjaan ke pekerjaan yang dikirimkan sebelum tanggal yang ditentukan.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Submitter
Menentukan alamat email pengguna.
Gunakan parameter ini untuk memfilter hasil daftar pekerjaan ke pekerjaan yang dikirimkan oleh pengguna tertentu.

```yaml
Type: System.String
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Top
Nilai opsional yang menunjukkan jumlah pekerjaan yang akan dikembalikan. Nilai defaultnya adalah 500

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: GetAllInResourceGroupAndAccount
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Guid

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.DataLakeAnalyticsEnums+ExtendedJobData

### System.Nullable'1[[System.DateTimeOffset, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Management.DataLake.Analytics.Models.JobState[]

### Microsoft.Azure.Management.DataLake.Analytics.Models.JobResult[]

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Nullable'1[[System.Guid, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Management.DataLake.Analytics.Models.JobInformation

## CATATAN

## RELATED LINKS

[Stop-AzDataLakeAnalyticsJob](./Stop-AzDataLakeAnalyticsJob.md)

[Kirim-AzDataLakeAnalyticsJob](./Submit-AzDataLakeAnalyticsJob.md)

[Wait-AzDataLakeAnalyticsJob](./Wait-AzDataLakeAnalyticsJob.md)


