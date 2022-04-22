---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 3B3F1870-348D-4303-9520-FD81D4650F5F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 24e23894b312f4be8732c8d381b88596652e038c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043281"
---
# Get-AzureWebHostingPlan

## SYNOPSIS
Mendapatkan paket hosting web Azure dalam langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureWebHostingPlan [-WebSpaceName <String>] [-Name <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Get-AzureWebHostingPlan** mendapatkan paket hosting web Azure dalam langganan saat ini.

Secara default, **Get-AzureWebHostingPlan** mendapatkan semua paket hosting Azure dalam langganan saat ini dan mengembalikan objek yang menyediakan informasi dasar tentang rencana.
Saat Anda menggunakan parameter *WebSpace* dan *Name* , **Get-AzureWebHostingPlan** mengembalikan objek paket hosting tertentu.

Untuk menemukan langganan saat ini, gunakan parameter cmdlet **Get-AzureSubscription** *saat ini*.
Untuk mengubah langganan saat ini, gunakan cmdlet **Select-AzureSubscription** .

## EXAMPLES

### Contoh 1: Dapatkan semua paket hosting web dalam langganan
```
PS C:\> Get-AzureWebHostingPlan 

Name : Default1 
SKU : Basic 
WorkerSize : Small 
NumberOfWorkers : 1 
CurrentWorkerSize : Small 
CurrentNumberOfWorkers : 1 
Status : Ready 
WebSpace : eastuswebspace 
Name : Default0 
SKU : Free 
WorkerSize : Small 
NumberOfWorkers : 0 
CurrentWorkerSize : Small 
CurrentNumberOfWorkers : 0 
Status : Ready
```

Perintah ini mendapatkan semua paket hosting web Azure dalam langganan saat ini.

### Contoh 2: Dapatkan paket hosting web tertentu dalam langganan
```
PS C:\> Get-AzureWebHostingPlan -WebSpaceName "westeuropewebspace" -Name "Default0" 

Name : Default0 
SKU : Free 
WorkerSize : Small 
NumberOfWorkers : 0 
CurrentWorkerSize : Small 
CurrentNumberOfWorkers : 0 
Status : Ready 
WebSpace : westeuropewebspace
```

Perintah ini mendapatkan paket hosting web bernama Default0 di ruang web bernama westeuropewebspace dalam langganan saat ini.

## PARAMETERS

### -Nama
Menentukan nama paket dalam langganan.
Secara default, cmdlet ini mendapatkan semua paket dalam langganan saat ini.
Parameter ini tidak mendukung karakter wildcard.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebSpaceName
Menentukan nama ruang web dalam langganan.
Secara default, cmdlet ini mendapatkan semua situs web dalam ruang web tertentu.
Parameter ini tidak mendukung karakter wildcard.

```yaml
Type: String
Parameter Sets: (All)
Aliases: WebSpace

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Anda dapat meneruskan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Websites.Services.WebEntities.WebHostingPlan
Secara default, **Get-AzureWebHostingPlan** mengembalikan array objek **WebHostingPlan** .

## NOTES

## RELATED LINKS

