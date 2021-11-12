---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: B5A2F2A8-5D20-47E4-AFC5-44F687142A08
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7b3cd85e7f5057f0a31b3edce6e12c074069aa8e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422053"
---
# Set-AzureSqlDatabaseServer

## SYNOPSIS
Mengubah properti server Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureSqlDatabaseServer -ServerName <String> -AdminPassword <String> [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureSqlDatabaseServer** mengubah properti instans server Azure SQL Database tertentu.
Dalam rilis saat ini, Anda hanya dapat memperbarui kata sandi akun administrator untuk server.

## EXAMPLES

### Contoh 1: Mengubah kata sandi untuk server
```
PS C:\>Set-AzureSqlDatabaseServer -ServerName "lpqd0zbr8y" -AdminPassword "NewPassword"
```

Perintah ini mengubah kata sandi akun administrator untuk server Azure SQL Database bernama lpqd0zbr8y.

## PARAMETERS

### -AdminPassword
Menentukan kata sandi akun administrator untuk Azure SQL Database server.
Anda harus menentukan kata sandi yang kuat.
Untuk informasi selengkapnya, lihat [Kata Sandi Yang](https://go.microsoft.com/fwlink/p/?LinkId=154152) Kuat ( di Microsoft Developer https://go.microsoft.com/fwlink/p/?LinkId=154152) Network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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
Menentukan nama server yang akan dimodifikasi cmdlet ini.
Tentukan nama server, bukan nama DNS yang sepenuhnya memenuhi syarat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
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
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## OUTPUTS

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Operasi untuk Database Azure SQL](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseServer](./Get-AzureSqlDatabaseServer.md)

[New-AzureSqlDatabaseServer](./New-AzureSqlDatabaseServer.md)

[Remove-AzureSqlDatabaseServer](./Remove-AzureSqlDatabaseServer.md)


