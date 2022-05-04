---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 326C87EB-EC3B-4B04-B593-EAC56FFA854A
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/get-aznotificationhublistkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubListKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Get-AzNotificationHubListKey.md
ms.openlocfilehash: 0682309a9ce7fd4be9d6d028c1fd33f1e45447d4
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144737452"
---
# Get-AzNotificationHubListKey

## SYNOPSIS
Mendapatkan string koneksi primer dan sekunder yang terkait dengan aturan otorisasi hub pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/get-aznotificationhublistkey) untuk informasi terbaru.

## SYNTAX

```
Get-AzNotificationHubListKey [-ResourceGroup] <String> [-Namespace] <String> [-NotificationHub] <String>
 [-AuthorizationRule] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNotificationHubListKey** mengembalikan string koneksi utama dan sekunder dari aturan otorisasi Tanda Tangan Akses Bersama (SAS) hub pemberitahuan.
Aturan otorisasi mengelola hak pengguna ke hub.
Setiap aturan menyertakan string koneksi primer dan sekunder.
String koneksi (URI) ini melakukan hal berikut:
- Arahkan pengguna ke sumber daya.
- Sertakan token yang berisi parameter kueri.
Salah satu parameter ini, tanda tangan, digunakan untuk mengautentikasi pengguna dan menyediakan tingkat akses yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan string koneksi primer dan sekunder untuk aturan otorisasi
```powershell
Get-AzNotificationHubListKey -Namespace "ContosoNamespace" -NotificationHub "ContosoInternalHub" -ResourceGroup "ContosoNotificationsGroup" -AuthorizationRule "ListenRule"
```

Perintah ini mendapatkan string koneksi primer dan sekunder untuk aturan otorisasi ListenRule, aturan yang ditetapkan ke hub pemberitahuan ContosoInternalHub.
Perintah harus menyertakan namespace hub dan grup sumber daya.

## PARAMETERS

### -AuthorizationRule
Menentukan nama aturan autentikasi Tanda Tangan Akses Bersama (SAS).
Aturan ini menentukan jenis akses yang dimiliki pengguna ke hub pemberitahuan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Menentukan hub pemberitahuan tempat cmdlet ini menetapkan aturan otorisasi.
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
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventarisasi dan administrasi Azure.

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

### Microsoft.Azure.Management.NotificationHubs.Models.ResourceListKeys

## NOTES

## RELATED LINKS

[Get-AzNotificationHubAuthorizationRule](./Get-AzNotificationHubAuthorizationRule.md)


