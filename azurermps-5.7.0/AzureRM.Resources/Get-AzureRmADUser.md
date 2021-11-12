---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: BF254F2F-F658-45CC-8AC8-53FF96CFCAAD
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermaduser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmADUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmADUser.md
ms.openlocfilehash: e111da68e00e0edad54823c763c06f84ea5100e9
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422580"
---
# Get-AzureRmADUser

## SYNOPSIS
Memfilter pengguna direktori aktif.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADUser [-UserPrincipalName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SearchStringParameterSet
```
Get-AzureRmADUser -SearchString <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ObjectIdParameterSet
```
Get-AzureRmADUser -ObjectId <Guid> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### UPNParameterSet
```
Get-AzureRmADUser -UserPrincipalName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### MailParameterSet
```
Get-AzureRmADUser -Mail <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Memfilter pengguna direktori aktif.

## EXAMPLES

### Memfilter pengguna menggunakan UPN
```
PS C:\> Get-AzureRmADUser -UPN foo@domain.com
```

Mendapatkan pengguna dengan foo@domain.com

### Memfilter pengguna menggunakan String Pencarian
```
PS C:\> Get-AzureRmADUser -SearchString Joe
```

Memfilter semua pengguna iklan yang memiliki Joe di nama tampilan.

### Pengguna Daftar AD
```
PS C:\> Get-AzureRmADUser
```

Mendapatkan semua pengguna AD

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mail
```yaml
Type: String
Parameter Sets: MailParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Id objek pengguna.

```yaml
Type: Guid
Parameter Sets: ObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SearchString
Nama tampilan pengguna

```yaml
Type: String
Parameter Sets: SearchStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserPrincipalName
UPN pengguna.

```yaml
Type: String
Parameter Sets: EmptyParameterSet
Aliases: UPN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UPNParameterSet
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### System.Collections.generic.List'1[Microsoft.Azure.Graph. RBAC. Version1_6.ActiveDirectory.DIRECTDUser]

## CATATAN

## RELATED LINKS

[New-AzureRmADUser](./New-AzureRmADUser.md)

[Set-AzureRmADUser](./Set-AzureRmADUser.md)

[Remove-AzureRmADUser](./Remove-AzureRmADUser.md)

