---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/register-azstaticwebappuserprovidedfunctionapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Register-AzStaticWebAppUserProvidedFunctionApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Register-AzStaticWebAppUserProvidedFunctionApp.md
ms.openlocfilehash: fa185df9c071048f2bc2eac99ce24c21db7869e8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142394567"
---
# Register-AzStaticWebAppUserProvidedFunctionApp

## SYNOPSIS
Deskripsi untuk Mendaftarkan aplikasi fungsi yang disediakan pengguna dengan build situs statis

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/register-azstaticwebappuserprovidedfunctionapp) untuk informasi terbaru.

## SYNTAX

### RegisterExpanded1 (Default)
```
Register-AzStaticWebAppUserProvidedFunctionApp -FunctionAppName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-Forced] [-FunctionAppRegion <String>]
 [-FunctionAppResourceId <String>] [-Kind <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### RegisterExpanded
```
Register-AzStaticWebAppUserProvidedFunctionApp -EnvironmentName <String> -FunctionAppName <String>
 -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-Forced] [-FunctionAppRegion <String>]
 [-FunctionAppResourceId <String>] [-Kind <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Mendaftarkan aplikasi fungsi yang disediakan pengguna dengan build situs statis

## EXAMPLES

### Contoh 1: Mendaftarkan aplikasi fungsi yang disediakan pengguna dengan situs statis
```powershell
PS C:\> Register-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName azure-rg-test -Name staticweb-pwsh02 -FunctionAppName funcapp-portal01-test -FunctionAppResourceId '/subscriptions/xxxxxxxxxxxxx/resourcegroups/azure-rg-test/providers/Microsoft.Web/sites/funcapp-portal01-test' -FunctionAppRegion 'Central US'

Kind Name                  Type
---- ----                  ----
     funcapp-portal01-test Microsoft.Web/staticSites/userProvidedFunctionApps
```

Perintah ini mendaftarkan aplikasi fungsi yang disediakan pengguna dengan situs statis.
-FunctionAppRegion adalah kawasan aplikasi fungsi.

### Contoh 2: Daftarkan aplikasi fungsi yang disediakan pengguna dengan build situs statis
```powershell
PS C:\> Register-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName azure-rg-test -Name staticweb-pwsh02 -FunctionAppName functionapp-portal02 -FunctionAppResourceId '/subscriptions/xxxxxxxxx/resourcegroups/azure-rg-test/providers/Microsoft.Web/sites/functionapp-portal02' -FunctionAppRegion 'Central US' -EnvironmentName 5

Kind Name                 Type
---- ----                 ----
     functionapp-portal02 Microsoft.Web/staticSites/builds/userProvidedFunctionApps
```

Perintah ini mendaftarkan aplikasi fungsi yang disediakan pengguna dengan build situs statis.
-FunctionAppRegion adalah kawasan aplikasi fungsi.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -EnvironmentName
Pengidentifikasi situs tahapan.

```yaml
Type: System.String
Parameter Sets: RegisterExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dipaksa
Tentukan \<code\>true\</code\> untuk memaksa pembaruan konfigurasi auth pada aplikasi fungsi meskipun penyedia AzureStaticWebApps sudah dikonfigurasi pada aplikasi fungsi.
Defaultnya adalah \<code\>false\</code\>.

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

### -FunctionAppName
Nama aplikasi fungsi untuk mendaftar dengan build situs statis.

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

### -FunctionAppRegion
Wilayah aplikasi fungsi yang terdaftar di situs statis

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

### -FunctionAppResourceId
Id sumber daya aplikasi fungsi yang terdaftar di situs statis

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

### -Jenis
Jenis sumber daya.

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

### -Nama
Nama situs statis.

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

### -NoWait
Jalankan perintah secara asinkron

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
Nama grup sumber daya tempat sumber daya berada.

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
ID langganan Azure Anda.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).

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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteUserProvidedFunctionAppArmResource

## CATATAN

ALIAS

## RELATED LINKS

