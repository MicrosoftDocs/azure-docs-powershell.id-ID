---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 08D03498-D18D-47FE-8916-702FA2E7D719
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhubsnamespaceauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespaceAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubsNamespaceAuthorizationRule.md
ms.openlocfilehash: 255197800e98437b0f8da8ba2ee316e964a612a6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142946927"
---
# Get-AzNotificationHubsNamespaceAuthorizationRule

## SYNOPSIS
Mendapatkan informasi tentang aturan otorisasi yang terkait dengan ruang nama hub pemberitahuan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/get-aznotificationhubsnamespaceauthorizationrule) untuk informasi terbaru.

## SYNTAX

```
Get-AzNotificationHubsNamespaceAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [[-AuthorizationRule] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNotificationHubsNamespaceAuthorizationRule** mengembalikan informasi tentang aturan otorisasi Tanda Tangan Akses Bersama (SAS) yang terkait dengan ruang nama hub pemberitahuan.
Anda bisa mengembalikan informasi tentang semua aturan yang terkait dengan ruang nama.
Alternatifnya, dan dengan menyertakan parameter *AuthorizationRule* , Anda dapat mengembalikan informasi untuk aturan tertentu.
Aturan otorisasi mengelola akses ke ruang nama.
Hal ini dilakukan melalui pembuatan tautan, sebagai URI, berdasarkan tingkat izin yang berbeda.
Tingkat platform dapat berupa salah satu hal berikut: 
- Mendengarkan
- Mengirim
- Kelola Klien diarahkan ke salah satu URI ini berdasarkan tingkat izin yang sesuai.
Misalnya, klien yang diberi izin Dengar akan diarahkan ke URI untuk izin tersebut.
Cmdlet ini hanya mendapatkan aturan otorisasi yang terkait dengan ruang nama.
Untuk mendapatkan informasi tentang ruang nama itu sendiri, gunakan Get-AzNotificationHubsNamespace.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua aturan otorisasi yang ditetapkan ke ruang nama
```
PS C:\>Get-AzNotificationHubsNamespaceAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup"
```

Perintah ini mendapatkan informasi tentang semua aturan otorisasi yang ditetapkan ke ruang nama ContosoNamespace dan grup sumber daya ContosoNotificationsGroup.

### Contoh 2: Mendapatkan informasi tentang aturan otorisasi
```
PS C:\>Get-AzNotificationHubsNamespaceAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -AuthorizationRule "ListenRule"
```

Perintah ini mendapatkan informasi tentang aturan otorisasi ruang nama tunggal bernama ListenRule.
Anda harus menyertakan ruang nama dan grup sumber daya saat mendapatkan informasi untuk aturan otorisasi tertentu.

## PARAMETERS

### -AuthorizationRule
Menentukan nama aturan autentikasi SAS.
Aturan ini menentukan tipe akses yang dimiliki pengguna ke ruang nama.

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
Menentukan ruang nama tempat aturan otorisasi ditetapkan.
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
Menentukan grup sumber daya tempat aturan otorisasi ditetapkan.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespace](./Get-AzNotificationHubsNamespace.md)

[New-AzNotificationHubsNamespace](./New-AzNotificationHubsNamespace.md)

[Remove-AzNotificationHubsNamespace](./Remove-AzNotificationHubsNamespace.md)

[Set-AzNotificationHubsNamespace](./Set-AzNotificationHubsNamespace.md)


