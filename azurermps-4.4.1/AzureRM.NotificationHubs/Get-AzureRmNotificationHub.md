---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: 796396B4-1F9D-4D53-AD2E-4CE83B563E93
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHub.md
ms.openlocfilehash: 2bb7d6f6addbbbf91f7f9f93e7e30de9cb3ece81
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425629"
---
# Get-AzureRmNotificationHub

## SYNOPSIS
Mendapatkan informasi tentang hub pemberitahuan Anda.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmNotificationHub [-ResourceGroup] <String> [-Namespace] <String> [[-NotificationHub] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmNotificationHub** mendapatkan informasi tentang hub pemberitahuan dalam ruang nama yang ditentukan dan ditetapkan ke grup sumber daya yang ditentukan.
Misalnya, Anda bisa mendapatkan informasi untuk semua hub pemberitahuan dalam ruang nama ContosoNamespace dan ditetapkan ke grup sumber daya ContosoNotificationsGroup.

Alternatifnya, Anda dapat menggunakan parameter *NotificationHub* untuk membatasi data yang dikembalikan menjadi informasi tentang hub pemberitahuan tertentu.

Hub pemberitahuan digunakan untuk mengirimkan pemberitahuan push ke beberapa klien terlepas dari platform, seperti iOS, Android, Windows Phone 8, dan Windows Store, yang digunakan oleh klien tersebut.
Hub tersebut kira-kira sama dengan aplikasi individu dan setiap aplikasi Anda biasanya akan memiliki hub pemberitahuannya sendiri.

Cmdlet ini hanya mendapatkan informasi tentang hub itu sendiri.
Cmdlet lain, seperti Get-AzureRmNotificationHubAuthorizationRules, Get-AzureRmNotificationHubListKeys, dan Get-AzureRmificationHubPNSCredentials, diperlukan untuk mendapatkan informasi tentang aturan otorisasi hub, string koneksi, dan kredensial layanan pemberitahuan platform.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk semua hub pemberitahuan dalam ruang nama tertentu
```
PS C:\>Get-AzureRmNotificationHub -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi untuk semua hub pemberitahuan dalam ruang nama contosoNamespace yang telah ditetapkan ke grup sumber daya ContosoNotificationsGroup.

## PARAMETERS

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### System.Collections.Generic.List'1[Microsoft.Azure.Commands.NotificationHubs.Models.NotificationHubAttributes]

## CATATAN

## RELATED LINKS

[Get-AzureRmNotificationHubAuthorizationRules](./Get-AzureRmNotificationHubAuthorizationRules.md)

[Get-AzureRmNotificationHubListKeys](./Get-AzureRmNotificationHubListKeys.md)

[Get-AzureRmNotificationHubPNSCredentials](./Get-AzureRmNotificationHubPNSCredentials.md)

[New-AzureRmNotificationHub](./New-AzureRmNotificationHub.md)

[Remove-AzureRmNotificationHub](./Remove-AzureRmNotificationHub.md)

[Set-AzureRmNotificationHub](./Set-AzureRmNotificationHub.md)


