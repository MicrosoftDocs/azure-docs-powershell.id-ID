---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: 3F59F7E8-CD32-40CB-9DE0-3FB044439DD0
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/new-aznotificationhubsnamespaceauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespaceAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/New-AzNotificationHubsNamespaceAuthorizationRule.md
ms.openlocfilehash: 9e256a6895226678113982e7106cdccad3062e40
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145662916"
---
# New-AzNotificationHubsNamespaceAuthorizationRule

## SYNOPSIS
Membuat aturan otorisasi dan menetapkan aturan tersebut ke namespace hub pemberitahuan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.notificationhubs/new-aznotificationhubsnamespaceauthorizationrule) untuk informasi terbaru.

## SYNTAX

### InputFileParameterSet
```
New-AzNotificationHubsNamespaceAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [-InputFile] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SASRuleParameterSet
```
New-AzNotificationHubsNamespaceAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [-SASRule] <SharedAccessAuthorizationRuleAttributes> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNotificationHubsNamespaceAuthorizationRule** membuat aturan otorisasi Tanda Tangan Akses Bersama (SAS) dan menetapkannya ke namespace hub pemberitahuan.
Aturan otorisasi mengelola hak pengguna ke namespace layanan dan ke hub pemberitahuan yang terkandung dengan namespace tersebut.
Cmdlet ini menyediakan dua cara untuk membuat aturan otorisasi baru dan menetapkannya ke namespace.
Anda dapat membuat **instans objek SharedAccessAuthorizationRuleAttributes** lalu mengonfigurasi objek tersebut dengan nilai properti yang Anda inginkan untuk dimiliki aturan baru.
Ini dapat dilakukan menggunakan .NET Framework.
Anda kemudian dapat menyalin nilai properti tersebut ke aturan baru Anda dengan menggunakan parameter *SASRule* .
Atau, Anda dapat membuat file JSON (JavaScript Object Notation) yang berisi nilai konfigurasi yang relevan lalu menerapkan nilai tersebut dengan menggunakan parameter *InputFile* .
File JSON adalah file teks yang menggunakan sintaks yang mirip dengan yang berikut ini: {  
    "Name": "ContosoAuthorizationRule",  
    "PrimaryKey": "WE4qH0398AyXjlekt56gg1gMR3NHoMs29KkUnnpUk01Y=",  
    "Hak": \[  
        "Dengarkan",  
        "Kirim"  
    \]  
} Ketika digunakan bersama dengan cmdlet **New-AzNotificationHubsNamespaceAuthorizationRule** , sampel JSON sebelumnya membuat aturan otorisasi bernama ContosoAuthorizationRule yang memberi pengguna hak Dengar dan Kirim ke namespace.
*PrimaryKey* yang digunakan untuk autentikasi, dapat dihasilkan secara acak dengan menggunakan perintah Windows PowerShell berikut: \[Convert\]::ToBase64String((1..32 |% { \[byte/](Get-Random -Minimum 0 -Maximum 255) }))

## EXAMPLES

### Contoh 1: Membuat aturan otorisasi dan menetapkannya ke namespace
```powershell
New-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -InputFile "C:\Configuration\NamespaceAuthorizationRules.json"
```

Perintah ini membuat aturan otorisasi dan menetapkan aturan tersebut ke namespace ContosoNamespace.
Saat membuat aturan ini, Anda harus menentukan namespace yang sesuai dan grup sumber daya tempat namespace ditetapkan.
Namun, Anda tidak perlu menentukan informasi apa pun tentang aturan itu sendiri: informasi aturan akan diambil dari file input C:\Configuration\NamespaceAuthorizationRules.json.

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

### -InputFile
Menentukan jalur ke file JSON yang berisi informasi konfigurasi untuk aturan otorisasi baru.

```yaml
Type: System.String
Parameter Sets: InputFileParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Menentukan namespace tempat aturan otorisasi akan ditetapkan.
Namespace menyediakan cara untuk mengelompokkan dan mengategorikan hub pemberitahuan.
Aturan baru harus ditetapkan ke namespace yang sudah ada.
Cmdlet **New-AzNotificationHubsNamespaceAuthorizationRule** tidak dapat membuat namespace baru.

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
Menentukan grup sumber daya tempat namespace layanan ditetapkan.
Grup sumber daya mengatur item seperti namespace, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu hanya manajemen inventarisasi dan administrasi Azure.
Anda harus menggunakan grup sumber daya yang ada.
Cmdlet ini tidak dapat membuat grup sumber daya baru.

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

### -SASRule
Menentukan objek **SharedAccessAuthorizationRuleAttributes** yang berisi informasi konfigurasi untuk aturan baru.

```yaml
Type: Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes
Parameter Sets: SASRuleParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS

[Get-AzNotificationHubAuthorizationRule](./Get-AzNotificationHubAuthorizationRule.md)

[Remove-AzNotificationHubAuthorizationRule](./Remove-AzNotificationHubAuthorizationRule.md)

[Set-AzNotificationHubAuthorizationRule](./Set-AzNotificationHubAuthorizationRule.md)


