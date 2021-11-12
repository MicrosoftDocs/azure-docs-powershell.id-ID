---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 6723557D-8052-4BFA-872C-384B1423B3AE
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1ec5e8eff3b2d5a353ce0f8274b20e99adda2e66718d62441166b717a4c8efaf
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419396"
---
# Get-AzureSqlDatabaseServerQuota

## SYNOPSIS
Mendapatkan informasi kuota untuk Azure SQL Database server.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionContext
```
Get-AzureSqlDatabaseServerQuota -ConnectionContext <IServerDataServiceContext> [-QuotaName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabaseServerQuota -ServerName <String> [-QuotaName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseServerQuota** mendapatkan informasi kuota untuk instans tertentu dari Azure SQL Database Server.
Menentukan konteks koneksi atau nama server.
Jika Anda tidak menentukan nama kuota, cmdlet ini akan mendapatkan semua informasi kuota untuk server.

## EXAMPLES

### Contoh 1: Mendapatkan informasi untuk kuota tertentu
```
PS C:\> $QuotaPremium = GetAzureSqlDatabaseServerQuota $Context -QuotaName "Premium_Databases"
```

Perintah ini mendapatkan kuota yang Premium_Databases dari server Azure SQL Database yang ditentukan oleh koneksi yang disimpan dalam $Context koneksi.

### Contoh 2: Mendapatkan informasi untuk semua kuota
```
PS C:\> $QuotaList = GetAzureSqlDatabaseServerQuota $Context
```

Perintah ini mendapatkan semua nilai kuota dari server yang ditentukan oleh koneksi $Context.

## PARAMETERS

### -ConnectionContext
Menentukan konteks koneksi server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: Context

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuotaName
Menentukan nama dari nilai kuota yang akan cmdlet dapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server.

```yaml
Type: String
Parameter Sets: ByServerName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServerQuota[]

## CATATAN
* Autentikasi: Cmdlet ini dapat SQL Server autentikasi atau autentikasi berbasis sertifikat. Untuk contoh pengaturan autentikasi, lihat cmdlet New-AzureSqlDatabaseServerContext lanjut.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


