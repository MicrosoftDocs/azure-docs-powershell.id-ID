---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 638B2BF6-23F8-4038-B20B-1CFABFDBF5D3
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/get-azapimanagementuser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagementUser.md
ms.openlocfilehash: f668a5f7c524a5dbd7a339a705cc2966502693c5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142295125"
---
# Get-AzApiManagementUser

## SYNOPSIS
Mendapatkan pengguna atau pengguna.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/get-azapimanagementuser) untuk informasi terbaru.

## SYNTAX

### GeAllUsers (Default)
```
Get-AzApiManagementUser -Context <PsApiManagementContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByUserId
```
Get-AzApiManagementUser -Context <PsApiManagementContext> [-UserId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByUser
```
Get-AzApiManagementUser -Context <PsApiManagementContext> [-FirstName <String>] [-LastName <String>]
 [-State <PsApiManagementUserState>] [-Email <String>] [-GroupId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApiManagementUser** mendapatkan pengguna tertentu, atau semua pengguna, jika tidak ada pengguna yang ditentukan.

## EXAMPLES

### Contoh 1: Dapatkan semua pengguna
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Get-AzApiManagementUser -Context $apimContext
```

Perintah ini akan mendapatkan semua pengguna.

### Contoh 2: Mendapatkan pengguna menurut ID
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Get-AzApiManagementUser -Context $apimContext -UserId "0123456789"
```

Perintah ini mendapatkan pengguna menurut ID.

### Contoh 3: Mendapatkan pengguna menurut nama belakang
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Get-AzApiManagementUser -Context $apimContext -LastName "Fuller"
```

Perintah ini memberi pengguna yang memiliki nama belakang tertentu, Fuller.

### Contoh 4: Mendapatkan pengguna berdasarkan alamat email
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Get-AzApiManagementUser -Context $apimContext -Email "user@contoso.com"
```

Perintah ini mendapatkan pengguna yang memiliki alamat email tertentu.

### Contoh 5: Mendapatkan semua pengguna dalam grup
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Get-AzApiManagementUser -Context $apimContext -GroupId "0001"
```

Perintah ini akan membuat semua pengguna berada dalam grup yang ditentukan.

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Email
Menentukan alamat email pengguna.
Jika parameter ini ditentukan, cmdlet ini akan menemukan pengguna melalui email.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: GetByUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FirstName
Menentukan nama depan pengguna.
Jika parameter ini ditentukan, cmdlet ini akan menemukan pengguna berdasarkan nama depan.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: GetByUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GroupId
Menentukan pengidentifikasi grup.
Jika ditentukan, cmdlet ini akan menemukan semua pengguna dalam grup yang ditentukan.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: GetByUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LastName
Menentukan nama belakang pengguna.
Jika ditentukan, cmdlet ini akan menemukan pengguna menurut nama belakang.
Parameter ini bersifat opsional.

```yaml
Type: System.String
Parameter Sets: GetByUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Negara Bagian
Menentukan status pengguna.
Jika ditentukan, cmdlet ini akan menemukan pengguna dalam status ini.
Parameter ini bersifat opsional.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementUserState]
Parameter Sets: GetByUser
Aliases:
Accepted values: Active, Blocked, Deleted, Pending

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
Parameter Sets: GetByUserId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Nullable'1[[Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementUserState, Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement, Version=1.0.0.0, Culture=netral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementUser

## CATATAN

## RELATED LINKS

[New-AzApiManagementUser](./New-AzApiManagementUser.md)

[Remove-AzApiManagementUser](./Remove-AzApiManagementUser.md)

[Set-AzApiManagementUser](./Set-AzApiManagementUser.md)


