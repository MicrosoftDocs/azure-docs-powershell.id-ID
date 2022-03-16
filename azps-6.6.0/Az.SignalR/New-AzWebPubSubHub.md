---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/new-azwebpubsubhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
ms.openlocfilehash: 076a98be5b998d54815a063ab221ce82168a66d5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140303917"
---
# New-AzWebPubSubHub

## SYNOPSIS
Buat atau perbarui pengaturan hub.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.signalr/new-azwebpubsubhub) untuk informasi terkini.

## SYNTAX

```
New-AzWebPubSubHub -Name <String> -ResourceGroupName <String> -ResourceName <String>
 [-SubscriptionId <String>] [-AnonymousConnectPolicy <String>] [-EventHandler <IEventHandler[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat atau perbarui pengaturan hub.

## EXAMPLES

### Contoh 1: Buat pengaturan hub
```powershell
PS C:\> $eventHandler = @{UrlTemplate = 'http://example.com/api/{hub}/connect/{event}' ; AuthType = 'None' ; SystemEvent = 'connect' ; } ,
@{ UrlTemplate = 'http://example.com/api/{hub}/userevent/{event}' ; AuthType = 'None' ; UserEventPattern = '*' }

PS C:\> New-AzWebPubSubHub -Name testHub -ResourceGroupName psdemo -ResourceName psdemo-wps -EventHandler $eventHandler

Name    AnonymousConnectPolicy
----    ----------------------
testHub deny
```

Contoh pertama membuat daftar tabel hash yang berisi dua pengaturan penanganan kejadian, satu untuk kejadian sistem dan yang lain untuk kejadian pengguna.
Kemudian, aplikasi akan membuat hub dengan penanganan acara.

## PARAMETERS

### -AnonymousConnectPolicy
Pengaturan untuk mengonfigurasi jika koneksi anonim diperbolehkan untuk hub ini: "izinkan" atau "tolak".
Default untuk "menolak".

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
Menjalankan perintah sebagai pekerjaan

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
Penanganan kejadian hub.
Untuk membuat, lihat bagian CATATAN untuk properti EVENTHANDLER dan membuat tabel hash.

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

### -Nama
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
Menjalankan perintah secara asinkron

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
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Mendapatkan Id langganan yang secara unik mengidentifikasi Microsoft Azure anda.
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

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubHub

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EVENTHANDLER <IEventHandler[]>: Penanganan kejadian sebuah hub.
  - `UrlTemplate <String>`: Mendapatkan atau mengatur templat URL EventHandler. Anda bisa menggunakan parameter {hub} dan {event} yang sudah ditentukan sebelumnya di dalam templat, nilai URL EventHandler dihitung secara dinamis saat permintaan klien masuk.         Misalnya, UrlTemplate dapat adalah `http://example.com/api/{hub}/{event}`. Bagian host tidak bisa berisi parameter.
  - `[AuthType <UpstreamAuthType?>]`: Mendapatkan atau mengatur tipe auth. Tidak ada atau Identitas Terkelola kini didukung.
  - `[ManagedIdentityResource <String>]`: Sumber daya yang menunjukkan URI ID Aplikasi dari sumber daya target.         Itu juga muncul dalam klaim aud (audiens) untuk token yang dikeluarkan.
  - `[SystemEvent <String[]>]`: Mendapatkan ot mengatur daftar kejadian sistem. Nilai yang valid berisi: 'sambungkan', 'tersambung', 'terputus'.
  - `[UserEventPattern <String>]`: Mendapatkan atau mengatur pola yang cocok untuk nama acara.         Ada 3 jenis pola yang didukung: 1. "*", agar sesuai dengan nama acara 2. Gabungkan beberapa acara dengan ",", misalnya "acara1,acara2", yang cocok dengan acara "acara1" dan "acara2" 3. Nama acara tunggal, misalnya, "acara1", cocok dengan "acara1"

## RELATED LINKS

