---
external help file: Microsoft.Azure.Commands.NotificationHubs.dll-Help.xml
Module Name: AzureRM.NotificationHubs
ms.assetid: F769A8AB-E025-49EE-AEA4-0D27EAEE341F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.notificationhubs/get-azurermnotificationhubsnamespacelistkeys
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHubsNamespaceListKeys.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/NotificationHubs/Commands.NotificationHubs/help/Get-AzureRmNotificationHubsNamespaceListKeys.md
ms.openlocfilehash: f559d141a478b721b0e07d3e32e0b12ad1d70bc7e63ef7e4cae809a8e52a7fa9
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416483"
---
# Get-AzureRmNotificationHubsNamespaceListKeys

## SYNOPSIS
Mendapatkan string koneksi utama dan sekunder yang terkait dengan aturan otorisasi ruang nama hub pemberitahuan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmNotificationHubsNamespaceListKeys [-ResourceGroup] <String> [-Namespace] <String>
 [-AuthorizationRule] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmNotificationHubsNamespaceListKeys** mengembalikan string koneksi utama dan sekunder untuk aturan otorisasi Tanda Tangan Akses Bersama (SAS, Shared Access Signature) yang ditetapkan ke ruang nama hub pemberitahuan.
Aturan otorisasi mengelola hak pengguna ke ruang nama hub pemberitahuan.
Setiap aturan menyertakan string koneksi utama dan sekunder.

## EXAMPLES

### Contoh 1: Mendapatkan string koneksi utama dan sekunder untuk aturan otorisasi
```
PS C:\>Get-AzureRmNotificationHubsNamespaceListKeys -Namespace "ContosoNamespace" -ResourceGroup "ContosoNotificationsGroup" -AuthorizationRule "ListenRule"
```

Perintah ini mengembalikan string koneksi utama dan sekunder untuk aturan otorisasi bernama ListenRule yang ditetapkan ke ruang nama ContosoNamespace.
Saat Anda menjalankan perintah ini Anda harus menyertakan nama grup sumber daya yang diberi ruang nama.

## PARAMETERS

### -AuthorizationRule
Menentukan nama aturan autentikasi SAS.
Aturan ini menentukan tipe akses yang pengguna miliki ke hub pemberitahuan.

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

### -Namespace
Menentukan ruang nama yang berisi string koneksi yang akan didapsum cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.NotificationHubs.Models.ResourceListKeys

## CATATAN

## RELATED LINKS

[Get-AzureRmNotificationHubsNamespace](./Get-AzureRmNotificationHubsNamespace.md)

[Get-AzureRmNotificationHubsNamespaceAuthorizationRules](./Get-AzureRmNotificationHubsNamespaceAuthorizationRules.md)


