---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/unregister-azstaticwebappbuilduserprovidedfunctionapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Unregister-AzStaticWebAppBuildUserProvidedFunctionApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Unregister-AzStaticWebAppBuildUserProvidedFunctionApp.md
ms.openlocfilehash: afdc386c90a4256ac5e4f7ff1ed3942a65086768
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140496795"
---
# Unregister-AzStaticWebAppBuildUserProvidedFunctionApp

## SYNOPSIS
Deskripsi untuk Melepaskan aplikasi fungsi yang disediakan pengguna dari build situs statis

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.websites/unregister-azstaticwebappbuilduserprovidedfunctionapp) untuk informasi terkini.

## SYNTAX

### Lepas (Default)
```
Unregister-AzStaticWebAppBuildUserProvidedFunctionApp -EnvironmentName <String> -FunctionAppName <String>
 -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DetachViaIdentity
```
Unregister-AzStaticWebAppBuildUserProvidedFunctionApp -InputObject <IWebsitesIdentity>
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Melepaskan aplikasi fungsi yang disediakan pengguna dari build situs statis

## EXAMPLES

### Contoh 1: Pisahkan pendaftaran aplikasi fungsi yang disediakan pengguna dari build situs statis
```powershell
PS C:\> Unregister-AzStaticWebAppBuildUserProvidedFunctionApp -ResourceGroupName 'resourceGroup' -Name 'staticweb00' -EnvironmentName 'default' -FunctionAppName 'functionAppName01'

```

Perintah ini membatalkan pendaftaran aplikasi fungsi yang disediakan pengguna dari build situs statis.

### Contoh 2: Pisahkan pendaftaran aplikasi fungsi yang disediakan pengguna dari build situs statis menurut pipeline
```powershell
PS C:\> Register-AzStaticWebAppUserProvidedFunctionApp -ResourceGroupName 'resourceGroup' -Name 'staticweb00' -EnvironmentName 'default' -FunctionAppName 'functionAppName01' -FunctionAppResourceId 'functionAppId01' -FunctionAppRegion 'eastus' -IsForced | Unregister-AzStaticWebAppBuildUserProvidedFunctionApp

```

Perintah ini membatalkan pendaftaran aplikasi fungsi yang disediakan pengguna dari situs statis yang dibuat menurut saluran.

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
Parameter Sets: Detach
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionAppName
Nama aplikasi fungsi yang terdaftar dengan build situs statis.

```yaml
Type: System.String
Parameter Sets: Detach
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: DetachViaIdentity
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
Parameter Sets: Detach
Aliases:

Required: True
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
Nama grup sumber daya tempat sumber daya tersebut berada.

```yaml
Type: System.String
Parameter Sets: Detach
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
Parameter Sets: Detach
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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebsitesIdentity>: Parameter Identitas
  - `[Authprovider <String>]`: Penyedia layanan auth untuk pengguna.
  - `[DomainName <String>]`: Nama domain kustom.
  - `[EnvironmentName <String>]`: Pengidentifikasi situs tahapan.
  - `[FunctionAppName <String>]`: Nama aplikasi fungsi yang terdaftar dengan build situs statis.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi tempat Anda berencana membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya tersebut berada.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.

## RELATED LINKS

