---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azstaticwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzStaticWebApp.md
ms.openlocfilehash: f87a35df8aa113d915f32639e71c4b396ca85d31
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143268713"
---
# Get-AzStaticWebApp

## SYNOPSIS
Deskripsi untuk Mendapatkan detail situs statis.

## SYNTAX

### Daftar (Default)
```
Get-AzStaticWebApp [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzStaticWebApp -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzStaticWebApp -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzStaticWebApp -InputObject <IWebsitesIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Mendapatkan detail situs statis.

## EXAMPLES

### Contoh 1: Mencantumkan semua aplikasi web statis di bawah langganan
```powershell
Get-AzStaticWebApp
```

```output
Kind Location   Name               Type
---- --------   ----               ----
     Central US staticweb-portal04 Microsoft.Web/staticSites
     East US 2  staticweb-portal02 Microsoft.Web/staticSites
```

Perintah ini mencantumkan semua aplikasi web statis di bawah langganan.

### Contoh 2: Mencantumkan semua aplikasi web statis di bawah grup sumber daya
```powershell
Get-AzStaticWebApp -ResourceGroupName azure-rg-test
```

```output
Kind Location   Name               Type
---- --------   ----               ----
     Central US staticweb-portal04 Microsoft.Web/staticSites
     East US 2  staticweb-portal02 Microsoft.Web/staticSites
```

Perintah ini mencantumkan semua aplikasi web statis di bawah grup sumber daya.

### Contoh 3: Dapatkan aplikasi web satic menurut nama
```powershell
Get-AzStaticWebApp -ResourceGroupName azure-rg-test -Name staticweb-portal04
```

```output
Kind Location   Name               Type
---- --------   ----               ----
     Central US staticweb-portal04 Microsoft.Web/staticSites
```

Perintah ini mendapatkan aplikasi web satic berdasarkan nama.

### Contoh 4: Dapatkan aplikasi web satic menurut pipline
```powershell
New-AzStaticWebApp -ResourceGroupName azure-rg-test -Name staticweb-pwsh01 -Location eastus2 -RepositoryUrl 'https://github.com/username/RepoName' -RepositoryToken 'repoToken123' -Branch 'master' -AppLocation 'Client' -ApiLocation 'Api' -OutputLocation 'wwwroot' -SkuName 'free' -SkuTier 'free'  | Get-AzStaticWebApp -InputObejct
```

```output
Kind Location   Name               Type
---- --------   ----               ----
     Central US staticweb-portal04 Microsoft.Web/staticSites
```

Perintah ini mendapatkan aplikasi web satic menurut pipline.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
Nama situs statis.

```yaml
Type: System.String
Parameter Sets: Get
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
Parameter Sets: Get, List1
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
Type: System.String[]
Parameter Sets: List, Get, List1
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteArmResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebsitesIdentity>: Parameter Identitas
  - `[Authprovider <String>]`: Penyedia auth untuk pengguna.
  - `[DomainName <String>]`: Nama domain kustom.
  - `[EnvironmentName <String>]`: Pengidentifikasi situs tahapan.
  - `[FunctionAppName <String>]`: Nama aplikasi fungsi yang terdaftar dengan build situs statis.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobHistoryId <String>]`: ID Riwayat.
  - `[Location <String>]`: Lokasi tempat Anda berencana untuk membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[Slot <String>]`: Nama slot penyebaran. Jika slot tidak ditentukan, API menghapus penyebaran untuk slot produksi.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.
  - `[WebJobName <String>]`: Nama Web Job.

## RELATED LINKS
