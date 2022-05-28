---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 1B2AA717-ECD6-4CC0-AB6D-A199AF21A4A5
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/set-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubsNamespace.md
ms.openlocfilehash: b041fd7a570f02399a6b236449de785a60480748
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145559046"
---
# Set-AzNotificationHubsNamespace

## SYNOPSIS
Mengatur nilai properti untuk namespace hub pemberitahuan.

## SYNTAX

```
Set-AzNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-State] <NamespaceState>] [[-Critical] <Boolean>] [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNotificationHubsNamespace** mengatur nilai properti dari namespace hub pemberitahuan yang ada.
Namespace adalah kontainer logis yang membantu Anda mengatur dan mengelola hub pemberitahuan Anda.
Anda harus memiliki setidaknya satu namespace hub pemberitahuan.
Selain itu, semua hub pemberitahuan harus memiliki namespace yang ditetapkan.
Cmdlet ini terutama digunakan untuk mengaktifkan dan menonaktifkan namespace.
Saat namespace dinonaktifkan, pengguna tidak dapat tersambung ke salah satu hub pemberitahuan di namespace layanan, administrator juga tidak dapat menggunakan hub tersebut untuk mengirim pemberitahuan push.
Untuk mengaktifkan kembali namespace yang dinonaktifkan, gunakan cmdlet ini untuk mengatur properti **Status** namespace layanan ke Aktif.
Anda juga dapat menggunakan cmdlet ini untuk menandai namespace sebagai penting.
Ini mencegah namespace dihapus.
Untuk menghapus namespace penting, Anda harus terlebih dahulu menghapus tag Kritis.

## EXAMPLES

### Contoh 1: Menonaktifkan namespace
```powershell
Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Disabled" -SkuTier "Standard"
```

Perintah ini menonaktifkan namespace tingkat Standar bernama ContosoPartners yang terletak di pusat data US Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Mengaktifkan namespace
```powershell
Set-AzNotificationHubsNamespace -Namespace "ContosoPartners" -Location "West US" -ResourceGroup "ContosoNotificationsGroup" -State "Active" -SkuTier "Standard"
```

Perintah ini memungkinkan namespace layanan tingkat Standar bernama ContosoPartners yang terletak di pusat data US Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

## PARAMETERS

### -Kritis
Menunjukkan apakah namespace adalah namespace penting.
Namespace penting tidak dapat dihapus.
Untuk menghapus namespace penting, Anda harus mengatur nilai properti ini ke False untuk menandai namespace sebagai non-kritis.

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

### -Force
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
Menentukan nama tampilan pusat data yang menghosting namespace.
Meskipun Anda dapat mengatur parameter ini ke lokasi Azure yang valid, untuk performa optimal, Anda harus menggunakan pusat data yang terletak di dekat sebagian besar pengguna Anda.
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
Menentukan namespace layanan yang dimodifikasi cmdlet ini.
Namespace menyediakan cara untuk mengelompokkan dan mengategorikan hub pemberitahuan.

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
Menentukan grup sumber daya tempat namespace layanan ditetapkan.
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventarisasi dan administrasi Azure.

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
Tingkat Sku namespace layanan

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

### -State
Menentukan status namespace saat ini.
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
Menentukan pasangan nama-nilai yang dapat digunakan untuk mengategorikan dan menata item Azure.
Tag berfungsi mirip dengan kata kunci, dan beroperasi di seluruh penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:IT, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti jenis item, lokasi, atau grup sumber daya.
Tag individual terdiri dari dua bagian: *Nama* dan (opsional) *Nilai*.
Misalnya, di Departemen:IT, nama tag adalah Departemen dan nilai tagnya adalah IT.
Untuk menambahkan tag, gunakan sintaks tabel hash yang mirip dengan ini, yang membuat tag CalendarYear:2016: -Tags @{Name="CalendarYear"; Value="2016"} Untuk menambahkan beberapa tag dalam perintah yang sama, pisahkan tag individual dengan menggunakan koma: -Tag @{Name="CalendarYear"; Value="2016"}, @{Name="FiscalYear"; Value="2017"}

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)


