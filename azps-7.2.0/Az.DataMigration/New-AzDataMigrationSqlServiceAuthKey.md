---
external help file: ''
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/new-azdatamigrationsqlserviceauthkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationSqlServiceAuthKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/New-AzDataMigrationSqlServiceAuthKey.md
ms.openlocfilehash: fe399bbacbe0c5d043a20dbfa3564fcb0291182d
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138316060"
---
# New-AzDataMigrationSqlServiceAuthKey

## SYNOPSIS
Meregenerasi kumpulan Baru Kunci Autentikasi untuk Runtime Integrasi Yang Dihosting Sendiri.

## SYNTAX

```
New-AzDataMigrationSqlServiceAuthKey -ResourceGroupName <String> -SqlMigrationServiceName <String>
 [-SubscriptionId <String>] [-AuthKey1 <String>] [-AuthKey2 <String>] [-KeyName <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kumpulan Baru Kunci Autentikasi untuk Runtime Integrasi Yang Dihosting Sendiri.

## EXAMPLES

### Contoh 1: Regenerasi AuthKeys untuk Layanan Migrasi Sql
```powershell
PS C:\> New-AzDataMigrationSqlServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService" -KeyName AuthKey2

AuthKey1 AuthKey2                                                   KeyName
-------- --------                                                   -------
         IR@abcd7-efgh8-jklmn9-opqr10@mysqlms@eastus@stuv2/wxyz1=
```

Perintah ini meregenerasi AuthKeys untuk Layanan Migrasi Sql tertentu.
Di sini, kami telah meregenerasi AuthKey2.

## PARAMETERS

### -AuthKey1
Tombol autentikasi pertama.

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
Tombol autentikasi kedua.

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
Nama tombol autentikasi untuk dihasilkan.

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
Mengembalikan true saat perintah berhasil

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
Nama grup sumber daya yang berisi sumber daya tersebut.
Anda dapat memperoleh nilai ini dari API Azure Resource Manager atau portal.

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
Nama layanan SQL migrasi.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IRegenAuthKeys

## CATATAN

ALIAS

## RELATED LINKS

