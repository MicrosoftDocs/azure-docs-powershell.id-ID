---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: 3F59F7E8-CD32-40CB-9DE0-3FB044439DD0
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/new-azurermnotificationhubsnamespaceauthorizationrules
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/New-AzureRmNotificationHubsNamespaceAuthorizationRules.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/New-AzureRmNotificationHubsNamespaceAuthorizationRules.md
ms.openlocfilehash: 6a55a1b6b032bf2354d7d88699744f9cc5dbaea2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427555"
---
# New-AzureRmNotificationHubsNamespaceAuthorizationRules

## SYNOPSIS
Membuat aturan otorisasi dan menetapkan aturan itu ke ruang nama hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InputFileParameterSet
```
New-AzureRmNotificationHubsNamespaceAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-InputFile] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SASRuleParameterSet
```
New-AzureRmNotificationHubsNamespaceAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-SASRule] <SharedAccessAuthorizationRuleAttributes> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmNotificationHubsNamespaceAuthorizationRules** membuat aturan otorisasi Tanda Tangan Akses Bersama (SAS, Shared Access Signature) dan menetapkannya ke ruang nama hub pemberitahuan.
Aturan otorisasi mengelola hak pengguna ke ruang nama dan ke hub pemberitahuan yang dimuat dengan ruang nama itu.
Cmdlet ini menyediakan dua cara untuk membuat aturan otorisasi baru dan menetapkannya ke ruang nama.
Anda dapat membuat contoh objek **SharedAccessAuthorizationRuleAttributes,** lalu mengonfigurasi objek tersebut dengan nilai properti yang ingin dimiliki aturan baru.
Ini bisa dilakukan menggunakan .NET Framework.
Kemudian, Anda dapat menyalin nilai properti tersebut ke aturan baru menggunakan parameter *SASRule.*
Alternatifnya, Anda dapat membuat file JSON (JavaScript Object Notation) yang berisi nilai konfigurasi yang relevan, lalu menerapkan nilai-nilai tersebut menggunakan parameter *InputFile.*
File JSON adalah file teks yang menggunakan sintaks yang sama seperti berikut: {  
    "Nama": "ContosoAuthorizationRule",  
    "PrimaryKey": "WE4qH0398AyXjlekt56gg1gMR3NHoMs29KeyUnnpUk01Y=",  
    "Hak": \[  
        "Dengarkan",  
        "Kirim"  
    \]  
} Ketika digunakan bersama dengan cmdlet **New-AzureRmNotificationHubsNamespaceAuthorizationRules,** sampel JSON sebelumnya membuat aturan otorisasi bernama ContosoAuthorizationRule yang memberi pengguna hak Dengarkan dan Kirim ke ruang nama.
*PrimaryKey yang* digunakan untuk autentikasi, dapat dihasilkan secara acak menggunakan perintah Windows PowerShell berikut: \[ Konversi \] ::ToBase64String((1,32 |% { \[ byte/](Get-Random -Minimum 0 -Maksimum 255) }))

## EXAMPLES

### Contoh 1: Membuat aturan otorisasi dan menetapkannya ke ruang nama
```
PS C:\>New-AzureRmNotificationHubAuthorizationRules -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -InputFile "C:\Configuration\NamespaceAuthorizationRules.json"
```

Perintah ini membuat aturan otorisasi dan menetapkan aturan tersebut ke ruang nama ContosoNamespace.
Saat membuat aturan ini Anda harus menentukan ruang nama yang tepat dan grup sumber daya yang diberi ruang nama.
Namun, Anda tidak perlu menentukan informasi apa pun tentang aturan itu sendiri: informasi aturan akan diambil dari file input C:\Configuration\NamespaceAuthorizationRules.json.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -InputFile
Menentukan jalur ke file JSON yang berisi informasi konfigurasi untuk aturan otorisasi yang baru.

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
Menentukan ruang nama tempat aturan otorisasi akan ditetapkan.
Ruang nama menyediakan cara untuk mengelompokkan dan mengkategorikan hub pemberitahuan.
Aturan baru harus ditetapkan ke ruang nama yang sudah ada.
Cmdlet **New-AzureRmNotificationHubsNamespaceAuthorizationRules** tidak dapat membuat ruang nama baru.

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
Menentukan grup sumber daya tempat ruang nama ditetapkan.
Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu manajemen inventaris dan administrasi Azure.
Anda harus menggunakan grup sumber daya yang sudah ada.
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
Menentukan objek **SharedAccessAuthorizationRuleAttributes yang** berisi informasi konfigurasi untuk aturan baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## CATATAN

## RELATED LINKS

[Get-AzureRmNotificationHubAuthorizationRules](./Get-AzureRmNotificationHubAuthorizationRules.md)

[Remove-AzureRmNotificationHubAuthorizationRules](./Remove-AzureRmNotificationHubAuthorizationRules.md)

[Set-AzureRmNotificationHubAuthorizationRules](./Set-AzureRmNotificationHubAuthorizationRules.md)


