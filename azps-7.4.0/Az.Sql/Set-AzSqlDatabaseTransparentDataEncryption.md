---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 01744DBD-1991-45EF-AA92-FD471F7E7551
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqldatabasetransparentdataencryption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseTransparentDataEncryption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlDatabaseTransparentDataEncryption.md
ms.openlocfilehash: f46f8026d70b494e0e030b93635cd3b9ce9422d4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142428337"
---
# Set-AzSqlDatabaseTransparentDataEncryption

## SYNOPSIS
Mengubah properti TDE untuk database.

## SYNTAX

```
Set-AzSqlDatabaseTransparentDataEncryption [-State] <TransparentDataEncryptionStateType> [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlDatabaseTransparentDataEncryption** mengubah properti Transparent Data Encryption (TDE) database Azure SQL.
Untuk informasi selengkapnya, lihat Enkripsi Data Transparan dengan Azure SQL Databasehttps://msdn.microsoft.com/library/dn948096 (https://msdn.microsoft.com/library/dn948096) di Pustaka Jaringan Pengembang Microsoft.
Cmdlet ini juga didukung oleh layanan SQL Server Stretch Database di Azure.

## EXAMPLES

### Contoh 1: Mengaktifkan TDE untuk database
```powershell
Set-AzSqlDatabaseTransparentDataEncryption -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "Database01" -State Enabled
```

```output
ResourceGroupName             ServerName                    DatabaseName                                          State
-----------------             ----------                    ------------                                          -----
ResourceGroup01               Server01                      Database01                                            Enabled
```

Perintah ini mengaktifkan TDE untuk database bernama Database01 di server bernama Server01.

## PARAMETERS

### -DatabaseName
Menentukan nama database yang diubah cmdlet ini.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat database ditetapkan.

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
Menentukan nama server yang menghosting database.

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

### -Negara Bagian
Menentukan nilai properti TDE.
Nilai yang dapat diterima untuk parameter ini adalah:
- Diaktifkan 
- Tamu penyandang cacat

```yaml
Type: Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.TransparentDataEncryptionStateType
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: True
Position: 3
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.TransparentDataEncryptionStateType

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.AzureSqlDatabaseTransparentDataEncryptionModel

## CATATAN

## RELATED LINKS

[Get-AzSqlDatabaseTransparentDataEncryption](./Get-AzSqlDatabaseTransparentDataEncryption.md)

[Get-AzSqlDatabaseTransparentDataEncryptionActivity](./Get-AzSqlDatabaseTransparentDataEncryptionActivity.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)


