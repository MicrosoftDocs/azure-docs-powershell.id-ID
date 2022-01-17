---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 796396B4-1F9D-4D53-AD2E-4CE83B563E93
online version: https://docs.microsoft.com/en-us/powershell/module/az.notificationhubs/get-aznotificationhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHub.md
ms.openlocfilehash: 944805a4883edce9354cfa372bfd30db145fc4ca
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136030727"
---
# Get-AzNotificationHub

## SYNOPSIS
Mendapatkan informasi tentang hub pemberitahuan Anda.

## SINTAKS

```
Get-AzNotificationHub [-ResourceGroup] <String> [-Namespace] <String> [[-NotificationHub] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzNotificationHub** mendapatkan informasi tentang hub pemberitahuan dalam ruang nama yang ditentukan dan ditetapkan ke grup sumber daya yang ditentukan.
Misalnya, Anda bisa mendapatkan informasi untuk semua hub pemberitahuan dalam ruang nama ContosoNamespace dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.
Alternatifnya, Anda dapat menggunakan parameter *NotificationHub* untuk membatasi data yang dikembalikan menjadi informasi tentang hub pemberitahuan tertentu.
Hub pemberitahuan digunakan untuk mengirimkan pemberitahuan push ke beberapa klien, terlepas dari platform, seperti iOS, Android, Windows Phone 8, dan Windows Store, yang digunakan oleh klien tersebut.
Hub tersebut kira-kira sama dengan aplikasi individu dan setiap aplikasi Anda biasanya akan memiliki hub pemberitahuannya sendiri.
Cmdlet ini hanya mendapatkan informasi tentang hub itu sendiri.
Cmdlet lain, seperti Get-AzNotificationHubAuthorizationRules, Get-AzNotificationHubListKeys, dan Get-AzNotificationHubPNSCredentials, diperlukan untuk mendapatkan informasi tentang aturan otorisasi hub, string koneksi, dan kredensial layanan pemberitahuan platform.

## CONTOH

### Contoh 1: Dapatkan informasi untuk semua hub pemberitahuan dalam ruang nama tertentu
```powershell
PS C:\>Get-AzNotificationHub -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi untuk semua hub pemberitahuan dalam ruang nama contosoNamespace yang telah ditetapkan ke grup sumber daya ContosoNotificationsGroup.

### Contoh 2

Mendapatkan informasi tentang hub pemberitahuan Anda. (otomatisgenerated)

<!-- Aladdin Generated Example -->
```powershell
Get-AzNotificationHub -Namespace 'ContosoNamespace' -NotificationHub 'ContosoInternalHub' -ResourceGroup 'ContosoNotificationsGroup'
```

## PARAMETERS

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

### -Namespace
Menentukan ruang nama tempat hub pemberitahuan ditetapkan.
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

### -NotificationHub
Menentukan nama hub pemberitahuan yang akan dapatkan cmdlet ini.
Hub pemberitahuan digunakan untuk mengirim pemberitahuan push ke beberapa klien terlepas dari platform yang digunakan oleh klien tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Menentukan grup sumber daya tempat hub pemberitahuan ditetapkan.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.NotificationHubs.Models.NotificationHubAttributes

## CATATAN

## LINK TERKAIT

[Get-AzNotificationHubAuthorizationRule](./Get-AzNotificationHubAuthorizationRule.md)

[Get-AzNotificationHubListKey](./Get-AzNotificationHubListKey.md)

[Get-AzNotificationHubPNSCredential](./Get-AzNotificationHubPNSCredential.md)

[New-AzNotificationHub](./New-AzNotificationHub.md)

[Remove-AzNotificationHub](./Remove-AzNotificationHub.md)

[Set-AzNotificationHub](./Set-AzNotificationHub.md)


