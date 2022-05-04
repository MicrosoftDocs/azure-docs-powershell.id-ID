---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azactivitylog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLog.md
ms.openlocfilehash: 36e40d713eb7bd4e41044cbb16ae888351398f22
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144738838"
---
# Get-AzActivityLog

## SYNOPSIS
Mengambil peristiwa Log Aktivitas.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/get-azactivitylog) untuk informasi terbaru.

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
Cmdlet Get-AzActivityLog mengambil peristiwa Log Aktivitas. Peristiwa dapat dikaitkan dengan ID langganan saat ini, ID korelasi, grup sumber daya, ID sumber daya, atau penyedia sumber daya.

## EXAMPLES

### Contoh 1: Mendapatkan log peristiwa berdasarkan ID langganan
```powershell
Get-AzActivityLog
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID langganan pengguna yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 2: Mendapatkan log peristiwa berdasarkan ID langganan dengan jumlah maksimum peristiwa
```powershell
Get-AzActivityLog -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 peristiwa yang terkait dengan ID langganan pengguna yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 3: Dapatkan log peristiwa berdasarkan ID langganan dengan waktu mulai.
```powershell
Get-AzActivityLog -StartTime 2017-06-01T10:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 2017-06-01T10:30 waktu setempat jika tanggal/waktu tersebut tidak lebih lama dari 90 hari dari tanggal/waktu saat ini.

### Contoh 4: Dapatkan log peristiwa berdasarkan ID langganan dengan waktu mulai dan waktu akhir.
```powershell
Get-AzActivityLog -StartTime 2017-04-01T10:30 -EndTime 2017-04-14T11:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 2017-04-01T10:30 waktu setempat, dan sebelum 2017-04-14T11:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode retensi.

### Contoh 5: Mendapatkan log peristiwa dengan ID korelasi
```powershell
Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23"
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID korelasi yang ditentukan yang berlangsung 7 hari sejak tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu peristiwa.

### Contoh 6: Mendapatkan log peristiwa dengan ID korelasi dengan jumlah maksimum peristiwa
```powershell
Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 peristiwa yang terkait dengan ID korelasi yang ditentukan yang berlangsung 7 hari sejak tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu peristiwa.

### Contoh 7: Mendapatkan log peristiwa dengan ID korelasi dan waktu mulai
```powershell
Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID korelasi yang ditentukan yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.
**CATATAN**: ini biasanya hanya satu peristiwa.

### Contoh 8: Mendapatkan log peristiwa dengan ID korelasi dengan waktu mulai dan waktu akhir
```powershell
Get-AzActivityLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-04-15T04:30:00 -EndTime 2017-04-25T12:30:00
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID korelasi yang ditentukan yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum 2017-04-25T12:30 waktu setempat jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode retensi.

### Contoh 9: Mendapatkan log peristiwa untuk grup sumber daya
```powershell
Get-AzActivityLog -ResourceGroupName "Contoso-Web-CentralUS"
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan grup sumber daya yang ditentukan yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 10: Mendapatkan log peristiwa untuk grup sumber daya dengan jumlah maksimum peristiwa
```powershell
Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 peristiwa yang terkait dengan grup sumber daya yang ditentukan yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 11: Mendapatkan log peristiwa untuk grup sumber daya berdasarkan waktu mulai
```powershell
Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan grup sumber daya yang ditentukan yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 12: Mendapatkan log peristiwa untuk grup sumber daya dengan waktu mulai dan waktu akhir
```powershell
Get-AzActivityLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan grup sumber daya yang ditentukan yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode retensi.

### Contoh 13: Mendapatkan log peristiwa berdasarkan ID sumber daya
```powershell
Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1"
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID sumber daya yang ditentukan yang berlangsung 7 hari dari tanggal/waktu saat ini.

### Contoh 14: Mendapatkan log peristiwa berdasarkan ID sumber daya dengan jumlah maksimum peristiwa
```powershell
Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 peristiwa yang terkait dengan ID sumber daya yang ditentukan yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 15: Mendapatkan log peristiwa berdasarkan ID sumber daya dengan waktu mulai
```powershell
Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID sumber daya yang ditentukan yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 16: Mendapatkan log peristiwa berdasarkan ID sumber daya dengan waktu mulai dan waktu akhir
```powershell
Get-AzActivityLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan ID sumber daya yang ditentukan yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode retensi.

### Contoh 17: Mendapatkan log peristiwa menurut penyedia sumber daya
```powershell
Get-AzActivityLog -ResourceProvider "Microsoft.Web"
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan penyedia sumber daya tertentu yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 18: Mendapatkan log peristiwa oleh penyedia sumber daya dengan jumlah maksimum peristiwa
```powershell
Get-AzActivityLog -ResourceProvider "Microsoft.Web" -MaxRecord 100
```

Perintah ini mencantumkan paling banyak 100 peristiwa yang terkait dengan penyedia sumber daya tertentu yang berlangsung 7 hari sejak tanggal/waktu saat ini.

### Contoh 19: Mendapatkan log peristiwa oleh penyedia sumber daya dengan waktu mulai
```powershell
Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan penyedia sumber daya tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu setempat jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 20: Mendapatkan log peristiwa oleh penyedia sumber daya dengan waktu mulai dan waktu akhir
```powershell
Get-AzActivityLog -ResourceProvider "Microsoft.Web" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan paling banyak 1000 peristiwa yang terkait dengan penyedia sumber daya yang ditentukan yang terjadi pada atau setelah 2017-04-15T04:30 waktu setempat, tetapi sebelum waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, yaitu: periode retensi.

## PARAMETERS

### -Penelepon
Pemanggil peristiwa yang akan diambil

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
Mengembalikan objek dengan semua detail peristiwa (defaultnya adalah mengembalikan hanya beberapa atribut, yaitu tidak ada detail)

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
Jumlah maksimum rekaman yang akan diambil.
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
Status peristiwa yang akan diambil

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.String

### System.Management.Automation.SwitchParameter

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSEventData

## NOTES

## RELATED LINKS
