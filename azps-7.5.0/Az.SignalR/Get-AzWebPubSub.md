---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSub.md
ms.openlocfilehash: ec3dc4a4e4d6230cac10d41f182c083bab4c3597
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146609014"
---
# Get-AzWebPubSub

## SYNOPSIS
Dapatkan sumber daya dan propertinya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.signalr/get-azwebpubsub) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzWebPubSub [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzWebPubSub -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzWebPubSub -InputObject <IWebPubSubIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzWebPubSub -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan sumber daya dan propertinya.

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya Web PubSub dalam langganan
```powershell
Get-AzWebPubSub -SubscriptionId ef72249e-9785-4799-a76b-7cdd80e1b1d0
```

```output
Name                Location      SkuName
----                --------      -------
demo1               eastus        Standard_S1
demo2               eastus        Free_F1
```



### Contoh 2: Mencantumkan semua sumber daya Web PubSub dalam grup sumber daya
```powershell
Get-AzWebPubSub -ResourceGroupName psdemo
```

```output
Name       Location SkuName
----       -------- -------
psdemo-wps eastus   Standard_S1
```



### Contoh 3: Mendapatkan sumber daya Web PubSub tertentu
```powershell
Get-AzWebPubSub -ResourceGroupName psdemo -Name psdemo-wps
```

```output
Name       Location SkuName
----       -------- -------
psdemo-wps eastus   Standard_S1
```



### Contoh 4: Mendapatkan sumber daya Web PubSub tertentu melalui objek identitas
```powershell
$identity = @{ ResourceGroupName = 'psdemo'
ResourceName = 'psdemo-wps'
SubscriptionId = $(Get-AzContext).Subscription.Id }

$identity | Get-AzWebPubSub
```

```output
Name       Location SkuName
----       -------- -------
psdemo-wps eastus   Standard_S1
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

```yaml
Type: System.String
Parameter Sets: Get, List1
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
Type: System.String[]
Parameter Sets: Get, List, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IWebPubSubIdentity>`: Parameter Identitas
  - `[HubName <String>]`: Nama hub.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: wilayah
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya. Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.
  - `[ResourceName <String>]`: Nama sumber daya.
  - `[SharedPrivateLinkResourceName <String>]`: Nama sumber daya tautan privat bersama
  - `[SubscriptionId <String>]`: Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

