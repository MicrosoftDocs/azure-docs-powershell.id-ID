---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/new-azwebpubsubhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
ms.openlocfilehash: 6b106190c77a01c2a616c52a18973d8bd6b28c4f
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144668932"
---
# New-AzWebPubSubHub

## SYNOPSIS
Membuat atau memperbarui pengaturan hub.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.signalr/new-azwebpubsubhub) untuk informasi terbaru.

## SYNTAX

```
New-AzWebPubSubHub -Name <String> -ResourceGroupName <String> -ResourceName <String>
 [-SubscriptionId <String>] [-AnonymousConnectPolicy <String>] [-EventHandler <IEventHandler[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui pengaturan hub.

## EXAMPLES

### Contoh 1: Membuat pengaturan hub
```powershell
$eventHandler = @{UrlTemplate = 'http://example.com/api/{hub}/connect/{event}' ; AuthType = 'None' ; SystemEvent = 'connect' ; }

New-AzWebPubSubHub -Name testHub -ResourceGroupName psdemo -ResourceName psdemo-wps -EventHandler $eventHandler
```

```output
Name    AnonymousConnectPolicy
----    ----------------------
testHub deny
```

Contoh pertama-tama membuat daftar tabel hash yang berisi dua pengaturan penanganan aktivitas, satu untuk peristiwa sistem dan yang lainnya untuk peristiwa pengguna.
Kemudian membuat hub dengan penanganan aktivitas.

## PARAMETERS

### -AnonymousConnectPolicy
Pengaturan untuk mengonfigurasi apakah koneksi anonim diizinkan untuk hub ini: "izinkan" atau "tolak".
Default ke "tolak".

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

### -AsJob
Jalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -EventHandler
Penanganan aktivitas hub.
Untuk membuat, lihat bagian CATATAN untuk properti EVENTHANDLER dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IEventHandler[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama hub.

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

### -NoWait
Jalankan perintah secara asinkron

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: (All)
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

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubHub

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EVENTHANDLER <IEventHandler[]>: Penanganan aktivitas hub.
  - `UrlTemplate <String>`: Mendapatkan atau mengatur templat URL EventHandler. Anda dapat menggunakan parameter {hub} dan {event} yang telah ditentukan sebelumnya di dalam templat, nilai URL EventHandler dihitung secara dinamis saat permintaan klien masuk.         Misalnya, UrlTemplate dapat berupa `http://example.com/api/{hub}/{event}`. Bagian host tidak dapat berisi parameter.
  - `[AuthType <UpstreamAuthType?>]`: Mendapatkan atau mengatur jenis autentikasi. Tidak ada atau ManagedIdentity didukung sekarang.
  - `[ManagedIdentityResource <String>]`: Sumber Daya yang menunjukkan URI ID Aplikasi dari sumber daya target.         Ini juga muncul dalam klaim aud (audiens) dari token yang dikeluarkan.
  - `[SystemEvent <String[]>]`: Mendapatkan ot menetapkan daftar peristiwa sistem. Nilai yang valid berisi: 'connect', 'connected', 'disconnected'.
  - `[UserEventPattern <String>]`: Mendapatkan atau mengatur pola pencocokan untuk nama peristiwa.         Ada 3 jenis pola yang didukung: 1. "*", cocok dengan nama kejadian 2. Gabungkan beberapa peristiwa dengan ",", misalnya "event1,event2", cocok dengan peristiwa "event1" dan "event2" 3. Nama peristiwa tunggal, misalnya, "event1", cocok dengan "event1"

## RELATED LINKS

