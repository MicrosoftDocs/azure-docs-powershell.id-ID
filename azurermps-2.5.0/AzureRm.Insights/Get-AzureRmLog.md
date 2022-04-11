---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 85492E00-3776-4F20-A444-9C28CC6154B7
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.insights/get-azurermlog
schema: 2.0.0
ms.openlocfilehash: 2c63efe0d22f1582b0828f595ba8a72cd389b435
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140858618"
---
# Get-AzureRmLog

## SYNOPSIS
Mendapatkan log kejadian.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByCorrelationId
```
Get-AzureRmLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-CorrelationId] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByResourceId
```
Get-AzureRmLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceId] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByResourceGroup
```
Get-AzureRmLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceGroupName] <String> [-MaxRecord <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceProvider
```
Get-AzureRmLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-ResourceProvider] <String> [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetBySubscription
```
Get-AzureRmLog [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>] [-Caller <String>]
 [-DetailedOutput] [-MaxRecord <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmLog** mendapatkan log kejadian.
Kejadian bisa dikaitkan dengan ID langganan, ID korelasi, grup sumber daya, ID sumber daya, atau penyedia sumber daya.

## EXAMPLES

### Contoh 1: Dapatkan log kejadian dengan ID langganan
```
PS C:\>Get-AzureRmLog
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna, yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 2: Mendapatkan log kejadian berdasarkan ID langganan dengan jumlah maksimum kejadian
```
PS C:\>Get-AzureRmLog -MaxEvents 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID langganan pengguna, yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 3: Dapatkan log kejadian berdasarkan ID langganan dengan waktu mulai.
```
PS C:\>Get-AzureRmLog -StartTime 2017-06-01T10:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 06-06-01T10:30 waktu lokal jika tanggal/waktu tersebut tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 4: Dapatkan log kejadian menurut ID langganan dengan waktu mulai dan waktu berakhir.
```
PS C:\>Get-AzureRmLog -StartTime 2017-04-01T10:30 -EndTime 2017-04-14T11:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID langganan pengguna yang terjadi pada atau setelah 04-01-01T10-30 waktu lokal 2017-04-14T11:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 5: Mendapatkan log kejadian menurut ID korelasi
```
PS C:\>Get-AzureRmLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 6: Mendapatkan log kejadian menurut ID korelasi dengan jumlah maksimum kejadian
```
PS C:\>Get-AzureRmLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -MaxEvents 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID korelasi tertentu yang terjadi 7 hari dari tanggal/waktu saat ini. 
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 7: Dapatkan log kejadian menurut ID korelasi dan waktu mulai
```
PS C:\>Get-AzureRmLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu lokal jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.
**CATATAN**: ini biasanya hanya satu acara.

### Contoh 8: Mendapatkan log kejadian menurut ID korelasi dengan waktu mulai dan waktu akhir
```
PS C:\>Get-AzureRmLog -CorrelationId "60c694d0-e46f-4c12-bed1-9b7aef541c23" -StartTime 2017-04-15T04:30:00 -EndTime 2017-04-25T12:30:00
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan ID korelasi tertentu yang terjadi pada atau setelah 2017-04-15T04:30 waktu lokal, tetapi sebelum 04-04-25T12:30 waktu lokal jika seluruh rentang tanggal/waktu tidak lebih lama dari 90 hari dari tanggal/waktu saat ini, misalnya: periode penyimpanan.

### Contoh 9: Dapatkan log kejadian untuk grup sumber daya
```
PS C:\>Get-AzureRmLog -ResourceGroupName "Contoso-Web-CentralUS"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 10: Mendapatkan log kejadian untuk grup sumber daya dengan jumlah kejadian maksimum
```
PS C:\>Get-AzureRmLog -ResourceGroup "Contoso-Web-CentralUS" -MaxEvents 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 11: Mendapatkan log kejadian untuk grup sumber daya menurut waktu mulai
```
PS C:\>Get-AzureRmLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-05-22T04:30:00
```

Perintah ini mencantumkan paling banyak 1000 kontak yang terkait dengan grup sumber daya tertentu yang terjadi pada atau setelah 2017-05-22T04:30:00 waktu lokal jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 12: Mendapatkan log aktivitas untuk grup sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzureRmLog -ResourceGroup "Contoso-Web-CentralUS" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan grup sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 13: Dapatkan log kejadian berdasarkan ID sumber daya
```
PS C:\>Get-AzureRmLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 14: Dapatkan log kejadian menurut ID sumber daya dengan jumlah kejadian maksimum
```
PS C:\>Get-AzureRmLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -MaxEvents 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 15: Dapatkan log kejadian menurut ID sumber daya dengan waktu mulai
```
PS C:\>Get-AzureRmLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak kejadian 1000 yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 05-05-22T04:30:00 waktu lokal 2017-05-2017 jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 16: Mendapatkan log kejadian menurut ID sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzureRmLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/ResourceGroups/Contoso-Web-CentralUS/providers/Microsoft.Web/ServerFarms/Contoso1" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan ID sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

### Contoh 17: Dapatkan log kejadian oleh penyedia sumber daya
```
PS C:\>Get-AzureRmLog -ResourceProvider "Microsoft.Web"
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 18: Mendapatkan log kejadian menurut penyedia sumber daya dengan jumlah maksimum kejadian
```
PS C:\>Get-AzureRmLog -ResourceProvider "Microsoft.Web" -MaxEvents 100
```

Perintah ini mencantumkan paling banyak 100 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi 7 hari dari tanggal/waktu saat ini.

### Contoh 19: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai
```
PS C:\>Get-AzureRmLog -ResourceProvider "Microsoft.Web" -StartTime 2017-05-22T04:30
```

Perintah ini mencantumkan paling banyak 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi pada atau setelah 05-05-22T04:30:00 waktu lokal 2017-05-2017 jika waktu mulai tidak lebih dari 90 hari dari tanggal/waktu saat ini.

### Contoh 20: Mendapatkan log kejadian menurut penyedia sumber daya dengan waktu mulai dan waktu berakhir
```
PS C:\>Get-AzureRmLog -ResourceProvider "Microsoft.Web" -StartTime 2017-04-15T04:30 -EndTime 2017-04-25T12:30
```

Perintah ini mencantumkan hampir 1000 kejadian yang terkait dengan penyedia sumber daya tertentu yang terjadi pada atau setelah 04-15-15T04:30 waktu lokal 2017-04-25T12:30 jika seluruh rentang tanggal/waktu tidak lebih dari 90 hari dari tanggal/waktu saat ini, yaitu: periode penyimpanan.

## PARAMETERS

### -Caller
Menentukan penelepon.

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
Menentukan ID korelasi.
Parameter ini diperlukan.

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

### -DetailOutput
Mengindikasikan bahwa cmdlet ini menampilkan output mendetail.
Secara default, output diringkas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Switch not present = False, i.e. output summarized
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Menentukan waktu akhir kueri dalam waktu lokal.
Nilai default adalah waktu saat ini.
Nilai harus setelah *StartTime*.
Anda dapat menggunakan cmdlet Get-Date untuk mendapatkan **objek DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current date (time: 00:00:00 AM) + 1 day
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxRecord
Menentukan jumlah total rekaman yang akan diambil untuk filter yang ditentukan.
Nilai default adalah 1000 dan nilai maksimum yang diterima adalah 100000. Nilai negatif dan 0 diabaikan dan nilai default akan digunakan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

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
Menentukan ID sumber daya.

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
Menentukan filter menurut penyedia sumber daya.

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
Menentukan waktu mulai kueri dalam waktu lokal.
Nilai defaultnya adalah *WaktuAkhir* dikurangi tujuh hari.
Anda dapat menggunakan cmdlet Get-Date untuk mendapatkan **objek DateTime** .

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: EndTime - 7 days
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Menentukan status.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Nullable'1[[System.DateTime, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

### System.String

### System.Management.Automation.SwitchParameter

### System.Int32

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSEventData

## CATATAN

## RELATED LINKS
