---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 8EF86C66-498F-4183-9070-F178628483F1
online version: ''
schema: 2.0.0
ms.openlocfilehash: aef3aa8d5a13b2b5d14d30f1735976267e5eec70788796993b43542c57684d15
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419239"
---
# Get-AzureRemoteAppCollectionUsageSummary

## SYNOPSIS
Mengambil ringkasan penggunaan untuk kumpulan Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppCollectionUsageSummary [-CollectionName] <String> [[-UsageMonth] <String>]
 [[-UsageYear] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppCollectionUsageSummary** mengambil ringkasan penggunaan untuk kumpulan Azure RemoteApp.

## EXAMPLES

### Contoh 1: Mendapatkan ringkasan penggunaan
```
PS C:\> Get-AzureRemoteAppCollectionUsageSummary -CollectionName Contoso -UsageMonth 12 -UsageYear 2014
```

Perintah ini mendapatkan ringkasan penggunaan untuk bulan Desember pada tahun 2014, untuk koleksi bernama Contoso.

## PARAMETERS

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -UsageMonth
Menentukan angka dua digit untuk bulan yang akan mendapatkan ringkasan penggunaan.
Jika parameter ini tidak ditentukan, cmdlet ini menyediakan penggunaan untuk bulan saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageYear
Menentukan empat digit tahun yang akan digunakan untuk mendapatkan ringkasan penggunaan.
Jika parameter ini tidak ditentukan, cmdlet ini akan menyediakan ringkasan penggunaan untuk tahun ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[Get-AzureRemoteAppCollectionUsageDetails](./Get-AzureRemoteAppCollectionUsageDetails.md)


