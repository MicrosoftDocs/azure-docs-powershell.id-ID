---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: FAAF458C-1662-4130-9A16-0514B714D11D
online version: https://docs.microsoft.com/powershell/module/az.sql/set-azsqlserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Set-AzSqlServer.md
ms.openlocfilehash: 840e602520047ba2c4947212c53b7611d361cead
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145722592"
---
# Atur-AzSqlServer

## SYNOPSIS
Memodifikasi properti server SQL Database.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/set-azsqlserver) untuk informasi terbaru.

## SYNTAX

```
Set-AzSqlServer [-ServerName] <String> [-SqlAdministratorPassword <SecureString>] [-Tags <Hashtable>]
 [-ServerVersion <String>] [-AssignIdentity] [-PublicNetworkAccess <String>]
 [-RestrictOutboundNetworkAccess <String>] [-MinimalTlsVersion <String>]
 [-PrimaryUserAssignedIdentityId <String>] [-KeyId <String>] [-FederatedClientId <Guid>]
 [-UserAssignedIdentityId <System.Collections.Generic.List`1[System.String]>] [-IdentityType <String>] [-Force]
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSqlServer** memodifikasi properti server Azure SQL Database.

## EXAMPLES

### Contoh 1: Mereset kata sandi administrator
```powershell
$ServerPassword = "newpassword"
$SecureString = ConvertTo-SecureString $ServerPassword -AsPlainText -Force
Set-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -SqlAdministratorPassword $secureString
```

```output
ResourceGroupName        : ResourceGroup01
ServerName               : Server01
Location                 : Australia East
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Identity                 :
FullyQualifiedDomainName : server01.database.windows.net
```

Perintah ini mengatur ulang kata sandi administrator di AzureSQL Server bernama server01.

### Contoh 2

Memodifikasi properti server SQL Database. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzSqlServer -AssignIdentity -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01'
```

## PARAMETERS

### -AssignIdentity
Buat dan tetapkan identitas Azure Active Directory untuk server ini untuk digunakan dengan layanan manajemen utama seperti Azure KeyVault.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -FederatedClientId
Menentukan ID klien Federasi server saat menggunakan CMK Lintas Penyewa, Jangan atur nilai ini jika Anda tidak berniat menggunakan CMK Lintas Penyewa

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Jenis identitas yang akan ditetapkan ke server. Nilai yang mungkin adalah SystemAsssigned, UserAssigned, 'SystemAssigned,UserAssigned' dan None.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyId
Azure Key Vault URI yang digunakan untuk enkripsi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimalTlsVersion
Versi TLS minimal yang akan diterapkan untuk Sql Server

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: 1.0, 1.1, 1.2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryUserAssignedIdentityId
Id Identitas Terkelola Pengguna (UMI) utama.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
Mengambil bendera, diaktifkan/dinonaktifkan, untuk menentukan apakah akses jaringan publik ke server diizinkan atau tidak.
Ketika dinonaktifkan, hanya koneksi yang dibuat melalui Private Link yang dapat menjangkau server ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -RestrictOutboundNetworkAccess
Ketika diaktifkan, hanya koneksi keluar yang diizinkan oleh aturan firewall keluar yang akan berhasil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Menentukan nama server yang diubah cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerVersion
Menentukan versi di mana cmdlet ini mengubah server. Nilai yang dapat diterima untuk parameter ini adalah: 2.0 dan 12.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlAdministratorPassword
Menentukan kata sandi baru, sebagai **SecureString**, untuk administrator server database. Untuk mendapatkan **SecureString**, gunakan cmdlet Get-Credential. Untuk informasi selengkapnya, ketik `Get-Help
ConvertTo-SecureString`.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
Menentukan kamus tag yang dikaitkan cmdlet ini dengan server. Pasangan kunci-nilai dalam bentuk tabel hash yang ditetapkan sebagai tag di server. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentityId
Daftar identitas yang ditetapkan pengguna.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

## NOTES

## RELATED LINKS

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
