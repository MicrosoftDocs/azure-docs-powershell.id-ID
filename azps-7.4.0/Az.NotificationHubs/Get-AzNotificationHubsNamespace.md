---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 9805B3F1-C6BB-4A0F-A7C3-1DD1ACB75CDA
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespace.md
ms.openlocfilehash: b8b25cd5566fae475959a870f36a476c39a420c7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144616604"
---
# Get-AzNotificationHubsNamespace

## SYNOPSIS
Mendapatkan informasi tentang namespace hub pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/get-aznotificationhubsnamespace) untuk informasi terbaru.

## SYNTAX

```
Get-AzNotificationHubsNamespace [[-ResourceGroup] <String>] [[-Namespace] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzNotificationHubsNamespace** mendapatkan informasi tentang namespace hub pemberitahuan.
Cmdlet ini memberi Anda opsi untuk mendapatkan informasi untuk semua namespace Anda, informasi tentang namespace yang ditetapkan ke grup sumber daya tertentu; atau untuk mengembalikan informasi tentang namespace tertentu.
Namespace adalah kontainer logis yang membantu Anda mengatur dan mengelola hub pemberitahuan Anda.
Anda harus memiliki setidaknya satu namespace hub pemberitahuan: semua hub pemberitahuan harus ditetapkan ke namespace layanan.
Satu namespace layanan dapat menampung beberapa hub yang berarti Anda mungkin hanya memerlukan satu namespace layanan di organisasi Anda.
Namun, Anda juga dapat memiliki beberapa namespace untuk mengatur hub Anda dengan lebih baik, atau untuk memberikan izin individu tertentu untuk mengelola subset hub yang dipilih.
Cmdlet **Get-AzNotificationHubsNamespace** mengembalikan informasi dasar tentang namespace itu sendiri.
Untuk mendapatkan informasi tentang aturan otorisasi yang terkait dengan namespace, gunakan Get-AzNotificationHubsNamespaceAuthorizationRules.

## EXAMPLES

### Contoh 1: Mendapatkan informasi untuk semua namespace hub pemberitahuan
```powershell
Get-AzNotificationHubsNamespace
```

Perintah ini mengembalikan informasi untuk semua namespace hub pemberitahuan Anda.

### Contoh 2: Mendapatkan informasi untuk namespace hub pemberitahuan tunggal
```powershell
Get-AzNotificationHubsNamespace -Namespace "ContosoNamespace"
```

Perintah ini mendapatkan informasi untuk namespace hub pemberitahuan tunggal: ContosoNamespace.

### Contoh 3: Mendapatkan informasi untuk semua hub pemberitahuan yang ditetapkan ke namespace tertentu
```powershell
Get-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi untuk semua namespace hub pemberitahuan yang ditetapkan ke grup sumber daya ContosoNotificationsGroup.

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

### -Namespace
Menentukan nama unik untuk namespace layanan.
Namespace menyediakan cara untuk mengelompokkan dan mengategorikan hub pemberitahuan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Menentukan grup sumber daya tempat namespace ditetapkan.
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventarisasi dan administrasi Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespaceAuthorizationRule](./Get-AzNotificationHubsNamespaceAuthorizationRule.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)

[Set-AzNotificationHubsNamespace](./Set-AzNotificationHubsNamespace.md)


