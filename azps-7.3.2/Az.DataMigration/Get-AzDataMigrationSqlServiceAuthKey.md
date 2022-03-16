---
external help file: Az.DataMigration-help.xml
Module Name: Az.DataMigration
online version: https://docs.microsoft.com/powershell/module/az.datamigration/get-azdatamigrationsqlserviceauthkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceAuthKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataMigration/DataMigration/help/Get-AzDataMigrationSqlServiceAuthKey.md
ms.openlocfilehash: 0e2de3e8b2e2374a3b051c0e082133bd2d5f6a81
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140001214"
---
# Get-AzDataMigrationSqlServiceAuthKey

## SYNOPSIS
Ambil Daftar Tombol Autentikasi untuk Runtime Integrasi Yang Dihosting Sendiri.

## SYNTAX

```
Get-AzDataMigrationSqlServiceAuthKey -ResourceGroupName <String> -SqlMigrationServiceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Ambil Daftar Tombol Autentikasi untuk Runtime Integrasi Yang Dihosting Sendiri.

## EXAMPLES

### Contoh 1: Dapatkan AuthKeys untuk Layanan Migrasi Sql tertentu
```powershell
PS C:\> Get-AzDataMigrationSqlServiceAuthKey -ResourceGroupName "MyResourceGroup" -SqlMigrationServiceName "MySqlMigrationService"

AuthKey1                                                 AuthKey2
--------                                                 --------
IR@abcd1-efgh2-jklmn3-opqr4@mysqlms@eastus@stuv5/wxyz6=  IR@abcd6-efgh5-jklmn4-opqr3@mysqlms@eastus@stuv2/wxyz1=
```

Perintah ini mendapatkan AuthKeys untuk Layanan Migrasi Sql tertentu.

## PARAMETERS

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
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.DataMigration.Models.Api20211030Preview.IAuthenticationKeys

## CATATAN

ALIAS

## RELATED LINKS
