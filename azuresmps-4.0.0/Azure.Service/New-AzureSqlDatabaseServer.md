---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
ms.assetid: A0C674FC-A1D8-4068-8CAB-2EE0AECB8E68
online version: ''
schema: 2.0.0
ms.openlocfilehash: 296033d8b7d201c569e878e4826c5c339094e91e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428058"
---
# New-AzureSqlDatabaseServer

## SYNOPSIS
Membuat server Azure SQL Database.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureSqlDatabaseServer -AdministratorLogin <String> -AdministratorLoginPassword <String> -Location <String>
 [-Version <Single>] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureSqlDatabaseServer** membuat instans Server Azure SQL Database di langganan saat ini.

## EXAMPLES

### Contoh 1: Membuat server
```
PS C:\>New-AzureSqlDatabaseServer -Location "East US" -AdministratorLogin "AdminLogin" -AdministratorLoginPassword "AdminPassword"
```

Perintah ini akan membuat server Azure SQL Database versi 11.

### Contoh 2: Membuat server versi 12
```
PS C:\>New-AzureSqlDatabaseServer -Location "East US" -AdministratorLogin "AdminLogin" -AdministratorLoginPassword "AdminPassword" -Version "12.0"
```

Perintah ini membuat server versi 12.

## PARAMETERS

### -AdministratorLogin
Menentukan nama akun administrator untuk server Azure SQL Database baru.

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

### -AdministratorLoginPassword
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

### -Lokasi
Menentukan lokasi pusat data di mana cmdlet ini membuat server.
Untuk informasi selengkapnya, [lihat Azure Regions](https://azure.microsoft.com/regions/) ( https://azure.microsoft.com/regions/#services) di pustaka Azure.

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

### -Versi
Menentukan versi server baru.
Nilai valid adalah: 2.0 dan 12.0.

```yaml
Type: Single
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Model.SqlDatabaseServerContext

## CATATAN

## RELATED LINKS

[Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)

[Buat Server](https://msdn.microsoft.com/en-us/library/azure/dn505699.aspx)

[Operasi untuk Database SQL Azure](https://msdn.microsoft.com/en-us/library/azure/dn505719.aspx)

[Get-AzureSqlDatabaseServer](./Get-AzureSqlDatabaseServer.md)

[Remove-AzureSqlDatabaseServer](./Remove-AzureSqlDatabaseServer.md)

[Set-AzureSqlDatabaseServer](./Set-AzureSqlDatabaseServer.md)


