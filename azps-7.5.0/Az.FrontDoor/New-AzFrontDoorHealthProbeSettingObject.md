---
external help file: Microsoft.Azure.PowerShell.Cmdlets.FrontDoor.dll-Help.xml
Module Name: Az.FrontDoor
online version: https://docs.microsoft.com/powershell/module/az.frontdoor/new-azfrontdoorhealthprobesettingobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/New-AzFrontDoorHealthProbeSettingObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/FrontDoor/FrontDoor/help/New-AzFrontDoorHealthProbeSettingObject.md
ms.openlocfilehash: 43b7277882929126d93388597a075355c1fbba63
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145788202"
---
# New-AzFrontDoorHealthProbeSettingObject

## SYNOPSIS
Membuat objek PSHealthProbeSetting untuk pembuatan Front Door

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.frontdoor/new-azfrontdoorhealthprobesettingobject) untuk informasi terbaru.

## SYNTAX

```
New-AzFrontDoorHealthProbeSettingObject -Name <String> [-Path <String>] [-Protocol <PSProtocol>]
 [-IntervalInSeconds <Int32>] [-HealthProbeMethod <String>] [-EnabledState <PSEnabledState>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek PSHealthProbeSetting untuk pembuatan Front Door

## EXAMPLES

### Contoh 1
```powershell
New-AzFrontDoorHealthProbeSettingObject -Name "healthProbeSetting1"
```

```output
Path              : /
Protocol          : Http
IntervalInSeconds : 30
ResourceState     :
HealthProbeMethod : Head
EnabledState      : Enabled
Id                :
Name              : healthProbeSetting1
Type              :
```

Catatan: Pengaturan HealthProbeMethod tidak peka huruf besar/kecil.

Membuat objek PSHealthProbeSetting untuk pembuatan Front Door

## PARAMETERS

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

### -EnabledState
Apakah akan mengaktifkan pemeriksaan kesehatan yang akan dilakukan terhadap backend yang ditentukan di bawah backendPools. Pemeriksaan kesehatan hanya dapat dinonaktifkan jika ada satu backend yang diaktifkan dalam satu kumpulan backend yang diaktifkan.

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSEnabledState
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthProbeMethod
Mengonfigurasi metode HTTP mana yang akan digunakan untuk memeriksa backend yang ditentukan di bawah backendPools.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntervalInSeconds
Jumlah detik antara pemeriksaan kesehatan.
Nilai defaultnya adalah 30

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama pengaturan pemeriksaan kesehatan.

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

### -Jalur
Jalur yang digunakan untuk pemeriksaan kesehatan.
Defaultnya adalah /

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Skema protokol yang akan digunakan untuk nilai Default pemeriksaan ini adalah HTTP

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Http, Https

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.FrontDoor.Models.PSHealthProbeSetting
## NOTES

## RELATED LINKS

[New-AzFrontDoor](./New-AzFrontDoor.md)
 [Set-AzFrontDoor](./Set-AzFrontDoor.md)
