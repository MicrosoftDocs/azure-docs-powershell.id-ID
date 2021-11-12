---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: 3BA94976-DE88-4F07-9C06-41FEEDE1B829
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/new-azurermnotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/New-AzureRmNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/New-AzureRmNotificationHubsNamespace.md
ms.openlocfilehash: d4bba9d54dac21a8eb19a4b161bb2fdef29d4bb7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425118"
---
# New-AzureRmNotificationHubsNamespace

## SYNOPSIS
Membuat ruang nama hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmNotificationHubsNamespace** membuat ruang nama hub pemberitahuan.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda setidaknya harus memiliki satu ruang nama hub pemberitahuan.
Ruang nama tunggal bisa menjadi rumah beberapa hub.
Anda bisa memiliki beberapa ruang nama untuk menata hub Anda, atau memberikan izin kepada individu tertentu untuk mengelola subkumpulan yang dipilih dari hub Anda.
Untuk membuat ruang nama, pastikan bahwa Anda menentukan nama yang unik untuk ruang nama; tentukan datacenter di mana ruang nama akan berada; dan, tentukan grup sumber daya yang akan diberi ruang nama.
Setelah ruang nama dibuat, Anda bisa menggunakan cmdlet New-AzureRmNotificationHubsNamespaceAuthorizationRules untuk menetapkan aturan otorisasi ke kumpulan nama itu.
Aturan otorisasi digunakan untuk mengelola izin ke ruang nama.

## EXAMPLES

### Contoh 1: Buat hub pemberitahuan
```
PS C:\>New-AzureRmNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners"
```

Perintah ini akan membuat hub pemberitahuan bernama ContosoPartners.
Ruang nama akan terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya Grup ContosoNotifications.

### Contoh 2: Buat hub pemberitahuan dengan tag
```
PS C:\>New-AzureRmNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners" -Tags @{Name="Audience";Value="PartnerOrganizations"}
```

Perintah ini akan membuat hub pemberitahuan bernama ContosoPartners.
Ruang nama akan terletak di pusat data AS Barat dan ditetapkan ke grup sumber daya Grup ContosoNotifications.
Selain itu, perintah ini membuat tag dengan nama Audiens dan nilai Organisasi Mitra dan ditetapkan ke ruang nama.
Ini memastikan bahwa ruang nama akan ditampilkan setiap kali Anda memfilter item di mana tag Audiens diatur ke Organisasi Mitra.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan nama tampilan datacenter yang akan menjadi host Ruang Nama.
Meskipun Anda bisa mengatur parameter ini ke lokasi valid apa pun, untuk kinerja optimal, Anda mungkin ingin menggunakan pusat data yang terletak di dekat mayoritas pengguna Anda.

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
Menentukan nama ruang nama baru.
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
Menentukan grup sumber daya tempat ruang nama akan ditetapkan.
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu manajemen inventaris dan administrasi.

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

### -Tag
Menentukan pasangan nilai nama yang dapat digunakan untuk mengategorikan dan menata item Azure.
Fungsi tag yang sama dengan kata kunci, dan beroperasi pada penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:IT, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti tipe item, lokasi, atau grup sumber daya.
Tag individu terdiri dari dua bagian: *Nama* dan, secara opsional, *Nilai.*
Misalnya, di Department:IT, nama tag adalah Departemen dan nilai tag adalah IT.
Untuk menambahkan tag, gunakan sintaks tabel hash seperti ini, yang akan membuat tag CalendarYear:2016:

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## CATATAN

## RELATED LINKS

[Get-AzureRmNotificationHubsNamespace](./Get-AzureRmNotificationHubsNamespace.md)

[Remove-AzureRmNotificationHubsNamespace](./Remove-AzureRmNotificationHubsNamespace.md)

[Set-AzureRmNotificationHubsNamespace](./Set-AzureRmNotificationHubsNamespace.md)


