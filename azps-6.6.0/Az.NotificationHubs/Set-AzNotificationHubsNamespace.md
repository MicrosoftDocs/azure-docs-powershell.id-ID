---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 1B2AA717-ECD6-4CC0-AB6D-A199AF21A4A5
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/set-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
ms.openlocfilehash: 7a8071b8d2df70fbd59357dbe41cbed02fa64c9a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142709505"
---
# Set-AzNotificationHubsNamespace

## SYNOPSIS
Mengatur nilai properti untuk ruang nama hub pemberitahuan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/set-aznotificationhubsnamespace) untuk informasi terbaru.

## SYNTAX

```
Set-AzNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-State] <NamespaceState>] [[-Critical] <Boolean>] [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNotificationHubsNamespace** mengatur nilai properti ruang nama hub pemberitahuan yang sudah ada.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda harus memiliki setidaknya satu ruang nama hub pemberitahuan.
Selain itu, semua hub pemberitahuan harus memiliki ruang nama yang ditetapkan.
Cmdlet ini terutama digunakan untuk mengaktifkan dan menonaktifkan ruang nama.
Ketika ruang nama dinonaktifkan, pengguna tidak dapat tersambung ke hub pemberitahuan apa pun di ruang nama, administrator juga tidak dapat menggunakan hub tersebut untuk mengirim pemberitahuan push.
Untuk mengaktifkan kembali ruang nama yang dinonaktifkan, gunakan cmdlet ini untuk mengatur properti **Status** ruang nama ke Aktif.
Anda juga bisa menggunakan cmdlet ini untuk menandai ruang nama sebagai penting.
Ini mencegah ruang nama dihapus.
Untuk menghapus ruang nama penting, Anda harus menghapus tag Penting terlebih dahulu.

## EXAMPLES

### Contoh 1: Menonaktifkan ruang nama
```
PS C:\>Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Disabled" -SkuTier "Standard"
```

Perintah ini menonaktifkan ruang nama tingkat standar bernama ContosoPartners yang terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Mengaktifkan ruang nama
```
PS C:\>Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Active" -SkuTier "Standard"
```

Perintah ini memungkinkan ruang nama tingkat standar bernama ContosoPartners yang terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

## PARAMETERS

### -Kritis
Menunjukkan apakah ruang nama adalah ruang nama yang penting.
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Paksa
Jangan meminta konfirmasi.

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
Menentukan nama tampilan pusat data yang menjadi host ruang nama.
Meskipun Anda dapat mengatur parameter ini ke lokasi Azure apa pun yang valid, untuk kinerja optimal, Anda harus menggunakan pusat data yang terletak di dekat sebagian besar pengguna.
Untuk mendapatkan daftar terbaru lokasi Azure, jalankan perintah berikut: `Get-AzLocation | Select-Object DisplayName`

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
Menentukan ruang nama yang diubah cmdlet ini.
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
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang hanya membantu manajemen inventaris dan administrasi Azure.

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
Tingkat Sku dari ruang nama

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
Menentukan status ruang nama saat ini.
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
Menentukan pasangan nilai nama yang dapat digunakan untuk mengkategorikan dan menata item Azure.
Fungsi tag mirip dengan kata kunci, dan beroperasi di seluruh penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:TI, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti tipe item, lokasi, atau grup sumber daya.
Tag individual terdiri dari dua bagian: *Nama* dan (opsional) *Nilai*.
Misalnya, di Departemen:TI, nama tag adalah Departemen dan nilai tagnya adalah TI.
Untuk menambahkan tag, gunakan sintaks tabel hash seperti ini, yang membuat tag CalendarYear:2016: -Tags @{Name="CalendarYear"; Value="2016"} Untuk menambahkan beberapa tag dalam perintah yang sama, pisahkan tag individual dengan menggunakan tanda koma: -Tag @{Name="CalendarYear"; Value="2016"}, @{Name="FiscalYear"; Value="2017"}

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceState

### System.Boolean

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)


