---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/get-azmapsaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Get-AzMapsAccountKey.md
ms.openlocfilehash: 045821011e7047adc77e2cf555dd437e2b8dca62
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138274011"
---
# Get-AzMapsAccountKey

## SYNOPSIS
Dapatkan kunci untuk digunakan dengan Peta API.
Kunci digunakan untuk mengautentikasi dan mengotorisasi akses ke Peta REST API.
Hanya satu kunci yang diperlukan dalam satu waktu; dua di antaranya diberikan untuk menyediakan regenerasi kunci yang mulus.

## SYNTAX

```
Get-AzMapsAccountKey -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan kunci untuk digunakan dengan Peta API.
Kunci digunakan untuk mengautentikasi dan mengotorisasi akses ke Peta REST API.
Hanya satu kunci yang diperlukan dalam satu waktu; dua di antaranya diberikan untuk menyediakan regenerasi kunci yang mulus.

## EXAMPLES

### Contoh 1: Get the keys to use with the Peta API
```powershell
PS C:\> Get-AzMapsAccountKey -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount02

PrimaryKey                                  PrimaryKeyLastUpdated        SecondaryKey                                SecondaryKeyLastUpdated
----------                                  ---------------------        ------------                                -----------------------
AZPcJC8OCNCpqRsnj1NB3Ngl-qQncBP5IT21jts_2b0 2021-05-20T05:59:16.2028276Z 3l_cups4uVp7LB90G861PB_ddEFJFOdt0beX1U8ROO4 2021-05-20T05:59:16.2028276Z
```

Perintah ini agar tombol dapat digunakan dengan Peta API.
Kunci digunakan untuk mengautentikasi dan mengotorisasi akses ke Peta REST API.
Hanya satu kunci yang diperlukan dalam satu waktu; dua di antaranya diberikan untuk menyediakan regenerasi kunci yang mulus.

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

### -Nama
Nama akun Peta Anda.

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.IMapsAccountKeys

## CATATAN

ALIAS

## RELATED LINKS

