---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azactivitylog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
ms.openlocfilehash: 730f23ac6fe021d5ee512ed46ffa4b01a93fc7b7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142109555"
---
# Get-AzActivityLog

## SYNOPSIS
Mengambil aktivitas Log Aktivitas.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.monitor/get-azactivitylog) untuk informasi terbaru.

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
Cmdlet Get-AzActivityLog mengambil kejadian Log Aktivitas. Kejadian dapat dikaitkan dengan ID langganan saat ini, ID korlasi, grup sumber daya, ID sumber daya, atau penyedia sumber daya.

## EXAMPLES

### Contoh 1: Mendapatkan log kejadian menurut ID langganan
```
PS C:\>Get-AzActivityLog
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 2: Dapatkan log kejadian berdasarkan ID langganan dengan jumlah peristiwa maksimum
```
PS C:\>Get-AzActivityLog -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID langganan pengguna yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 3: Dapatkan log kejadian menurut ID langganan dengan waktu mulai.
```
PS C:\>Get-AzActivityLog -StartTime 2017-06-01T10:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang berlangsung pada atau setelah 2017-06-01T10:30 waktu setempat jika tanggal/waktu tersebut tidak lebih lama dari 90 hari dari tanggal/waktu saat ini.

### Contoh 4: Dapatkan log kejadian menurut ID langganan dengan waktu mulai dan waktu akhir.
```
PS C:\>Get-AzActivityLog -StartTime 2017-04-01T10:30 -EndTime 2017-04-14T11:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang berlangsung pada atau setelah 2017-04-01T10:30 waktu setempat, dan sebelum 2017-04-14T11:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 5: Dapatkan log kejadian menurut ID korlasi
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korlasi tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 6: Dapatkan log kejadian menurut ID korlasi dengan jumlah peristiwa maksimum
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID korlasi tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 7: Dapatkan log kejadian menurut ID korlasi dan waktu mulai
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korlasi tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 8: Mendapatkan log kejadian berdasarkan ID korlasi dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-04-15T04:30:00 -EndTime 2017-04-25T12:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korlasi tertentu yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum 2017-04-25T12:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 9: Mendapatkan log kejadian untuk grup sumber daya
```
PS C:\>Get-AzActivityLog -ResourceGroupName "Contoso-Web-CentralUS"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 10: Mendapatkan log kejadian untuk grup sumber daya dengan jumlah peristiwa maksimum
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan grup sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 11: Mendapatkan log kejadian untuk grup sumber daya menurut waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang berlangsung pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih lama dari 90 hari dari tanggal/waktu saat ini.

### Contoh 12: Mendapatkan log kejadian untuk grup sumber daya dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang berlangsung pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum 2017-04-25T12:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 13: Mendapatkan log kejadian menurut ID sumber daya
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 14: Dapatkan log kejadian menurut ID sumber daya dengan jumlah peristiwa maksimum
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 15: Mendapatkan log kejadian menurut ID sumber daya dengan waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih lama dari 90 hari dari tanggal/waktu saat ini.

### Contoh 16: Mendapatkan log kejadian menurut ID sumber daya dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum 2017-04-25T12:30 waktu setempat jika rentang tanggal/waktu keseluruhan tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 17: Mendapatkan log kejadian menurut penyedia sumber daya
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 18: Mendapatkan log kejadian menurut penyedia sumber daya dengan jumlah peristiwa maksimum
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan penyedia sumber daya tertentu yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 19: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang berlangsung pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih lama dari 90 hari dari tanggal/waktu saat ini.

### Contoh 20: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang berlangsung pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum 2017-04-25T12:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

## PARAMETERS

### -Penelepon
Penelepon acara untuk mengambil

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

### -DetailedOutput
Mengembalikan objek dengan semua detail kejadian (defaultnya hanya mengembalikan beberapa atribut, misalnya tanpa detail)

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
EndTime kueri

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
Jumlah maksimum rekaman yang akan disambungkan.
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
CorrelationId kueri

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
Status acara untuk mengambil

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.String

### System.Management.Automation.SwitchParameter

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSEventData

## CATATAN

## RELATED LINKS
