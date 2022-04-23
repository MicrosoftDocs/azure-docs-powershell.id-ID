---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
ms.assetid: 7039528F-42AE-45DB-BF81-FE5003F8AEE2
online version: https://docs.microsoft.com/powershell/module/az.sql/new-azsqlserver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlServer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/New-AzSqlServer.md
ms.openlocfilehash: afefa53cda73d1fadbdedf71b56240ebd3511f48
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143325665"
---
# New-AzSqlServer

## SYNOPSIS
Membuat server SQL Database.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.sql/new-azsqlserver) untuk informasi terbaru.

## SYNTAX

```
New-AzSqlServer -ServerName <String> [-SqlAdministratorCredentials <PSCredential>] -Location <String>
 [-Tags <Hashtable>] [-ServerVersion <String>] [-AssignIdentity] [-PublicNetworkAccess <String>]
 [-MinimalTlsVersion <String>] [-RestrictOutboundNetworkAccess <String>] [-AsJob] 
 [-EnableActiveDirectoryOnlyAuthentication] [-ExternalAdminName <String>] [-ExternalAdminSID <Guid>] 
 [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] 
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSqlServer** membuat server Azure SQL Database.

## EXAMPLES

### Contoh 1: Membuat server Azure SQL Database baru
```
PS C:\>New-AzSqlServer -ResourceGroupName "ResourceGroup01" -Location "Central US" -ServerName "server01" -ServerVersion "12.0" -SqlAdministratorCredentials (Get-Credential)
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
```

Perintah ini membuat server Azure SQL Database versi 12.

### Contoh 2: Membuat server Azure SQL Database baru dengan Administrator External(Azure Active Directory), Azure Active Directory Hanya Autentikasi dan tanpa SqlAdministratorCredentials
```
PS C:\>New-AzSqlServer -ResourceGroupName "ResourceGroup01" -Location "Central US" -ServerName "server01" -ServerVersion "12.0" -ExternalAdminName DummyLogin -EnableActiveDirectoryOnlyAuthentication
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : adminLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Administrators           :

PS C:\>$val = Get-AzSqlServer -ResourceGroupName "ResourceGroup01" -ServerName "server01" -ExpandActiveDirectoryAdministrator
ResourceGroupName        : resourcegroup01
ServerName               : server01
Location                 : Central US
SqlAdministratorLogin    : randomLogin
SqlAdministratorPassword :
ServerVersion            : 12.0
Tags                     :
Administrators           : Microsoft.Azure.Management.Sql.Models.ServerExternalAdministrator

PS C:\>$val.Administrators
AdministratorType         : ActiveDirectory
PrincipalType             : Group
Login                     : DummyLogin
Sid                       : df7667b8-f9fd-4029-a0e3-b43c75ce9538
TenantId                  : f553829b-6d84-481b-86a9-42db57c1dc73
AzureADOnlyAuthentication : True
```

Perintah ini membuat server Azure SQL Database versi 12 dengan properti administrator eksternal dan autentikasi azure active directory saja yang diaktifkan.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -AssignIdentity
Buat dan tetapkan identitas Azure Active Directory untuk server ini untuk digunakan dengan layanan manajemen kunci seperti Azure KeyVault.

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

### -EnableActiveDirectoryOnlyAuthentication
Aktifkan Autentikasi Direktori Aktif Saja pada server.

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

### -ExternalAdminName
Menentukan nama tampilan pengguna, grup, atau aplikasi yang merupakan administrator Azure Active Directory untuk server. Nama tampilan ini harus ada di direktori aktif yang terkait dengan langganan saat ini.

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

### -ExternalAdminsID
Menentukan ID objek pengguna, grup, atau aplikasi yang merupakan administrator Azure Active Directory.

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

### -Lokasi
Menentukan lokasi pusat data tempat cmdlet ini membuat server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimalTlsVersion
Versi TLS minimal yang diterapkan untuk Sql Server

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

### -PublicNetworkAccess
Mengambil bendera, diaktifkan/dinonaktifkan, untuk menentukan apakah akses jaringan publik ke server diperbolehkan atau tidak.
Ketika dinonaktifkan, hanya koneksi yang dibuat melalui Tautan Privat yang dapat menjangkau server ini.

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

### -RestrictOutboundNetworkAccess
Saat diaktifkan, hanya koneksi keluar yang diperbolehkan oleh aturan firewall keluar yang akan berhasil.

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
Menentukan nama grup sumber daya tempat cmdlet ini menetapkan server.

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
Menentukan nama server baru.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerVersion
Menentukan versi server baru. Nilai yang dapat diterima untuk parameter ini adalah: 2,0 dan 12,0.
Tentukan 2.0 untuk membuat server versi 11, atau 12.0 untuk membuat server versi 12.

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

### -SqlAdministratorCredentials
Menentukan kredensial administrator server SQL Database untuk server baru. Untuk mendapatkan objek **PSCredential** , gunakan cmdlet Get-Credential. Untuk informasi selengkapnya, ketik .`Get-Help
Get-Credential`

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

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

### -UserAssignedIdentityId
Daftar identitas yang ditetapkan pengguna.

```yaml
Type: System.Collections.Generic.List
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Tipe identitas yang akan ditetapkan ke server. Nilai yang memungkinkan adalah SystemAsssigned, UserAssigned, 'SystemAssigned,UserAssigned' dan None.

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

### -Tags
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.Server.Model.AzureSqlServerModel

## NOTES

## RELATED LINKS

[Get-AzSqlServer](./Get-AzSqlServer.md)

[Remove-AzSqlServer](./Remove-AzSqlServer.md)

[Set-AzSqlServer](./Set-AzSqlServer.md)

[New-AzSqlServerFirewallRule](./New-AzSqlServerFirewallRule.md)

[Dokumentasi SQL Database](https://docs.microsoft.com/azure/sql-database/)
