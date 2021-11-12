---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: A2C22A8A-EF50-4BE3-82DF-5ED6F69C00CA
online version: ''
schema: 2.0.0
ms.openlocfilehash: a5921caa493121f22be8626af2e89e80d9195ce8904f3dd2f3a274298948b787
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419234"
---
# Get-AzureSqlDatabaseServiceObjective

## SYNOPSIS
Mendapatkan tujuan layanan untuk Azure SQL Database server.

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
Cmdlet **Get-AzureSqlDatabaseServiceObjective** mendapatkan tujuan layanan untuk Azure SQL Database server.
Tujuan layanan dirujuk sebagai tingkat kinerja.
Jika Anda tidak menentukan tujuan layanan, cmdlet ini mengembalikan semua tujuan layanan yang valid untuk server yang ditentukan.

Cmdlet ini berlaku untuk tingkatan layanan Dasar, Standar, Premium layanan.

## EXAMPLES

### Contoh 1: Dapatkan semua tujuan layanan dengan menggunakan konteks koneksi
```
PS C:\> Get-AzureSqlDatabaseServiceObjective -Context $Context
```

Perintah ini mendapatkan semua tujuan layanan untuk server yang ditentukan oleh konteks koneksi $Context tentukan.

### Contoh 2: Dapatkan semua tujuan layanan dengan menggunakan nama server
```
PS C:\> Get-AzureSqlDatabaseServiceObjective -ServerName "Server01"
```

Perintah ini akan mendapatkan semua tujuan layanan untuk server bernama Server01.

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
Menentukan objek yang mewakili tujuan layanan yang akan didaptifkan cmdlet ini.
Nilai valid adalah: 

- Dasar: dd6d99bb-f193-4ec1-86f2-43d3bccbc49c
- Standar (S0): f1173c43-91bd-4aaa-973c-54e79e15235b
- Standar (S1): 1b1ebd4d-d903-4baa-97f9-4ea675f5e928
- Standar (S2): 455330e1-00cd-488b-b5fa-177c226f28b7
- *Standard (S3): 789681b8-ca10-4eb0-bdf2-e0b050601b40
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P1): 7203483a-c4fb-4304-9e9f-17c71c904f5d
- Premium (P2): a7d1b92d-c987-4375-b54d-2b1d0e0f5bb0
- Premium (P3): a7c4c615-cfb1-464b-b252-925be0a19446

*Standar (S3) adalah bagian dari Pembaruan SQL Database V12 (pratinjau).
Untuk informasi selengkapnya, [lihat Apa yang Baru dalam Azure SQL Database V12 Preview](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/) ( ) di pustaka `https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/` Azure.

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
Menentukan nama tujuan layanan yang akan dapatkan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServiceObjective

## OUTPUTS

### IEnumerable\<Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.ServiceObjective\>

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://msdn.microsoft.com/library/ee336279.aspx)

[Dapatkan Tujuan Tingkat Layanan](https://msdn.microsoft.com/en-us/library/azure/dn505709.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[New-AzureSqlDatabaseServerContext](./New-AzureSqlDatabaseServerContext.md)


