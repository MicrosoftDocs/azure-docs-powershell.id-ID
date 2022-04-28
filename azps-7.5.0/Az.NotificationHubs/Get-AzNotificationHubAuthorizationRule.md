---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 7A9D8F5A-6035-411B-8FDB-96ABFEED05A2
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhubauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubAuthorizationRule.md
ms.openlocfilehash: dade85cdcc23851495435818f86badaaad12d977
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144245679"
---
# Get-AzNotificationHubAuthorizationRule

## SYNOPSIS
Mendapatkan informasi tentang aturan otorisasi yang terkait dengan hub pemberitahuan.

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
Aturan otorisasi akan membuat tautan, sebagai URI, berdasarkan tingkat izin yang berbeda.
Klien diarahkan ke salah satu URI ini berdasarkan tingkat izin yang sesuai.
Misalnya, klien dengan izin Dengar akan diarahkan ke URI untuk izin tersebut.
Cmdlet **Get-AzNotificationHubAuthorizationRule** hanya mendapatkan informasi tentang aturan otorisasi yang terkait dengan hub pemberitahuan.
Untuk mendapatkan informasi tentang hub itu sendiri, gunakan Get-AzNotificationHub.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan
```powershell
Get-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -NotificationHub "ContosoInternalHub"
```

Perintah ini mendapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoInternalHub di namespace ContosoNamespace.
Anda harus menentukan namespace tempat hub berada serta grup sumber daya tempat hub ditetapkan.

### Contoh 2: Mendapatkan informasi untuk aturan otorisasi yang ditetapkan ke hub pemberitahuan
```powershell
Get-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -NotificationHub "ContosoInternalHub" -AuthorizationRule "ListenRule"
```

Perintah ini mendapatkan informasi untuk semua aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoInternalHub di namespace ContosoNamespace.
Perintah menggunakan parameter *AuthorizationRule* untuk membatasi data yang dikembalikan ke satu aturan otorisasi bernama ListenRule.

## PARAMETERS

### -AuthorizationRule
Menentukan nama aturan autentikasi SAS.
Aturan ini menentukan jenis akses yang dimiliki pengguna ke hub pemberitahuan.

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
Menentukan namespace tempat hub pemberitahuan ditetapkan.
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
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu menyederhanakan manajemen inventarisasi dan administrasi Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubsNamespaceAuthorizationRule](./Get-AzNotificationHubsNamespaceAuthorizationRule.md)

[New-AzNotificationHubAuthorizationRule](./New-AzNotificationHubAuthorizationRule.md)

[Remove-AzNotificationHubAuthorizationRule](./Remove-AzNotificationHubAuthorizationRule.md)

[Set-AzNotificationHubAuthorizationRule](./Set-AzNotificationHubAuthorizationRule.md)


