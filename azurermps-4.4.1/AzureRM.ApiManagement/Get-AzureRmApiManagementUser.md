---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: AzureRM.ApiManagement
ms.assetid: 638B2BF6-23F8-4038-B20B-1CFABFDBF5D3
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Get-AzureRmApiManagementUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Get-AzureRmApiManagementUser.md
ms.openlocfilehash: be6c9ee6c0db12e324786052348209703b79601e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428639"
---
# Get-AzureRmApiManagementUser

## SYNOPSIS
Mendapatkan satu atau beberapa pengguna.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Mendapatkan semua pengguna (Default)
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Dapatkan pengguna dengan ID
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [-UserId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Menemukan pengguna
```
Get-AzureRmApiManagementUser -Context <PsApiManagementContext> [-FirstName <String>] [-LastName <String>]
 [-State <PsApiManagementUserState>] [-Email <String>] [-GroupId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmApiManagementUser** mendapatkan pengguna tertentu, atau semua pengguna, jika tidak ada pengguna yang ditentukan.

## EXAMPLES

### Contoh 1: Mendapatkan semua pengguna
```
PS C:\>Get-AzureRmApiManagementUser -Context $apimContext
```

Perintah ini akan memberikan semua pengguna.

### Contoh 2: Dapatkan pengguna dengan ID
```
PS C:\>Get-AzureRmApiManagementUser -Context $apimContext -UserId "0123456789"
```

Perintah ini mendapatkan pengguna menurut ID.

### Contoh: Get users by last name
```
PS C:\>Get-AzureRmApiManagementUser -Context $apimContext -LastName "Fuller"
```

Perintah ini akan memberikan pengguna dengan nama belakang yang ditentukan, Lebih Lengkap.

### Contoh 4: Mendapatkan pengguna berdasarkan alamat email
```
PS C:\>Get-AzureRmApiManagementUser -Context $apimContext -Email 
"user@contoso.com"
```

Perintah ini akan mendapatkan pengguna dengan alamat email yang ditentukan.

### Contoh 5: Mendapatkan semua pengguna dalam grup
```
PS C:\>Get-AzureRmApiManagementUser -Context $apimContext -GroupId "0001"
```

Perintah ini membuat semua pengguna berada dalam grup yang ditentukan.

## PARAMETERS

### -Konteks
Menentukan contoh **PsApiManagementContext**.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Email
Menentukan alamat email pengguna.
Jika parameter ini ditentukan, cmdlet ini menemukan pengguna melalui email.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: Find users
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FirstName
Menentukan nama depan pengguna.
Jika parameter ini ditentukan, cmdlet ini menemukan pengguna dengan nama depan.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: Find users
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupId
Menentukan pengidentifikasi grup.
Jika ditentukan, cmdlet ini menemukan semua pengguna di dalam grup yang ditentukan.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: Find users
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LastName
Menentukan nama belakang pengguna.
Jika ditentukan, cmdlet ini menemukan pengguna menurut nama belakang.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: Find users
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan status pengguna.
Jika ditentukan, cmdlet ini menemukan pengguna dalam status ini.
Parameter ini bersifat opsional.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementUserState]
Parameter Sets: Find users
Aliases: 
Accepted values: Active, Blocked

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserId
Menentukan ID pengguna.
Jika ditentukan, cmdlet ini akan menemukan pengguna dengan pengidentifikasi ini.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: Get user by ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### IList<Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementUser>

## CATATAN

## RELATED LINKS

[New-AzureRmApiManagementUser](./New-AzureRmApiManagementUser.md)

[Remove-AzureRmApiManagementUser](./Remove-AzureRmApiManagementUser.md)

[Set-AzureRmApiManagementUser](./Set-AzureRmApiManagementUser.md)


