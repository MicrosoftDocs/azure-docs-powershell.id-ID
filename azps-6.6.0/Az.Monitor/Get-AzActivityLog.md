---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azactivitylog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
ms.openlocfilehash: 730f23ac6fe021d5ee512ed46ffa4b01a93fc7b7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140076239"
---
# Get-AzActivityLog

## SYNOPSIS
Ambil kejadian Log Aktivitas.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.monitor/get-azactivitylog) untuk informasi terkini.

## SYNTAX

### GetByCorrelationId
```
Get-AzActivityLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-CorrelationId] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByResourceId
```
Get-AzActivityLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceId] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByResourceGroup
```
Get-AzActivityLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceGroupName] <String> [-MaxRecord <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceProvider
```
Get-AzActivityLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceProvider] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetBySubscription
```
Get-AzActivityLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzActivityLog mengambil kejadian Log Aktivitas. Kejadian bisa dikaitkan dengan ID langganan, ID korelasi, grup sumber daya, ID sumber daya, atau penyedia sumber daya.

## EXAMPLES

### Contoh 1: Dapatkan log kejadian dengan ID langganan
```
PS C:\>Get-AzActivityLog
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna, yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 2: Mendapatkan log kejadian berdasarkan ID langganan dengan jumlah maksimum kejadian
```
PS C:\>Get-AzActivityLog -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID langganan pengguna, yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 3: Dapatkan log kejadian berdasarkan ID langganan dengan waktu mulai.
```
PS C:\>Get-AzActivityLog -StartTime 2017-06-01T10:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 06-06-01T10:30 waktu lokal jika tanggal/waktu tersebut tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 4: Dapatkan log kejadian menurut ID langganan dengan waktu mulai dan waktu berakhir.
```
PS C:\>Get-AzActivityLog -StartTime 2017-04-01T10:30 -EndTime 2017-04-14T11:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 04-01-01T10-30 waktu lokal 2017-04-14T11:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 5: Mendapatkan log kejadian menurut ID korelasi
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 6: Mendapatkan log kejadian menurut ID korelasi dengan jumlah maksimum kejadian
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID korelasi tertentu yang terjadi 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 7: Dapatkan log kejadian menurut ID korelasi dan waktu mulai
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu lokal jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 8: Mendapatkan log kejadian menurut ID korelasi dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-04-15T04:30:00 -EndTime 2017-04-25T12:30:00
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi pada atau setelah 2017-04-15T04:30 waktu lokal, tetapi sebelum 04-04-25T12:30 waktu lokal jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, misalnya: periode penyimpanan.

### Contoh 9: Dapatkan log kejadian untuk grup sumber daya
```
PS C:\>Get-AzActivityLog -ResourceGroupName "Contoso-Web-CentralUS"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 10: Mendapatkan log kejadian untuk grup sumber daya dengan jumlah kejadian maksimum
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 11: Mendapatkan log kejadian untuk grup sumber daya menurut waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi pada atau setelah 05-05-22T04:30:00 waktu lokal 2017-05-2017 jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 12: Mendapatkan log aktivitas untuk grup sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 13: Dapatkan log kejadian berdasarkan ID sumber daya
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 14: Dapatkan log kejadian menurut ID sumber daya dengan jumlah kejadian maksimum
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 15: Dapatkan log kejadian menurut ID sumber daya dengan waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak kejadian 1000 yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 05-05-22T04:30:00 waktu lokal 2017-05-2017 jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 16: Mendapatkan log kejadian menurut ID sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 17: Dapatkan log kejadian oleh penyedia sumber daya
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 18: Mendapatkan log kejadian menurut penyedia sumber daya dengan jumlah maksimum kejadian
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 19: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi pada atau setelah 05-05-22T04:30:00 waktu lokal 2017-05-2017 jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 20: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

## PARAMETERS

### -Caller
Penelepon acara untuk diambil

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CorrelationId
The CorrelationId

```yaml
Type: System.String
Parameter Sets: GetByCorrelationId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DetailOutput
Mengembalikan objek dengan semua detail kejadian (defaultnya adalah untuk mengembalikan beberapa atribut saja, misalnya tidak ada detail)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Waktuh akhir kueri

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxRecord
Jumlah maksimum rekaman untuk diambil.
Alias: MaxRecords, MaxEvents

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: GetByResourceGroup
Aliases: ResourceGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
The ResourceId

```yaml
Type: System.String
Parameter Sets: GetByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceProvider
Nama ResourceProvider

```yaml
Type: System.String
Parameter Sets: GetByResourceProvider
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Id korelasi kueri

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Status acara untuk diambil

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.String

### System.Management.Automation.SwitchParameter

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSEventData

## CATATAN

## RELATED LINKS
