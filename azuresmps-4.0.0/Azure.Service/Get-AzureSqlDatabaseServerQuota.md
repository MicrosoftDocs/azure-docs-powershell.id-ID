---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 6723557D-8052-4BFA-872C-384B1423B3AE
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3fe03c348ade07f0375502d98e782cc55109fd7f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043803"
---
# Get-AzureSqlDatabaseServerQuota

## SYNOPSIS
Mendapatkan informasi kuota untuk server Azure SQL Database.

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
Cmdlet **Get-AzureSqlDatabaseServerQuota** mendapatkan informasi kuota untuk contoh server Azure SQL Database tertentu.
Tentukan konteks koneksi atau nama server.
Jika Anda tidak menentukan nama kuota, cmdlet ini akan mendapatkan semua informasi kuota untuk server.

## EXAMPLES

### Contoh 1: Dapatkan informasi untuk kuota tertentu
```
PS C:\> $QuotaPremium = GetAzureSqlDatabaseServerQuota $Context -QuotaName "Premium_Databases"
```

Perintah ini mendapatkan kuota bernama Premium_Databases dari server Azure SQL Database yang ditentukan oleh koneksi yang disimpan dalam variabel $Context.

### Contoh 2: Dapatkan informasi untuk semua kuota
```
PS C:\> $QuotaList = GetAzureSqlDatabaseServerQuota $Context
```

Perintah ini mendapatkan semua nilai kuota dari server yang ditentukan oleh $Context koneksi.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan nama nilai kuota yang didapat cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServerQuota[]

## NOTES
* Autentikasi: Cmdlet ini dapat menggunakan autentikasi SQL Server atau autentikasi berbasis sertifikat. Untuk contoh pengaturan autentikasi, lihat cmdlet New-AzureSqlDatabaseServerContext.

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


