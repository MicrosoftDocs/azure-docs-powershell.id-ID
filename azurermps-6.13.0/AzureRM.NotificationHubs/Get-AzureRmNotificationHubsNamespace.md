---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: 9805B3F1-C6BB-4A0F-A7C3-1DD1ACB75CDA
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/get-azurermnotificationhubsnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHubsNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHubsNamespace.md
ms.openlocfilehash: b4603566b793cbded7e593c9e4a23c3788c140de
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141776673"
---
# Get-AzureRmNotificationHubsNamespace

## SYNOPSIS
Mendapatkan informasi tentang ruang nama hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmNotificationHubsNamespace [[-ResourceGroup] <String>] [[-Namespace] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmNotificationHubsNamespace** mendapatkan informasi tentang ruang nama hub pemberitahuan.
Cmdlet ini menyediakan opsi untuk mendapatkan informasi untuk semua ruang nama Anda, informasi tentang ruang nama yang ditetapkan ke grup sumber daya tertentu; atau untuk mengembalikan informasi tentang ruang nama tertentu.
Ruang nama adalah wadah logis yang membantu Anda menata dan mengelola hub pemberitahuan.
Anda harus memiliki setidaknya satu ruang nama hub pemberitahuan: semua hub pemberitahuan harus ditetapkan ke ruang nama.
Ruang nama tunggal dapat menampung beberapa hub yang berarti Anda mungkin hanya memerlukan satu ruang nama di organisasi Anda.
Namun, Anda juga bisa memiliki beberapa ruang nama untuk menata hub Anda dengan lebih baik, atau untuk memberikan izin individu tertentu untuk mengelola subset hub yang dipilih.
Cmdlet **Get-AzureRmNotificationHubsNamespace** mengembalikan informasi dasar tentang ruang nama itu sendiri.
Untuk mendapatkan informasi tentang aturan otorisasi yang terkait dengan ruang nama, gunakan Get-AzureRmNotificationHubsNamespaceAuthorizationRules.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk semua ruang nama hub pemberitahuan
```
PS C:\>Get-AzureRmNotificationHubsNamespace
```

Perintah ini mengembalikan informasi untuk semua ruang nama hub pemberitahuan Anda.

### Contoh 2: Mendapatkan informasi untuk ruang nama hub pemberitahuan tunggal
```
PS C:\>Get-AzureRmNotificationHubsNamespace -Namespace "ContosoNamespace"
```

Perintah ini mendapatkan informasi untuk ruang nama hub pemberitahuan tunggal: ContosoNamespace.

### Contoh 3: Mendapatkan informasi untuk semua hub pemberitahuan yang ditetapkan ke ruang nama tertentu
```
PS C:\>Get-AzureRmNotificationHubsNamespace -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi untuk semua ruang nama hub pemberitahuan yang ditetapkan ke grup sumber daya ContosoNotificationsGroup.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Namespace
Menentukan nama unik untuk ruang nama.
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
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang hanya membantu manajemen inventaris dan administrasi Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.NamespaceAttributes

## CATATAN

## RELATED LINKS

[Get-AzureRmNotificationHubsNamespaceAuthorizationRules](./Get-AzureRmNotificationHubsNamespaceAuthorizationRules.md)

[Baru-AzureRmNotificationHubsNamespace](./New-AzureRmNotificationHubsNamespace.md)

[Hapus-AzureRmNotificationHubsNamespace](./Remove-AzureRmNotificationHubsNamespace.md)

[Set-AzureRmNotificationHubsNamespace](./Set-AzureRmNotificationHubsNamespace.md)


