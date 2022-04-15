---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 3BA94976-DE88-4F07-9C06-41FEEDE1B829
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/new-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespace.md
ms.openlocfilehash: df1722228fe1a73d2f8324529f3f7ebf2c1736ad
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142430934"
---
# New-AzNotificationHubsNamespace

## SYNOPSIS
Membuat ruang nama hub pemberitahuan.

## SYNTAX

```
New-AzNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNotificationHubsNamespace** membuat ruang nama hub pemberitahuan.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda harus memiliki setidaknya satu ruang nama hub pemberitahuan.
Ruang nama tunggal dapat menampung beberapa hub.
Anda bisa memiliki beberapa ruang nama untuk menata hub Anda, atau untuk memberikan izin individu tertentu untuk mengelola subset hub yang dipilih.
Untuk membuat ruang nama, pastikan Anda menentukan nama unik untuk ruang nama; tentukan pusat data tempat ruang nama akan berada; dan, tentukan grup sumber daya tempat ruang nama akan ditetapkan.
Setelah ruang nama dibuat, Anda dapat menggunakan cmdlet New-AzNotificationHubsNamespaceAuthorizationRules untuk menetapkan aturan otorisasi ke ruang nama tersebut.
Aturan otorisasi digunakan untuk mengelola izin ke ruang nama.

## EXAMPLES

### Contoh 1: Membuat hub pemberitahuan
```powershell
New-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners"
```

Perintah ini membuat hub pemberitahuan bernama ContosoPartners.
Ruang nama akan berada di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Membuat hub pemberitahuan dengan tag
```powershell
New-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners" -Tags @{Name="Audience";Value="PartnerOrganizations"}
```

Perintah ini membuat hub pemberitahuan bernama ContosoPartners.
Ruang nama akan berada di pusat data AS Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.
Selain itu, perintah ini membuat tag dengan nama Audiens dan nilai PartnerOrganizations dan ditetapkan ke ruang nama.
Ini memastikan bahwa ruang nama akan ditampilkan setiap kali Anda memfilter item di mana tag Audiens diatur ke PartnerOrganizations.

## PARAMETERS

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

### -Lokasi
Menentukan nama tampilan pusat data yang akan menghosting Ruang Nama.
Meskipun Anda bisa mengatur parameter ini ke lokasi yang valid, untuk kinerja optimal Anda mungkin ingin menggunakan pusat data yang terletak di dekat sebagian besar pengguna Anda.

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
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventaris dan administrasi.

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

### -Tag
Menentukan pasangan nilai nama yang dapat digunakan untuk mengkategorikan dan menata item Azure.
Fungsi tag mirip dengan kata kunci, dan beroperasi di seluruh penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:TI, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti tipe item, lokasi, atau grup sumber daya.
Tag individual terdiri dari dua bagian: *Nama* dan, secara opsional, *Nilai*.
Misalnya, dalam Departemen:TI, nama tag adalah Departemen dan nilai tagnya adalah TI.
Untuk menambahkan tag, gunakan sintaks tabel hash yang mirip dengan ini, yang membuat tag CalendarYear:2016:

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## CATATAN

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)

[Set-AzNotificationHubsNamespace](./Set-AzNotificationHubsNamespace.md)


