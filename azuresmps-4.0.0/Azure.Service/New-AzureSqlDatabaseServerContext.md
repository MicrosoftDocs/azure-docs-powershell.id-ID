---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: B7B29875-D2E5-4E96-AD4B-83032AB18D02
online version: ''
schema: 2.0.0
ms.openlocfilehash: e7517016f06c4e1a5fdfb9a4ed3a4ca9feabab64
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428056"
---
# New-AzureSqlDatabaseServerContext

## SYNOPSIS
Membuat konteks koneksi server.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByServerNameWithSqlAuth (Default)
```
New-AzureSqlDatabaseServerContext -ServerName <String> -Credential <PSCredential> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByManageUrlWithSqlAuth
```
New-AzureSqlDatabaseServerContext [-ServerName <String>] -ManageUrl <Uri> -Credential <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerNameWithCertAuth
```
New-AzureSqlDatabaseServerContext -ServerName <String> [-UseSubscription] [-SubscriptionName <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByFullyQualifiedServerNameWithSqlAuth
```
New-AzureSqlDatabaseServerContext -FullyQualifiedServerName <String> -Credential <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByFullyQualifiedServerNameWithCertAuth
```
New-AzureSqlDatabaseServerContext -FullyQualifiedServerName <String> [-UseSubscription]
 [-SubscriptionName <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureSqlDatabaseServerContext** membuat Azure SQL Database koneksi server baru.
Gunakan SQL Server autentikasi untuk membuat konteks koneksi ke server SQL Database dengan menggunakan kredensial yang ditentukan.
Anda bisa menentukan server SQL Database berdasarkan nama, dengan nama yang sepenuhnya memenuhi syarat, atau dengan URL.
Untuk mendapatkan kredensial, gunakan cmdlet Get-Credential cmdlet yang meminta Anda menentukan nama pengguna dan kata sandi.

Gunakan cmdlet **New-AzureSqlDatabaseServerContext** dengan autentikasi berbasis sertifikat untuk membuat konteks koneksi ke server SQL Database tertentu menggunakan data langganan Azure yang ditentukan.
Anda dapat menentukan server SQL Database berdasarkan nama atau dengan nama yang sepenuhnya memenuhi syarat.
Anda dapat menentukan data langganan sebagai parameter atau data yang dapat diambil dari langganan Azure saat ini.
Gunakan cmdlet Select-AzureSubscription https://msdn.microsoft.com/library/windowsazure/jj152833.aspx untuk memilih langganan Azure saat ini.

## EXAMPLES

### Contoh 1: Membuat konteks menggunakan autentikasi SQL Server
```
PS C:\> $Credential = Get-Credential
PS C:\> $Context = New-AzureSqlDatabaseServerContext -ServerName "lpqd0zbr8y" -Credential $Credential
PS C:\> $Database17 = New-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database17" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

Contoh ini menggunakan autentikasi SQL Server.

Perintah pertama meminta kredensial administrator server, dan menyimpan kredensial di $Credential lain.

Perintah kedua tersambung ke server SQL Database bernama lpqd0zbr8y dengan menggunakan $Credential.

Perintah terakhir membuat database bernama Database17 di server yang menjadi bagian dari konteks dalam $Context.

### Contoh 2: Membuat konteks menggunakan autentikasi berbasis sertifikat
```
PS C:\> $SubscriptionId = <Subscription ID>
PS C:\> $Thumbprint = <Certificate Thumbprint>
PS C:\> $Certificate = Get-Item "Cert:\CurrentUser\My\$Thumbprint"
PS C:\> Set-AzureSubscription -SubscriptionName "Subscription07" -SubscriptionId $SubscriptionId -Certificate $Certificate
PS C:\> Select-AzureSubscription -SubscriptionName "Subscription07"
PS C:\> $Context = New-AzureSqlDatabaseServerContext -ServerName "lpqd0zbr8y" -UseSubscription
```

Contoh ini menggunakan autentikasi berbasis sertifikat.

Dua perintah pertama menetapkan nilai ke $SubscriptionId dan $Thumbprint lainnya.

Perintah ketiga mendapatkan sertifikat yang diidentifikasi dengan thumbprint di $Thumbprint, dan menyimpannya dalam $Certificate.

Perintah keempat mengatur langganan menjadi Langganan07, dan perintah kelima memilih langganan tersebut.

The final command creates a context in the current subscription for the server named lpqd0zbr8y.

## PARAMETERS

### -Credential
Menentukan objek kredensial yang menyediakan SQL Server autentikasi bagi Anda untuk mengakses server.

```yaml
Type: PSCredential
Parameter Sets: ByServerNameWithSqlAuth, ByManageUrlWithSqlAuth, ByFullyQualifiedServerNameWithSqlAuth
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedServerName
Menentukan nama domain berkualifikasi lengkap (FQDN, Fully Qualified Domain Name) untuk server Azure SQL Database.
Misalnya, Server02.database.windows.net.

```yaml
Type: String
Parameter Sets: ByFullyQualifiedServerNameWithSqlAuth, ByFullyQualifiedServerNameWithCertAuth
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManageUrl
Menentukan URL yang digunakan cmdlet ini untuk mengakses Portal Azure SQL DatabaseManagement untuk server.

```yaml
Type: Uri
Parameter Sets: ByManageUrlWithSqlAuth
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
Menentukan nama server database.

```yaml
Type: String
Parameter Sets: ByServerNameWithSqlAuth, ByServerNameWithCertAuth
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByManageUrlWithSqlAuth
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
Menentukan nama langganan Azure yang digunakan cmdlet ini untuk membuat konteks koneksi.
Jika Anda tidak menentukan nilai untuk parameter ini, cmdlet menggunakan langganan saat ini.
Jalankan cmdlet Select-AzureSubscription untuk mengubah langganan saat ini.

```yaml
Type: String
Parameter Sets: ByServerNameWithCertAuth, ByFullyQualifiedServerNameWithCertAuth
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSubscription
Menunjukkan bahwa cmdlet ini menggunakan langganan Azure untuk membuat konteks koneksi.

```yaml
Type: SwitchParameter
Parameter Sets: ByServerNameWithCertAuth, ByFullyQualifiedServerNameWithCertAuth
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

## OUTPUTS

### Microsoft.WindowsAzure.commands.SqlDatabase.Services.Server.IServerDataServiceContext

## CATATAN
* Jika Anda mengautentikasi tanpa menentukan domain, dan jika Anda menggunakan Windows PowerShell 2.0, cmdlet Get-Credential mengembalikan garis miring terbalik ( ) yang disingkapkan dengan nama \\ pengguna, misalnya, \user. Windows PowerShell 3.0 tidak menambahkan garis miring terbalik. Garis miring terbalik ini tidak dikenali oleh parameter *Kredensial* cmdlet **New-AzureSqlDatabaseServerContext.** Untuk menghapusnya, gunakan perintah yang sama seperti berikut:

  `PS C:\\\> $Credential = Get-Credential`
`PS C:\\\> $Credential = New-Object -TypeName 'System.Management.Automation.PSCredential' -ArgumentList $Credential.Username.Replace("\",""),$Credential.Password`

## RELATED LINKS



[Get-AzureSqlDatabase](./Get-AzureSqlDatabase.md)

[New-AzureSqlDatabase](./New-AzureSqlDatabase.md)

[Remove-AzureSqlDatabase](./Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](./Set-AzureSqlDatabase.md)


