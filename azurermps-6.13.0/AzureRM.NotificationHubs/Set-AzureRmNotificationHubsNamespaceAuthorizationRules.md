---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: F0981A7A-1B17-4141-A267-927E5B78BE5F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/set-azurermnotificationhubsnamespaceauthorizationrules
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Set-AzureRmNotificationHubsNamespaceAuthorizationRules.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Set-AzureRmNotificationHubsNamespaceAuthorizationRules.md
ms.openlocfilehash: be65e7e55eca726b7fab39e0abcb272abbd65c6ec3601f22f67eef17dc248a71
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418533"
---
# Set-AzureRmNotificationHubsNamespaceAuthorizationRules

## SYNOPSIS
Mengatur aturan otorisasi untuk ruang nama hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InputFileParameterSet
```
Set-AzureRmNotificationHubsNamespaceAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-InputFile] <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SASRuleParameterSet
```
Set-AzureRmNotificationHubsNamespaceAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-SASRule] <SharedAccessAuthorizationRuleAttributes> [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmNotificationHubsNamespaceAuthorizationRules** mengubah aturan otorisasi Shared Access Signature (SAS) yang ditetapkan untuk ruang nama hub pemberitahuan.
Aturan otorisasi mengelola hak pengguna ke ruang nama dan ke hub pemberitahuan yang terdapat dalam ruang nama itu.
Cmdlet ini menyediakan dua cara untuk mengubah aturan otorisasi yang ditetapkan ke ruang nama.
Sebagai contoh, Anda dapat membuat contoh objek **SharedAccessAuthorizationRuleAttributes,** lalu mengonfigurasi objek tersebut dengan nilai properti yang ingin dimiliki aturan.
Anda bisa menggunakan .NET Framework untuk menyelesaikan ini.
Anda kemudian dapat menyalin nilai properti tersebut ke aturan melalui parameter *SASRule.*
Alternatifnya, Anda dapat membuat file JSON (JavaScript Object Notation) yang berisi nilai konfigurasi yang relevan, lalu menerapkan nilai-nilai tersebut melalui parameter *InputFile.*
File JSON adalah file teks yang menggunakan sintaks yang mirip dengan ini: {  
    "Nama": "ContosoAuthorizationRule",  
    "PrimaryKey": "WE4qH0398AyXjlekt56gg1gMR3NHoMs29KeyUnnpUk01Y=",  
    "Hak": \[  
        "Dengarkan",  
        "Kirim"  
    \]  
} Ketika digunakan bersama dengan cmdlet **Set-AzureRmNotificationHubsNamespaceAuthorizationRules,** sampel JSON sebelumnya mengubah aturan otorisasi bernama ContosoAuthorizationRule untuk memberi pengguna hak Dengarkan dan Kirim ke ruang nama.

## EXAMPLES

### Contoh 1: Mengubah aturan otorisasi yang ditetapkan ke ruang nama
```
PS C:\>Set-AzureRmNotificationHubsNamespaceAuthorizationRules -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationGroup" -InputFile "C:\Configuration\AuthorizationRules.json"
```

Perintah ini mengubah aturan otorisasi yang ditetapkan ke ruang nama bernama ContosoNamespace.
Anda harus menentukan grup sumber daya yang diberi ruang nama.
Informasi tentang aturan otorisasi tidak disertakan dalam perintah itu sendiri.
Sebagai gantinya, informasi tersebut dapat diperoleh dari file input C:\Configuration\AuthorizationRules.json.

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
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Menentukan ruang nama yang berisi aturan otorisasi yang dimodifikasi cmdlet ini.
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
Menentukan grup sumber daya tempat ruang nama ditetapkan.
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

### -SASRule
Menentukan objek **SharedAccessAuthorizationRuleAttributes** yang berisi informasi konfigurasi untuk aturan otorisasi yang dimodifikasi cmdlet ini.

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

[Get-AzureRmNotificationHubsNamespaceAuthorizationRules](./Get-AzureRmNotificationHubsNamespaceAuthorizationRules.md)

[New-AzureRmNotificationHubsNamespaceAuthorizationRules](./New-AzureRmNotificationHubsNamespaceAuthorizationRules.md)

[Remove-AzureRmNotificationHubsNamespaceAuthorizationRules](./Remove-AzureRmNotificationHubsNamespaceAuthorizationRules.md)


