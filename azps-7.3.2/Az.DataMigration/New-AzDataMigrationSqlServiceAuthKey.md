---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationsqlserviceauthkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationSqlServiceAuthKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationSqlServiceAuthKey.md
ms.openlocfilehash: 9d03d1dfa76192b13b8c79e7b864ee290aff38d3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141894662"
---
# New-AzDataMigrationSqlServiceAuthKey

## SYNOPSIS
Meregenerasi sekumpulan Kunci Autentikasi baru untuk Integration Runtime yang Dihosting Sendiri.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datamigration/new-azdatamigrationsqlserviceauthkey) untuk informasi terbaru.

## SYNTAX

```
New-AzDataMigrationSqlServiceAuthKey -ResourceGroupName <String> -SqlMigrationServiceName <String>
 [-SubscriptionId <String>] [-AuthKey1 <String>] [-AuthKey2 <String>] [-KeyName <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi sekumpulan Kunci Autentikasi baru untuk Integration Runtime yang Dihosting Sendiri.

## EXAMPLES

### Contoh 1: Regenerasi AuthKeys untuk Layanan Migrasi Sql tertentu
```powershell
PS C:\> New-AzDataMigrationSqlServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService" -KeyName AuthKey2

AuthKey1 AuthKey2                                                   KeyName
-------- --------                                                   -------
         IR@abcd7-efgh8-jklmn9-opqr10@mysqlms@eastus@stuv2/wxyz1=
```

Perintah ini meregenerasi AuthKeys untuk Layanan Migrasi Sql tertentu.
Di sini kita telah meregenerasi AuthKey2.

## PARAMETERS

### -AuthKey1
Kunci autentikasi pertama.

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

### -AuthKey2
Kunci autentikasi kedua.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyName
Nama kunci autentikasi yang akan dihasilkan.

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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya yang berisi sumber daya.
Anda dapat memperoleh nilai ini dari API azure Resource Manager atau portal.

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

### -SqlMigrationServiceName
Nama Layanan Migrasi SQL.

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

### -SubscriptionId
ID Langganan yang mengidentifikasi langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IRegenAuthKeys

## CATATAN

ALIAS

## RELATED LINKS
