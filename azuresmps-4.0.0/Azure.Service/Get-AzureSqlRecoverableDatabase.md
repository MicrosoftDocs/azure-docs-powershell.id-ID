---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: 83E8DAD8-151A-408D-819F-274CB813ABDA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 58ed537ec716cb344996d8523adf78f78a1b4435
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428094"
---
# Get-AzureSqlRecoverableDatabase

## SYNOPSIS
Mendapatkan database yang dapat dipulihkan dari server tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### AllDatabasesOnGivenServer (Default)
```
Get-AzureSqlRecoverableDatabase -ServerName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### GivenDatabaseOnGivenServer
```
Get-AzureSqlRecoverableDatabase -ServerName <String> -DatabaseName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### GivenDatabaseObject
```
Get-AzureSqlRecoverableDatabase -Database <RecoverableDatabase> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSqlRecoverableDatabase** mendapatkan database yang dapat dipulihkan dari server tertentu.
Cmdlet ini mendapatkan database tertentu yang dapat dipulihkan atau semua database yang dapat dipulihkan di server.

## EXAMPLES

### Contoh 1: Mendapatkan semua database yang dapat dipulihkan
```
PS C:\> Get-AzureSqlRecoverableDatabase -ServerName "Server01"
```

Perintah ini mendapatkan semua database yang dapat dipulihkan di server bernama Server01.

### Contoh 2: Mendapatkan database tertentu yang dapat dipulihkan
```
PS C:\> Get-AzureSqlRecoverableDatabase -ServerName "Server01" -DatabaseName "Database17"
```

Perintah ini akan mengambil database yang bernama Database17 di server yang bernama Server01.

## PARAMETERS

### -Database
Menentukan objek yang mewakili database yang dapat dipulihkan oleh cmdlet ini.

```yaml
Type: RecoverableDatabase
Parameter Sets: GivenDatabaseObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatabaseName
Menentukan nama database yang dapat dipulihkan oleh cmdlet ini.

```yaml
Type: String
Parameter Sets: GivenDatabaseOnGivenServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Menentukan nama server asal cmdlet ini mendapatkan database yang dapat dipulihkan.

```yaml
Type: String
Parameter Sets: AllDatabasesOnGivenServer, GivenDatabaseOnGivenServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Management.Sql.Models.RecoverableDatabase

## OUTPUTS

### IEnumerable\<Microsoft.WindowsAzure.Management.Sql.Models.RecoverableDatabase\>

## CATATAN
* Anda harus menggunakan autentikasi berbasis sertifikat untuk menjalankan cmdlet ini. Jalankan perintah berikut di komputer tempat menjalankan cmdlet ini: 

`PS C:\\\> $subId = \<Subscription ID\>`
`PS C:\\\> $thumbprint = \<Certificate Thumbprint\>`
`PS C:\\\> $myCert = Get-Item Cert:\CurrentUser\My\$thumbprint`
`PS C:\\\> Set-AzureSubscription -SubscriptionName "mySubscription" -SubscriptionId $subId -Certificate $myCert`
`PS C:\\\> Select-AzureSubscription -SubscriptionName "mySubscription"`

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Dapatkan Database yang Dapat Dipulihkan](https://msdn.microsoft.com/en-us/library/azure/dn800985.aspx)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Start-AzureSqlDatabaseRecovery](./Start-AzureSqlDatabaseRecovery.md)


