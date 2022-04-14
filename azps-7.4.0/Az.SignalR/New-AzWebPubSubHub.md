---
external help file: ''
Module Name: Az.SignalR
online version: https://docs.microsoft.com/powershell/module/az.signalr/new-azwebpubsubhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SignalR/SignalR/help/New-AzWebPubSubHub.md
ms.openlocfilehash: c3caa2bf3396865109c5b958d232eee0540d48bc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142171886"
---
# New-AzWebPubSubHub

## SYNOPSIS
Membuat atau memperbarui pengaturan hub.

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

Contoh pertama membuat daftar tabel hash yang berisi dua pengaturan pengatur kejadian, satu untuk kejadian sistem dan yang lainnya untuk acara pengguna.
Lalu membuat hub dengan pengatur acara.

## PARAMETERS

### -AnonymousConnectPolicy
Pengaturan untuk mengonfigurasi jika koneksi anonim diperbolehkan untuk hub ini: "izinkan" atau "tolak".
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
Untuk membangun, lihat bagian CATATAN untuk properti EVENTHANDLER dan membuat tabel hash.

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
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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
Mendapatkan Id langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.WebPubSub.Models.Api20211001.IWebPubSubHub

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EVENTHANDLER <IEventHandler[]>: Pengatur acara hub.
  - `UrlTemplate <String>`: Mendapatkan atau mengatur templat URL EventHandler. Anda dapat menggunakan parameter yang sudah ditentukan sebelumnya {hub} dan {event} di dalam templat, nilai URL EventHandler dihitung secara dinamis saat permintaan klien masuk.         Misalnya, UrlTemplate dapat berupa `http://example.com/api/{hub}/{event}`. Bagian host tidak dapat berisi parameter.
  - `[AuthType <UpstreamAuthType?>]`: Mendapatkan atau mengatur tipe auth. Tidak ada atau ManagedIdentity yang didukung sekarang.
  - `[ManagedIdentityResource <String>]`: Sumber Daya yang menunjukkan URI ID Aplikasi dari sumber daya target.         Hal ini juga muncul dalam klaim aud (audiens) dari token yang dikeluarkan.
  - `[SystemEvent <String[]>]`: Mendapatkan rangkaian ot daftar kejadian sistem. Nilai yang valid berisi: 'hubungkan', 'tersambung', 'terputus'.
  - `[UserEventPattern <String>]`: Mendapatkan atau mengatur pola yang cocok untuk nama acara.         Ada 3 jenis pola yang didukung: 1. "*", sesuai dengan nama acara 2. Gabungkan beberapa acara dengan ",", misalnya "event1,event2", acara cocok dengan acara "event1" dan "event2" 3. Nama acara tunggal, misalnya, "event1", cocok dengan "event1"

## RELATED LINKS

