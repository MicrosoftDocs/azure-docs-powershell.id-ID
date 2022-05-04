---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azstaticwebappuserprovidedfunctionapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebAppUserProvidedFunctionApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebAppUserProvidedFunctionApp.md
ms.openlocfilehash: 196181f0db45aa0b4d3fff85dec7be2f355f3f7a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144741106"
---
# Get-AzStaticWebAppUserProvidedFunctionApp

## SYNOPSIS
Deskripsi untuk Mendapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.websites/get-azstaticwebappuserprovidedfunctionapp) untuk informasi terbaru.

## SYNTAX

### List1 (Default)
```
Get-AzStaticWebAppUserProvidedFunctionApp -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzStaticWebAppUserProvidedFunctionApp -EnvironmentName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzStaticWebAppUserProvidedFunctionApp -EnvironmentName <String> -FunctionAppName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar2
```
Get-AzStaticWebAppUserProvidedFunctionApp -FunctionAppName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStaticWebAppUserProvidedFunctionApp -InputObject <IWebsitesIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Mendapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis

## EXAMPLES

### Contoh 1: Mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar di situs statis
```powershell
Get-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName resourceGroup -Name staticweb00
```

```output
Kind Name               Type
---- ----               ----
     functionApp-5enjko Microsoft.Web/staticSites/userProvidedFunctionApps
```

Perintah ini mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar di situs statis

### Contoh 2: Mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis
```powershell
Get-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName resourceGroup -Name staticweb00 -EnvironmentName 'default'
```

```output
Kind Name               Type
---- ----               ----
     functionApp-5enjko Microsoft.Web/staticSites/builds/userProvidedFunctionApps
```

Perintah ini mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis.

### Contoh 3: Mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar
```powershell
Get-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName resourceGroup -Name staticweb00 -FunctionAppName $env.functionAppName01
```

```output
Kind Name               Type
---- ----               ----
     functionApp-5enjko Microsoft.Web/staticSites/builds/userProvidedFunctionApps
```

Perintah ini mencantumkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar.

### Contoh 4: Mendapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis
```powershell
Get-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName resourceGroup -Name staticweb00 -EnvironmentName 'default' -FunctionAppName $env.functionAppName01
```

```output
Kind Name               Type
---- ----               ----
     functionApp-5enjko Microsoft.Web/staticSites/builds/userProvidedFunctionApps
```

Perintah ini mendapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis.

### Contoh 5: Dapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis berdasarkan alur
```powershell
Register-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName lucas-rg-test -Name staticweb-pwsh02 -FunctionAppName functionapp-portal02 -FunctionAppResourceId '/subscriptions/xxxxxx-xx-xxx-xxxx-xxxxx/resourcegroups/xxx-xx-xxxx/providers/Microsoft.Web/sites/functionapp-portal02' -FunctionAppRegion 'Central US' -EnvironmentName 5 | Get-AzStaticWebAppUserProvidedFunctionApp
```

```output
Kind Name               Type
---- ----               ----
     functionApp-5enjko Microsoft.Web/staticSites/builds/userProvidedFunctionApps
```

Perintah ini mendapatkan detail aplikasi fungsi yang disediakan pengguna yang terdaftar dengan build situs statis berdasarkan alur.

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

### -EnvironmentName
Pengidentifikasi situs tahapan.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionAppName
Nama aplikasi fungsi yang terdaftar di build situs statis.

```yaml
Type: System.String
Parameter Sets: Get, List2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama situs statis.

```yaml
Type: System.String
Parameter Sets: List1, List, Get, List2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya berada.

```yaml
Type: System.String
Parameter Sets: List1, List, Get, List2
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000).

```yaml
Type: System.String[]
Parameter Sets: List1, List, Get, List2
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteUserProvidedFunctionAppArmResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebsitesIdentity>: Parameter Identitas
  - `[Authprovider <String>]`: Penyedia autentikasi untuk pengguna.
  - `[DomainName <String>]`: Nama domain kustom.
  - `[EnvironmentName <String>]`: Pengidentifikasi situs tahapan.
  - `[FunctionAppName <String>]`: Nama aplikasi fungsi yang terdaftar dengan build situs statis.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobHistoryId <String>]`: ID Riwayat.
  - `[Location <String>]`: Lokasi tempat Anda berencana membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[Slot <String>]`: Nama slot penyebaran. Jika slot tidak ditentukan, API akan menghapus penyebaran untuk slot produksi.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000).
  - `[Userid <String>]`: Id pengguna pengguna.
  - `[WebJobName <String>]`: Nama Pekerjaan Web.

## RELATED LINKS
