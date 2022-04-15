---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
Module Name: AzureRM.Sql
ms.assetid: 60E0D10F-9B93-45A9-A1FF-5C943B8CA09C
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.sql/set-azurermsqlserveractivedirectoryadministrator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerActiveDirectoryAdministrator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Set-AzureRmSqlServerActiveDirectoryAdministrator.md
ms.openlocfilehash: f801d3e36fabf0fcd0b5829ed01ad0410517a0c9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142314515"
---
# Set-AzureRmSqlServerActiveDirectoryAdministrator

## SYNOPSIS
Menyediakan administrator Azure AD untuk SQL Server.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmSqlServerActiveDirectoryAdministrator [-DisplayName] <String> [[-ObjectId] <Guid>]
 [-ServerName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmSqlServerActiveDirectoryAdministrator** menyediakan administrator Azure Active Directory (Azure AD) untuk AzureSQL Server dalam langganan saat ini.
Anda hanya bisa menyediakan satu administrator dalam satu waktu.
Anggota Azure AD berikut ini dapat ditetapkan sebagai administrator SQL Server:
- Anggota asli Azure AD 
- Anggota gabungan Azure AD 
- Anggota yang diimpor dari AZURE AD lain yang merupakan anggota asli atau gabungan 
- Azure AD grup yang dibuat sebagai grup keamanan akun Microsoft, seperti yang ada di domain Outlook.com, Hotmail.com, atau Live.com, tidak didukung sebagai administrator.
Akun tamu lain, seperti yang ada di domain Gmail.com atau Yahoo.com, tidak didukung sebagai administrator.
Kami menyarankan agar Anda menyediakan grup Azure AD khusus sebagai administrator.

## EXAMPLES

### Contoh 1: Menyediakan grup administrator untuk server
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "DBAs" 
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

Perintah ini menyediakan grup administrator Azure AD bernama DBAs untuk server bernama Server01.
Server ini dikaitkan dengan grup sumber daya ResourceGroup01.

### Contoh 2: Menyediakan pengguna administrator untuk server
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "David Chew"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
resourcegroup01   server01   David Chew  11E95548-B179-4FE1-9AF4-ACA49D13ABB9
```

Perintah ini menyediakan pengguna Azure AD sebagai administrator untuk server bernama Server01.

### Contoh 3: Menyediakan grup administrator dengan menentukan ID-nya
```
PS C:\>Set-AzureRmSqlServerActiveDirectoryAdministrator -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DisplayName "DBAs" -ObjectId "40b79501-b343-44ed-9ce7-da4c8cc7353b"
ResourceGroupName ServerName DisplayName ObjectId 
----------------- ---------- ----------- -------- 
ResourceGroup01   Server01   DBAs        40b79501-b343-44ed-9ce7-da4c8cc7353b
```

Perintah ini menyediakan grup administrator Azure AD bernama DBAs untuk server bernama Server01.
Perintah menentukan ID untuk parameter *ObjectId* .
Ini memastikan bahwa perintah berhasil meskipun nama tampilan grup tidak unik.

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

### -DisplayName
Menentukan nama tampilan administrator Azure AD yang ditetapkan cmdlet ini.

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

### -ObjectId
Menentukan ID unik administrator Azure AD yang ditetapkan cmdlet ini.
Jika nama tampilan tidak unik, Anda harus menentukan nilai untuk parameter ini.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat server ditetapkan.

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

### -ServerName
Menentukan nama SQL Server tempat cmdlet ini menyediakan administrator.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Guid

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerActiveDirectoryAdministrator.Model.AzureSqlServerActiveDirectoryAdministratorModel

## CATATAN

## RELATED LINKS

[Get-AzureRmSqlServerActiveDirectoryAdministrator](./Get-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Remove-AzureRmSqlServerActiveDirectoryAdministrator](./Remove-AzureRmSqlServerActiveDirectoryAdministrator.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


