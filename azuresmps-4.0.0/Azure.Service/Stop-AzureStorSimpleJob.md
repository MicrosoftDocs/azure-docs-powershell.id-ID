---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: A1E143A8-70F2-4158-9A10-F2082AD62A73
online version: ''
schema: 2.0.0
ms.openlocfilehash: 42536092e072783230acb4d43b6f0ff2396a550f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427418"
---
# Stop-AzureStorSimpleJob

## SYNOPSIS
Menghentikan pekerjaan StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Stop-AzureStorSimpleJob -InstanceId <String> [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureStorSimpleJob** menghentikan pekerjaan StorSimple yang sedang berlangsung.
Anda dapat menentukan pekerjaan dengan menyediakan ID instans atau nama pekerjaan.

## EXAMPLES

### Contoh 1: Hentikan pekerjaan untuk perangkat
```
PS C:\>Get-AzureStorSimpleJob -DeviceName "Device07" | Stop-AzureStorSimpleJob -Force
```

Perintah ini mendapatkan pekerjaan untuk perangkat bernama Device07, dengan menggunakan cmdlet **Get-AzureStorSimpleJob.**
Perintah itu menyampaikan pekerjaan ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menghentikan pekerjaan yang dilakukan perintah.
Perintah menentukan parameter *Paksa,* dan, oleh karena itu, perintah tidak akan meminta konfirmasi Anda sebelum perintah itu menghentikan pekerjaan.

### Contoh 2: Menghentikan pekerjaan tertentu
```
PS C:\>Stop-AzureStorSimpleJob -InstanceId "574f47e0-44e9-495c-b8a5-0203c57ebf6d" -Force
```

Perintah ini menghentikan pekerjaan yang memiliki ID instans tertentu.

## PARAMETERS

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -InstanceId
Menentukan ID pekerjaan perangkat untuk dihentikan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### DeviceJobDetails
Cmdlet ini mendapatkan detail **DeviceJob bahwa** cmdlet ini berhenti.

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


