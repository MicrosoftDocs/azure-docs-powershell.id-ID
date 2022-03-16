---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 62631E1C-FB43-4E87-82C2-159A9D1D4221
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/remove-aznotificationhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Remove-AzNotificationHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Remove-AzNotificationHub.md
ms.openlocfilehash: 516dc4dae977b70d41186234e5da6d63034c6a12
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140248615"
---
# Remove-AzNotificationHub

## SYNOPSIS
Menghapus hub pemberitahuan yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.notificationhubs/remove-aznotificationhub) untuk informasi terkini.

## SYNTAX

```
Remove-AzNotificationHub [-ResourceGroup] <String> [-Namespace] <String> [-NotificationHub] <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzNotificationHub** menghapus hub pemberitahuan yang sudah ada.
Hub pemberitahuan digunakan untuk mengirim pemberitahuan push ke beberapa klien terlepas dari platform yang digunakan oleh klien tersebut.
Platform termasuk, namun tidak terbatas pada: iOS, Android, Windows Phone 8, Windows Store.
Hub pemberitahuan kurang lebih sama dengan aplikasi individu: setiap aplikasi biasanya akan memiliki hub pemberitahuannya sendiri.
Anda dapat menghapus hub pemberitahuan yang sudah ada menggunakan cmdlet **Remove-AzNotificationHub** .
Setelah hub dihapus, Anda tidak dapat lagi menggunakan hub tersebut untuk mengirim pemberitahuan push kepada pengguna.

## EXAMPLES

### Contoh 1: Hapus hub pemberitahuan
```
PS C:\>Remove-AzNotificationHub -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -NotificationHub "ContosoInternalHub"
```

Perintah ini menghapus hub pemberitahuan bernama ContosoInternalHub.
Untuk menghapus hub, Anda harus menentukan ruang nama tempat hub terletak serta grup sumber daya tempat hub ditetapkan.

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

### -Force
Jangan minta konfirmasi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

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
Menentukan hub pemberitahuan yang akan dihapus.
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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzNotificationHub](./Get-AzNotificationHub.md)

[New-AzNotificationHub](./New-AzNotificationHub.md)

[Set-AzNotificationHub](./Set-AzNotificationHub.md)


