---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataLakeAnalytics.dll-Help.xml
Module Name: Az.DataLakeAnalytics
online version: https://docs.microsoft.com/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticsjobrecurrence
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsJobRecurrence.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataLakeAnalytics/DataLakeAnalytics/help/Get-AzDataLakeAnalyticsJobRecurrence.md
ms.openlocfilehash: bc105168b3d79511996f9645f46068f6b461a2fa
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142271671"
---
# Get-AzDataLakeAnalyticsJobRecurrence

## SYNOPSIS
Mendapatkan pekerjaan Data Lake Analytics pengulangan atau pengulangan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datalakeanalytics/get-azdatalakeanalyticsjobrecurrence) untuk informasi terbaru.

## SYNTAX

### GetAllInAccount (Default)
```
Get-AzDataLakeAnalyticsJobRecurrence [-Account] <String> [-SubmittedAfter <DateTimeOffset>]
 [-SubmittedBefore <DateTimeOffset>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetBySpecificJobRecurrence
```
Get-AzDataLakeAnalyticsJobRecurrence [-Account] <String> [-RecurrenceId] <Guid>
 [-SubmittedAfter <DateTimeOffset>] [-SubmittedBefore <DateTimeOffset>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzDataLakeAnalyticsJobRecurrence** mendapatkan Pengulangan Azure Data Lake Analytics Job tertentu atau daftar pengulangan.

## EXAMPLES

### Contoh 1: Dapatkan pengulangan yang ditentukan
```
PS C:\>Get-AzDataLakeAnalyticsJobRecurrence -Account "contosoadla" -RecurrenceId 83cb7ad2-3523-4b82-b909-d478b0d8aea3
```

Perintah ini mendapatkan pengulangan pekerjaan yang ditentukan dengan id '83cb7ad2-3523-4b82-b909-d478b0d8aea3' dalam akun 'contosoadla'.

### Contoh 2: Dapatkan daftar semua pengulangan dalam akun
```
PS C:\>Get-AzDataLakeAnalyticsJobRecurrence -AccountName "contosoadla"
```

Perintah ini mendapatkan daftar semua pengulangan dalam akun "contosoadla"

## PARAMETERS

### -Akun
Nama nama akun Data Lake Analytics yang ingin diambil pengulangan pekerjaannya.

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

### -RecurrenceId
ID pengulangan pekerjaan tertentu untuk mengembalikan informasi.

```yaml
Type: System.Guid
Parameter Sets: GetBySpecificJobRecurrence
Aliases: Id

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SubmittedAfter
Filter opsional yang mengembalikan pengulangan pekerjaan hanya dikirimkan setelah waktu yang ditentukan.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DikirimBefore
Filter opsional yang mengembalikan pengulangan pekerjaan hanya dikirimkan sebelum waktu yang ditentukan.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: (All)
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

### System.Nullable'1[[System.DateTimeOffset, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.DataLakeAnalytics.Models.PSJobRecurrenceInformation

## CATATAN

## RELATED LINKS
