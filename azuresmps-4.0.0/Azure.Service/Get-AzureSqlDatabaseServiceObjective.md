---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: A2C22A8A-EF50-4BE3-82DF-5ED6F69C00CA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 474c41a50416494d7de043c32cbdbed8fafae697
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245598"
---
# Get-AzureSqlDatabaseServiceObjective

## SYNOPSIS
Mendapatkan tujuan layanan untuk server Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByConnectionContext (Default)
```
Get-AzureSqlDatabaseServiceObjective -Context <IServerDataServiceContext>
 [-ServiceObjective <ServiceObjective>] [-ServiceObjectiveName <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByServerName
```
Get-AzureSqlDatabaseServiceObjective -ServerName <String> [-ServiceObjective <ServiceObjective>]
 [-ServiceObjectiveName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlDatabaseServiceObjective** mendapatkan tujuan layanan untuk server Azure SQL Database.
Tujuan layanan disebut sebagai tingkat kinerja.
Jika Anda tidak menentukan tujuan layanan, cmdlet ini mengembalikan semua tujuan layanan yang valid untuk server yang ditentukan.

Cmdlet ini berlaku untuk tingkat layanan Basic, Standard, dan Premium.

## EXAMPLES

### Contoh 1: Mendapatkan semua tujuan layanan menggunakan konteks koneksi
```
PS C:\> Get-AzureSqlDatabaseServiceObjective -Context $Context
```

Perintah ini mendapatkan semua tujuan layanan untuk server yang ditentukan konteks koneksi $Context.

### Contoh 2: Dapatkan semua tujuan layanan dengan menggunakan nama server
```
PS C:\> Get-AzureSqlDatabaseServiceObjective -ServerName "Server01"
```

Perintah ini mendapatkan semua tujuan layanan untuk server bernama Server01.

## PARAMETERS

### -Konteks
Menentukan konteks koneksi server.

```yaml
Type: IServerDataServiceContext
Parameter Sets: ByConnectionContext
Aliases: 

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

### -ServiceObjective
Menentukan objek yang mewakili tujuan layanan yang didapatkan cmdlet ini.
Nilai yang valid adalah: 

- Dasar: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
- Standar (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
- Standar (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
- Standar (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
- *Standar (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
- Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

*Standar (S3) adalah bagian dari Pembaruan SQL Database Terbaru V12 (pratinjau).
Untuk informasi selengkapnya, lihat [Apa yang Baru dalam Pratinjau V12 Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/) (`https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/`) di pustaka Azure.

```yaml
Type: ServiceObjective
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServiceObjectiveName
Menentukan nama tujuan layanan untuk didapatkan.
Nilai yang valid adalah: Dasar, S0, S1, S2, S3, P1, P2, dan P3.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServiceObjective

## OUTPUTS

### Ienumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServiceObjective\>

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://msdn.microsoft.com/library/ee336279.aspx)

[Dapatkan Tujuan Tingkat Layanan](https://msdn.microsoft.com/en-us/library/azure/dn505709.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Baru-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


