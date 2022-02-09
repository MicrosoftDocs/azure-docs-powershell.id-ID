---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 9805B3F1-C6BB-4A0F-A7C3-1DD1ACB75CDA
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespace.md
ms.openlocfilehash: 6fa093953212e958c5dd2a87a7650cfa1a92add0
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138271084"
---
# Get-AzNotificationHubsNamespace

## SYNOPSIS
Mendapatkan informasi tentang ruang nama hub pemberitahuan.

## SYNTAX

```
Get-AzNotificationHubsNamespace [[-ResourceGroup] <String>] [[-Namespace] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzNotificationHubsNamespace** mendapatkan informasi tentang ruang nama hub pemberitahuan.
Cmdlet ini menyediakan opsi untuk mendapatkan informasi untuk semua ruang nama Anda, informasi tentang ruang nama yang ditetapkan ke grup sumber daya yang ditentukan; atau untuk mengembalikan informasi tentang ruang nama tertentu.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda setidaknya harus memiliki satu ruang nama hub pemberitahuan: semua hub pemberitahuan harus ditetapkan ke ruang nama.
Satu ruang nama bisa menjadi rumah beberapa hub yang berarti bahwa Anda mungkin hanya membutuhkan satu ruang nama di organisasi Anda.
Namun, Anda juga bisa memiliki beberapa ruang nama untuk menata hub Anda dengan lebih baik, atau memberikan izin kepada individu tertentu untuk mengelola subkumpulan hub yang dipilih.
Cmdlet **Get-AzNotificationHubsNamespace** mengembalikan informasi dasar tentang kumpulan nama itu sendiri.
Untuk mendapatkan informasi tentang aturan otorisasi yang terkait dengan ruang nama gunakan Get-AzNotificationHubsNamespaceAuthorizationRules.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk semua ruang nama hub pemberitahuan
```
PS C:\>Get-AzNotificationHubsNamespace
```

Perintah ini mengembalikan informasi untuk semua ruang nama hub pemberitahuan Anda.

### Contoh 2: Dapatkan informasi untuk satu ruang nama hub pemberitahuan
```
PS C:\>Get-AzNotificationHubsNamespace -Namespace "ContosoNamespace"
```

Perintah ini mendapatkan informasi untuk ruang nama hub pemberitahuan tunggal: ContosoNamespace.

### Contoh 3: Dapatkan informasi untuk semua hub pemberitahuan yang ditetapkan ke ruang nama tertentu
```
PS C:\>Get-AzNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi untuk semua ruang nama hub pemberitahuan yang ditetapkan ke grup sumber daya ContosoNotificationsGroup.

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
Menentukan nama yang unik untuk ruang nama.
Ruang nama menyediakan cara untuk mengelompokkan dan mengkategorikan hub pemberitahuan.

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
Menentukan grup sumber daya tempat ruang nama ditetapkan.
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu manajemen inventaris dan administrasi Azure.

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

## CATATAN

## RELATED LINKS

[Get-AzNotificationHubsNamespaceAuthorizationRule](./Get-AzNotificationHubsNamespaceAuthorizationRule.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)

[Set-AzNotificationHubsNamespace](./Set-AzNotificationHubsNamespace.md)


