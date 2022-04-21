---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: BD311CEF-378B-463E-8998-CC3E9A5B3A7B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/set-azurermnotificationhubauthorizationrules
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Set-AzureRmNotificationHubAuthorizationRules.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Set-AzureRmNotificationHubAuthorizationRules.md
ms.openlocfilehash: 24c65b6f7bf39d4fe046b020a9427dba7bf53aa9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142726570"
---
# Set-AzureRmNotificationHubAuthorizationRules

## SYNOPSIS
Mengatur aturan otorisasi untuk hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InputFileParameterSet
```
Set-AzureRmNotificationHubAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-NotificationHub] <String> [-InputFile] <String> [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SASRuleParameterSet
```
Set-AzureRmNotificationHubAuthorizationRules [-ResourceGroup] <String> [-Namespace] <String>
 [-NotificationHub] <String> [-SASRule] <SharedAccessAuthorizationRuleAttributes> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmNotificationHubAuthorizationRules** mengubah aturan otorisasi Tanda Tangan Akses Bersama (SAS) yang ditetapkan ke hub pemberitahuan.
Aturan otorisasi mengelola akses ke hub pemberitahuan Anda dengan membuat tautan, sebagai URI, berdasarkan tingkat izin yang berbeda.
Tingkat izin bisa menjadi salah satu hal berikut ini: 
- Mendengarkan
- Mengirim
- Kelola Klien diarahkan ke salah satu URI ini berdasarkan tingkat izin yang sesuai.
Misalnya, klien yang diberi izin Dengar akan diarahkan ke URI untuk izin tersebut.
Cmdlet ini menyediakan dua cara untuk mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan.
Untuk satu, Anda dapat membuat contoh objek **SharedAccessAuthorizationRuleAttributes** lalu mengonfigurasi objek tersebut dengan nilai properti yang anda inginkan untuk dimiliki aturan.
Anda dapat mengonfigurasi objek melalui .NET Framework.
Anda kemudian dapat menyalin nilai properti tersebut ke aturan menggunakan parameter *SASRule* .
Alternatifnya, Anda dapat membuat file JSON (JavaScript Object Notation) yang berisi nilai konfigurasi yang relevan lalu menerapkan nilai tersebut melalui parameter *InputFile* .
File JSON adalah file teks yang menggunakan sintaks seperti ini: { "Name": "ContosoAuthorizationRule",  
  "PrimaryKey": "WE4qH0398AyXjlekt56gg1gMR3NHoMs29KkUnnpUk01Y=",  
  "Hak": \[  
        "Dengarkan",  
        "Kirim"  
    \]  
  } Ketika digunakan bersamaan dengan cmdlet New-AzureRmNotificationHubAuthorizationRules, sampel JSON sebelumnya mengubah aturan otorisasi bernama ContosoAuthorizationRule untuk memberikan pengguna hak Dengarkan dan Kirim ke hub.

## EXAMPLES

### Contoh 1: Mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan
```
PS C:\>Set-AzureRmNotificationHubAuthorizationRules -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationGroup" -NotificationHub "ContosoExternalHub" -InputFile "C:\Configuration\AuthorizationRules.json"
```

Perintah ini mengubah aturan otorisasi yang ditetapkan ke hub pemberitahuan bernama ContosoExternalHub.
Anda harus menentukan ruang nama tempat hub berada serta grup sumber daya yang ditetapkan hub.
Informasi tentang aturan yang diubah tidak disertakan dalam perintah itu sendiri.
Sebagai gantinya, informasi tersebut ditemukan dalam file input C:\Configuration\AuthorizationRules.json.

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

### -Paksa
Jangan meminta konfirmasi.

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
Menentukan jalur ke file JSON yang berisi informasi konfigurasi untuk aturan baru.

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
Menentukan hub pemberitahuan tempat cmdlet ini menetapkan aturan otorisasi.
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
Menentukan grup sumber daya tempat hub pemberitahuan ditetapkan. Grup sumber daya menata item seperti ruang nama, hub pemberitahuan, dan aturan otorisasi dengan cara yang hanya membantu manajemen inventaris dan administrasi Azure.

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
Menentukan objek **SharedAccessAuthorizationRuleAttributes** yang berisi informasi konfigurasi untuk aturan otorisasi yang diubah.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.NotificationHubs.Models.SharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS

[Get-AzureRmNotificationHubAuthorizationRules](./Get-AzureRmNotificationHubAuthorizationRules.md)

[AzureRmNotificationHubAuthorizationRules baru](./New-AzureRmNotificationHubAuthorizationRules.md)

[Hapus-AzureRmNotificationHubAuthorizationRules](./Remove-AzureRmNotificationHubAuthorizationRules.md)


