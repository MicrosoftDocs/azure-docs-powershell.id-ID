---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 1B2AA717-ECD6-4CC0-AB6D-A199AF21A4A5
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/set-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
ms.openlocfilehash: e00511375128bfdaca6c86d97921cb320b49b45c
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138305643"
---
# Set-AzNotificationHubsNamespace

## SYNOPSIS
Mengatur nilai properti untuk ruang nama hub pemberitahuan.

## SYNTAX

```
Set-AzNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-State] <NamespaceState>] [[-Critical] <Boolean>] [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNotificationHubsNamespace** mengatur nilai properti dari ruang nama hub pemberitahuan yang sudah ada.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda setidaknya harus memiliki satu ruang nama hub pemberitahuan.
Selain itu, semua hub pemberitahuan harus memiliki ruang nama yang ditetapkan.
Cmdlet ini terutama digunakan untuk mengaktifkan dan menonaktifkan ruang nama.
Saat ruang nama dinonaktifkan, pengguna tidak bisa tersambung ke salah satu hub pemberitahuan dalam ruang nama, juga tidak bisa administrator menggunakan hub tersebut untuk mengirim pemberitahuan push.
Untuk mengaktifkan kembali ruang nama yang dinonaktifkan, gunakan cmdlet ini untuk mengatur **properti Status** kumpulan nama ke Aktif.
Anda juga bisa menggunakan cmdlet ini untuk menandai ruang nama sebagai sangat penting.
Ini mencegah ruang nama dihapus.
Untuk menghapus ruang nama penting, Anda harus terlebih dahulu menghapus tag Sangat Penting.

## EXAMPLES

### Contoh 1: Menonaktifkan ruang nama
```
PS C:\>Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Disabled" -SkuTier "Standard"
```

Perintah ini menonaktifkan ruang nama tingkatan Standar bernama ContosoPartners yang terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Mengaktifkan ruang nama
```
PS C:\>Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Active" -SkuTier "Standard"
```

Perintah ini mengaktifkan ruang nama tingkatan Standar bernama ContosoPartners yang terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

## PARAMETERS

### -Kritis
Menunjukkan apakah ruang nama merupakan ruang nama penting.
Ruang nama penting tidak bisa dihapus.
Untuk menghapus ruang nama penting, Anda harus mengatur nilai properti ini ke False untuk menandai ruang nama sebagai non-kritis.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Force
Jangan minta konfirmasi.

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

### -Lokasi
Menentukan nama tampilan datacenter yang menjadi host ruang nama.
Meskipun parameter ini dapat ditetapkan ke lokasi Azure yang valid, Anda harus menggunakan datacenter yang terletak di dekat mayoritas pengguna.
Untuk mendapatkan daftar lokasi Azure terkini, jalankan perintah berikut: `Get-AzLocation | Select-Object DisplayName`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Menentukan ruang nama yang dimodifikasi cmdlet ini.
Ruang nama menyediakan cara untuk mengelompokkan dan mengkategorikan hub pemberitahuan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Menentukan grup sumber daya tempat ruang nama ditetapkan.
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu manajemen inventaris dan administrasi Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuTier
Sku tier dari ruang nama

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan status saat ini dari ruang nama.
Nilai yang dapat diterima untuk parameter ini adalah: Aktif dan Dinonaktifkan.

```yaml
Type: Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceState
Parameter Sets: (All)
Aliases:
Accepted values: Unknown, Active, Disabled

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Menentukan pasangan nilai nama yang dapat digunakan untuk mengategorikan dan menata item Azure.
Fungsi tag yang sama dengan kata kunci, dan beroperasi pada penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:IT, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti tipe item, lokasi, atau grup sumber daya.
Tag individu terdiri dari dua bagian: *Nama* dan (opsional) *Nilai*.
Misalnya, di Departemen:IT, nama tag adalah Departemen dan nilai tag adalah IT.
Untuk menambahkan tag, gunakan sintaks tabel hash seperti ini, yang membuat tag CalendarYear:2016: -Tag @{Name="CalendarYear"; Value="2016"} Untuk menambahkan beberapa tag dalam perintah yang sama, pisahkan tag individu tersebut menggunakan koma: -Tag @{Name="CalendarYear"; Value="2016"}, @{Name="FiscalYear"; Value="2017"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceState

### System.Boolean

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## CATATAN

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)


