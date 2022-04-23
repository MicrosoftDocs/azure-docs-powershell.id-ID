---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/update-azstaticwebappuser
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebAppUser.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebAppUser.md
ms.openlocfilehash: 82ccbba050becf23ed5a00774ea0812425ac1ccc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143055469"
---
# Update-AzStaticWebAppUser

## SYNOPSIS
Deskripsi untuk Memperbarui entri pengguna dengan peran yang tercantum

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzStaticWebAppUser -AuthProvider <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -UserId <String> [-Kind <String>] [-Role <String>] [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzStaticWebAppUser -InputObject <IWebsitesIdentity> [-Kind <String>] [-Role <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Memperbarui entri pengguna dengan peran yang tercantum

## EXAMPLES

### Contoh 1: Memperbarui entri pengguna dengan peran yang tercantum
```powershell
Update-AzStaticWebAppUser -ResourceGroupName azure-rg-test -Name staticweb-portal01 -Authprovider 'github' -Userid 'fa4eba85fa9f4a42b5300dc4c7bb45aa' -Role 'contributor'
```

```output
Kind Name                             Type
---- ----                             ----
     fa4eba85fa9f4a42b5300dc4c7bb45aa Microsoft.Web/staticSites/users
```

Perintah ini memperbarui entri pengguna dengan peran yang tercantum.

### Contoh 2: Memperbarui entri pengguna dengan peran yang tercantum menurut saluran
```powershell
Get-AzStaticWebAppUser -ResourceGroupName azure-rg-test -Name staticweb-portal01 -Authprovider 'all'  | Update-AzStaticWebAppUser -Role 'contributor'
```

```output
Kind Name                             Type
---- ----                             ----
     fa4eba85fa9f4a42b5300dc4c7bb45aa Microsoft.Web/staticSites/users
     8bcf2cef5f3c4c8e9a58386d62bba7c3 Microsoft.Web/staticSites/users
```

Perintah ini memperbarui entri pengguna dengan peran yang tercantum menurut saluran.

## PARAMETERS

### -AuthProvider
Penyedia auth untuk pengguna ini.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
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
Parameter Sets: UpdateViaIdentityExpanded
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
Parameter Sets: UpdateExpanded
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
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Peran
Peran untuk pengguna situs statis, dalam format string bentuk bebas

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

### -SubscriptionId
ID langganan Azure Anda.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserId
Id pengguna pengguna.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteUserArmResource

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
