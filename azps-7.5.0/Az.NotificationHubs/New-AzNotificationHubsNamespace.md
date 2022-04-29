---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 3BA94976-DE88-4F07-9C06-41FEEDE1B829
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/new-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespace.md
ms.openlocfilehash: df1722228fe1a73d2f8324529f3f7ebf2c1736ad
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144226922"
---
# New-AzNotificationHubsNamespace

## SYNOPSIS
Membuat namespace hub pemberitahuan.

## SYNTAX

```
New-AzNotificationHubsNamespace [-ResourceGroup] <String> [-Namespace] <String> [-Location] <String>
 [[-Tag] <Hashtable>] [[-SkuTier] <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNotificationHubsNamespace** membuat namespace hub pemberitahuan.
Namespace adalah kontainer logis yang membantu Anda mengatur dan mengelola hub pemberitahuan Anda.
Anda harus memiliki setidaknya satu namespace hub pemberitahuan.
Satu namespace dapat menampung beberapa hub.
Anda dapat memiliki beberapa namespace untuk mengatur hub Anda, atau untuk memberikan izin kepada individu tertentu untuk mengelola subset hub yang dipilih.
Untuk membuat namespace, pastikan Anda menentukan nama unik untuk namespace layanan; tentukan pusat data tempat namespace akan berada; dan, tentukan grup sumber daya tempat namespace akan ditetapkan.
Setelah namespace layanan dibuat, Anda dapat menggunakan cmdlet New-AzNotificationHubsNamespaceAuthorizationRules untuk menetapkan aturan otorisasi ke namespace tersebut.
Aturan otorisasi digunakan untuk mengelola izin ke namespace.

## EXAMPLES

### Contoh 1: Membuat hub pemberitahuan
```powershell
New-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners"
```

Perintah ini membuat hub pemberitahuan bernama ContosoPartners.
Namespace akan terletak di pusat data US Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Membuat hub pemberitahuan dengan tag
```powershell
New-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup" -Location "West US" -Namespace "ContosoPartners" -Tags @{Name="Audience";Value="PartnerOrganizations"}
```

Perintah ini membuat hub pemberitahuan bernama ContosoPartners.
Namespace akan terletak di pusat data US Barat dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.
Selain itu, perintah ini membuat tag dengan nama Audiens dan nilai PartnerOrganizations dan ditetapkan ke namespace.
Ini memastikan bahwa namespace layanan akan ditampilkan setiap kali Anda memfilter item tempat tag Audiens diatur ke PartnerOrganizations.

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
Menentukan nama tampilan pusat data yang akan menghosting Namespace.
Meskipun Anda dapat mengatur parameter ini ke lokasi yang valid, untuk performa optimal, Anda mungkin ingin menggunakan pusat data yang terletak di dekat sebagian besar pengguna Anda.

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
Menentukan nama namespace layanan baru.
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
Menentukan grup sumber daya tempat namespace layanan akan ditetapkan.
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventarisasi dan administrasi.

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

### -Tag
Menentukan pasangan nama-nilai yang dapat digunakan untuk mengategorikan dan menata item Azure.
Tag berfungsi mirip dengan kata kunci, dan beroperasi di seluruh penyebaran.
Misalnya, jika Anda mencari semua item dengan tag Departemen:IT, pencarian akan mengembalikan semua item Azure yang memiliki tag tersebut, terlepas dari hal-hal seperti jenis item, lokasi, atau grup sumber daya.
Tag individual terdiri dari dua bagian: *Nama* dan, secara opsional, *Nilai*.
Misalnya, di Departemen:IT, nama tag adalah Departemen dan nilai tagnya adalah IT.
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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)

[Set-AzNotificationHubsNamespace](./Set-AzNotificationHubsNamespace.md)


