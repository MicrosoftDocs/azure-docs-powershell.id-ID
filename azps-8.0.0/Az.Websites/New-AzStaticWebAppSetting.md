---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azstaticwebappsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebAppSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebAppSetting.md
ms.openlocfilehash: 62727f1b6213e98a69ff6cb049fa6d975c922cfe
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146594562"
---
# New-AzStaticWebAppSetting

## SYNOPSIS
Deskripsi untuk Membuat atau memperbarui pengaturan aplikasi situs statis.

## SYNTAX

### CreateExpanded (Default)
```
New-AzStaticWebAppSetting -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AppSetting <Hashtable>] [-Kind <String>] [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CreateViaIdentityExpanded
```
New-AzStaticWebAppSetting -InputObject <IWebsitesIdentity> [-AppSetting <Hashtable>] [-Kind <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Membuat atau memperbarui pengaturan aplikasi situs statis.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui pengaturan aplikasi situs statis
```powershell
New-AzStaticWebAppSetting -ResourceGroupName resourceGroup -Name staticweb01 -AppSetting @{'function01' = 'value01'; 'function02' = 'value02' }
```

```output
Kind Name        Type
---- ----        ----
     appsettings Microsoft.Web/staticSites/config
```

Perintah ini membuat atau memperbarui pengaturan aplikasi situs statis.

### Contoh 2: Membuat atau memperbarui pengaturan aplikasi situs statis menurut alur.
```powershell
Get-AzStaticWebAppSetting -ResourceGroupName resourceGroup -Name staticweb01 | New-AzStaticWebAppSetting -AppSetting @{'function01' = 'value01'; 'function02' = 'value02' }
```

```output
Kind Name        Type
---- ----        ----
     appsettings Microsoft.Web/staticSites/config
```

Perintah ini membuat atau memperbarui pengaturan aplikasi situs statis menurut alur.

## PARAMETERS

### -AppSetting
Pengaturan.

```yaml
Type: System.Collections.Hashtable
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: CreateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Name
Nama situs statis.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
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
Parameter Sets: CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000).

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStringDictionary

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IWebsitesIdentity>`: Parameter Identitas
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
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.
  - `[WebJobName <String>]`: Nama Pekerjaan Web.

## RELATED LINKS
