---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/get-azwebpubsubkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/Get-AzWebPubSubKey.md
ms.openlocfilehash: 7ad82f8438ed034cf11a834a4ea0fbadb797d918
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144242364"
---
# Get-AzWebPubSubKey

## SYNOPSIS
Dapatkan kunci akses sumber daya.

## SYNTAX

### Daftar (Default)
```
Get-AzWebPubSubKey -ResourceGroupName <String> -ResourceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ListViaIdentity
```
Get-AzWebPubSubKey -InputObject <IWebPubSubIdentity> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan kunci akses sumber daya.

## EXAMPLES

### Contoh 1: Mendapatkan kunci akses sumber daya Web PubSub
```powershell
Get-AzWebPubSubKey -ResourceGroupName psdemo -ResourceName psdemo-wps  | Format-List
```

```output
PrimaryConnectionString   : Endpoint=https://psdemo-wps.webpubsub.azure.com;AccessKey=********;Version=1.0;
PrimaryKey                : ********
SecondaryConnectionString : Endpoint=https://psdemo-wps.webpubsub.azure.com;AccessKey=********;Version=1.0;
SecondaryKey              : ********
```

Contohnya mendapatkan kunci akses sumber daya Web PubSub lalu menyalurkan hasilnya untuk `Format-List` melihat semua nilai properti hasilnya.

### Contoh 2: Mendapatkan kunci akses sumber daya Web PubSub melalui identitas
```powershell
$wps = Get-AzWebPubSub -ResourceGroupName psdemo -ResourceName psdemo-wps
$wps | Get-AzWebPubSubKey | Format-List
```

```output
PrimaryConnectionString   : Endpoint=https://psdemo-wps.webpubsub.azure.com;AccessKey=********;Version=1.0;
PrimaryKey                : ********
SecondaryConnectionString : Endpoint=https://psdemo-wps.webpubsub.azure.com;AccessKey=********;Version=1.0;
SecondaryKey              : ********
```

Contohnya mendapatkan kunci akses sumber daya Web PubSub lalu menyalurkan hasilnya untuk `Format-List` melihat semua nilai properti hasilnya.

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
Parameter Sets: ListViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceName
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: List
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
Parameter Sets: List
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

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.IWebPubSubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubKeys

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebPubSubIdentity>: Parameter Identitas
  - `[HubName <String>]`: Nama hub.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: wilayah
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat
  - `[ResourceGroupName <String>]`: Nama grup sumber daya yang berisi sumber daya. Anda dapat memperoleh nilai ini dari Azure Resource Manager API atau portal.
  - `[ResourceName <String>]`: Nama sumber daya.
  - `[SharedPrivateLinkResourceName <String>]`: Nama sumber daya tautan privat bersama
  - `[SubscriptionId <String>]`: Mendapatkan Id langganan yang secara unik mengidentifikasi langganan Microsoft Azure. ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

## RELATED LINKS

