---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 7A9D8F5A-6035-411B-8FDB-96ABFEED05A2
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhubauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubAuthorizationRule.md
ms.openlocfilehash: 85a483a5edf316a95114738812b173ec54788f08
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142837450"
---
# Get-AzNotificationHubAuthorizationRule

## SYNOPSIS
Mendapatkan informasi tentang aturan otorisasi yang terkait dengan hub pemberitahuan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/get-aznotificationhubauthorizationrule) untuk informasi terbaru.

## SYNTAX

```
Get-AzNotificationHubAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [-NotificationHub] <String> [[-AuthorizationRule] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNotificationHubAuthorizationRule** mendapatkan informasi tentang aturan otorisasi Tanda Tangan Akses Bersama (SAS) yang terkait dengan hub pemberitahuan.
Cmdlet mengembalikan informasi tentang semua aturan yang terkait dengan hub atau, dengan menyertakan parameter *AuthorizationRule* , mendapatkan informasi tentang aturan tertentu.
Aturan otorisasi mengelola akses ke hub pemberitahuan Anda.
Aturan otorisasi akan membuat link, sebagai URI, berdasarkan tingkat izin yang berbeda.
Klien diarahkan ke salah satu URI ini berdasarkan tingkat izin yang sesuai.
Misalnya, klien dengan izin Dengar akan diarahkan ke URI untuk izin tersebut.
Cmdlet **Get-AzNotificationHubAuthorizationRule** hanya mendapatkan informasi tentang aturan otorisasi yang terkait dengan hub pemberitahuan.
Untuk mendapatkan informasi tentang hub itu sendiri, gunakan Get-AzNotificationHub.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan
```
PS C:\>Get-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -NotificationHub "ContosoInternalHub"
```

Perintah ini mendapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoInternalHub di ruang nama ContosoNamespace.
Anda harus menentukan ruang nama tempat hub berada serta grup sumber daya tempat hub telah ditetapkan.

### Contoh 2: Mendapatkan informasi untuk aturan otorisasi yang ditetapkan ke hub pemberitahuan
```
PS C:\>Get-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -NotificationHub "ContosoInternalHub" -AuthorizationRule "ListenRule"
```

Perintah ini mendapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoInternalHub di ruang nama ContosoNamespace.
Perintah menggunakan parameter *AuthorizationRule* untuk membatasi data yang dikembalikan ke satu aturan otorisasi bernama ListenRule.

## PARAMETERS

### -AuthorizationRule
Menentukan nama aturan autentikasi SAS.
Aturan ini menentukan tipe akses yang dimiliki pengguna ke hub pemberitahuan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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
Menentukan hub pemberitahuan bahwa cmdlet ini menetapkan aturan otorisasi.
Hub pemberitahuan digunakan untuk mengirim pemberitahuan push ke beberapa klien terlepas dari platform yang digunakan oleh klien tersebut.

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

### -ResourceGroup
Menentukan grup sumber daya tempat hub pemberitahuan ditetapkan.
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu menyederhanakan manajemen inventaris dan administrasi Azure.

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

[Get-AzNotificationHubsNamespaceAuthorizationRule](./Get-AzNotificationHubsNamespaceAuthorizationRule.md)

[New-AzNotificationHubAuthorizationRule](./New-AzNotificationHubAuthorizationRule.md)

[Hapus-AzNotificationHubAuthorizationRule](./Remove-AzNotificationHubAuthorizationRule.md)

[Set-AzNotificationHubAuthorizationRule](./Set-AzNotificationHubAuthorizationRule.md)


