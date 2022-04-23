---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azstaticwebappbuildfunctionappsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebAppBuildFunctionAppSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebAppBuildFunctionAppSetting.md
ms.openlocfilehash: bce8af85d1cfde119642fed2f1811f6d640633c2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143352611"
---
# New-AzStaticWebAppBuildFunctionAppSetting

## SYNOPSIS
Deskripsi untuk Membuat atau memperbarui pengaturan aplikasi fungsi build situs statis.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/new-azstaticwebappbuildfunctionappsetting) untuk informasi terbaru.

## SYNTAX

### CreateExpanded (Default)
```
New-AzStaticWebAppBuildFunctionAppSetting -EnvironmentName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-AppSetting <Hashtable>] [-Kind <String>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### CreateViaIdentityExpanded
```
New-AzStaticWebAppBuildFunctionAppSetting -InputObject <IWebsitesIdentity> [-AppSetting <Hashtable>]
 [-Kind <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Membuat atau memperbarui pengaturan aplikasi fungsi build situs statis.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui pengaturan aplikasi build situs statis
```powershell
PS C:\> New-AzStaticWebAppBuildFunctionAppSetting -ResourceGroupName azure-rg-test -Name staticweb-pwsh01 -EnvironmentName 'default' -AppSetting @{'functionapp01' = 'value01'; 'functionapp02' = 'value02' }

Kind Name        Type
---- ----        ----
     appsettings Microsoft.Web/staticSites/builds/config
```

Perintah ini membuat atau memperbarui pengaturan aplikasi build situs statis.

### Contoh 2: Membuat atau memperbarui pengaturan aplikasi build situs statis menurut saluran
```powershell
PS C:\> Get-AzStaticWebAppBuildFunctionAppSetting -ResourceGroupName resourceGroup -Name staticweb01 -EnvironmentName 'default' | New-AzStaticWebAppBuildFunctionAppSetting  -AppSetting @{'buildsetting1' = 'someval'; 'buildsetting2' = 'someval2' }

Kind Name        Type
---- ----        ----
     appsettings Microsoft.Web/staticSites/builds/config
```

Perintah ini membuat atau memperbarui pengaturan aplikasi build situs statis menurut saluran.

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

### -EnvironmentName
Pengidentifikasi situs tahapan.

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

### -Nama
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
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).

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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStringDictionary

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
  - `[Location <String>]`: Lokasi tempat Anda berencana untuk membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.

## RELATED LINKS

