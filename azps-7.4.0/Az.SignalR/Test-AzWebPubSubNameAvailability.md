---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/test-azwebpubsubnameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Test-AzWebPubSubNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Test-AzWebPubSubNameAvailability.md
ms.openlocfilehash: 758b51f2194e9ad7b9d0dee39be44bf760a6c5bc
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144610304"
---
# Test-AzWebPubSubNameAvailability

## SYNOPSIS
Memeriksa apakah nama sumber daya valid dan belum digunakan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.signalr/test-azwebpubsubnameavailability) untuk informasi terbaru.

## SYNTAX

```
Test-AzWebPubSubNameAvailability -Location <String> -Name <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memeriksa apakah nama sumber daya valid dan belum digunakan.

## EXAMPLES

### Contoh 1: Periksa apakah nama sumber daya "abc" tersedia di wilayah US timur.
```powershell
Test-AzWebPubSubNameAvailability -Location eastus -Name abc
```

```output
NameAvailable Reason Message
------------- ------ -------
True
```



## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
wilayah

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya untuk divalidasi.
misalnya,my-resource-name"

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.INameAvailability

## NOTES

ALIAS

## RELATED LINKS

