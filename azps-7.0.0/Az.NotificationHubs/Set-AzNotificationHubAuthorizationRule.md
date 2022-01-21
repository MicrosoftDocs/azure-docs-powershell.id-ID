---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NotificationHubs.dll-Help.xml
Module Name: Az.NotificationHubs
ms.assetid: BD311CEF-378B-463E-8998-CC3E9A5B3A7B
online version: https://docs.microsoft.com/powershell/module/az.notificationhubs/set-aznotificationhubauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NotificationHubs/NotificationHubs/help/Set-AzNotificationHubAuthorizationRule.md
ms.openlocfilehash: 92b897df3d54ab5d7a11394a32ed517b6538827a
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136530620"
---
# Set-AzNotificationHubAuthorizationRule

## SYNOPSIS
Mengatur aturan otorisasi untuk hub pemberitahuan.

## SYNTAX

### InputFileParameterSet
```
Set-AzNotificationHubAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [-NotificationHub] <String> [-InputFile] <String> [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SASRuleParameterSet
```
Set-AzNotificationHubAuthorizationRule [-ResourceGroup] <String> [-Namespace] <String>
 [-NotificationHub] <String> [-SASRule] <SharedAccessAuthorizationRuleAttributes> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzNotificationHubAuthorizationRule** mengubah aturan otorisasi Shared Access Signature (SAS) yang ditetapkan ke hub pemberitahuan.
Aturan otorisasi mengelola akses ke hub pemberitahuan Anda dengan membuat link, sebagai URI, berdasarkan pada tingkat izin yang berbeda.
Tingkat izin bisa menjadi salah satu dari yang berikut: 
- Dengarkan
- Kirim
- Kelola Klien diarahkan ke salah satu URI ini berdasarkan tingkat izin yang sesuai.
Misalnya, klien yang diberikan izin Dengarkan akan diarahkan ke URI untuk izin tersebut.
Cmdlet ini menyediakan dua cara untuk mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan.
Sebagai contoh, Anda dapat membuat contoh objek **SharedAccessAuthorizationRuleAttributes,** lalu mengonfigurasi objek tersebut dengan nilai properti yang ingin dimiliki aturan.
Anda dapat mengonfigurasi objek melalui .NET Framework.
Kemudian, Anda dapat menyalin nilai properti tersebut ke aturan menggunakan parameter *SASRule.*
Alternatifnya, Anda dapat membuat file JSON (JavaScript Object Notation) yang berisi nilai konfigurasi yang relevan, lalu menerapkan nilai-nilai tersebut melalui parameter *InputFile.*
File JSON adalah file teks yang menggunakan sintaks seperti ini: { "Name": "ContosoAuthorizationRule",  
  "PrimaryKey": "WE4qH0398AyXjlekt56gg1gMR3NHoMs29IkalUnnpUk01Y=",  
  "Hak": \[  
        "Dengarkan",  
        "Kirim"  
    \]  
  } Ketika digunakan bersama dengan cmdlet New-AzNotificationHubAuthorizationRule, sampel JSON sebelumnya mengubah aturan otorisasi bernama ContosoAuthorizationRule untuk memberi pengguna hak Dengarkan dan Kirim ke hub.

## EXAMPLES

### Contoh 1: Mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan
```
PS C:\>Set-AzNotificationHubAuthorizationRule -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationGroup" -NotificationHub "ContosoExternalHub" -InputFile "C:\Configuration\AuthorizationRules.json"
```

Perintah ini mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoExternalHub.
Anda harus menentukan ruang nama tempat hub terletak serta grup sumber daya yang ditetapkan hub.
Informasi tentang aturan yang dimodifikasi tidak disertakan dalam perintah itu sendiri.
Sebagai gantinya, informasi tersebut dapat ditemukan di file input C:\Configuration\AuthorizationRules.json.

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

### -InputFile
Menentukan jalur ke file JSON yang berisi informasi konfigurasi untuk aturan yang baru.

```yaml
Type: System.String
Parameter Sets: InputFileParameterSet
Aliases:

Required: True
Position: 3
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
Menentukan hub pemberitahuan di mana cmdlet ini menetapkan aturan otorisasi.
Hub pemberitahuan digunakan untuk mengirim pemberitahuan push ke beberapa klien terlepas dari yang digunakan oleh klien tersebut.

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
Menentukan grup sumber daya tempat hub pemberitahuan ditetapkan. Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang membantu manajemen inventaris dan administrasi Azure.

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
Menentukan objek **SharedAccessAuthorizationRuleAttributes** yang berisi informasi konfigurasi untuk aturan otorisasi yang dimodifikasi.

```yaml
Type: Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes
Parameter Sets: SASRuleParameterSet
Aliases:

Required: True
Position: 3
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## CATATAN

## RELATED LINKS

[Get-AzNotificationHubAuthorizationRule](./Get-AzNotificationHubAuthorizationRule.md)

[New-AzNotificationHubAuthorizationRule](./New-AzNotificationHubAuthorizationRule.md)

[Remove-AzNotificationHubAuthorizationRule](./Remove-AzNotificationHubAuthorizationRule.md)


