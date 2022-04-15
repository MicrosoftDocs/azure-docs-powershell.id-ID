---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/export-azurermloganalyticthrottledrequests
schema: 2.0.0
ms.openlocfilehash: e98819ab7de961dacefea673ac43690ad260ac3b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141930289"
---
# Export-AzureRmLogAnalyticThrottledRequests

## SYNOPSIS
Ekspor log yang memperlihatkan total permintaan Api yang dibatasi untuk langganan ini di jendela waktu tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Export-AzureRmLogAnalyticThrottledRequests [-Location] <String> [-FromTime] <DateTime> [-ToTime] <DateTime>
 [-BlobContainerSasUri] <String>
 [-GroupByOperationName]  [-GroupByThrottlePolicy] [-GroupByResourceName] 
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Tindakan ini akan mengekspor jumlah total panggilan API Microsoft.Compute yang dibatasi.
Log dapat diagregat lebih lanjut dengan tiga opsi: GroupByOperationName, GroupByThrottlePolicy, atau GroupByResourceName.
Perhatikan bahwa cmdlet ini hanya mengumpulkan log CRP.

## EXAMPLES

### Contoh 1
```
PS C:\> Export-AzureRmLogAnalyticThrottledRequests -Location 'West Central US' -FromTime '2018-02-20T17:54:14.8806951-08:00' -ToTime '2018-02-22T17:54:17.5832413-08:00' -BlobContainerSasUri 'https://wkuotest1.blob.core.windows.net/mylogs?someSasUri' -GroupByOperationName
```

Perintah ini menyimpan total panggilan API Microsoft.Compute yang dibatasi antara 2018-02-20T17:54:14 dan 2018-02-22T17:54:17 dalam URI SAS yang diberikan, diagregasi menurut nama operasi.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobContainerSasUri
SAS Uri dari kontainer logging blob tempat LogAnalytics Api menulis log output.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromTime
Dari waktu kueri

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupByoperationName
Hasil kueri grup menurut Nama Operasi.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupByResourceName
Hasil kueri grup menurut Nama Sumber Daya.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupByThrottlePolicy
Hasil kueri grup menurut Kebijakan Throttle diterapkan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi di mana analitik log dikueri.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ToTime
Ke waktu kueri

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSLogAnalyticsOperationResult

## CATATAN

## RELATED LINKS

