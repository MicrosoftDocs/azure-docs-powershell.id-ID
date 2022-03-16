---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/update-azstaticwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebApp.md
ms.openlocfilehash: a52e95e3889e54e954e3d081b9bf6827c620da6b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139997842"
---
# Update-AzStaticWebApp

## SYNOPSIS
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzStaticWebApp -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AllowConfigFileUpdate] [-ApiBuildCommand <String>] [-ApiLocation <String>] [-AppArtifactLocation <String>]
 [-AppBuildCommand <String>] [-AppLocation <String>] [-Branch <String>] [-ForkRepositoryDescription <String>]
 [-ForkRepositoryIsPrivate] [-ForkRepositoryName <String>] [-ForkRepositoryOwner <String>]
 [-GithubActionSecretNameOverride <String>] [-Kind <String>] [-OutputLocation <String>]
 [-RepositoryToken <String>] [-RepositoryUrl <String>] [-SkipGithubActionWorkflowGeneration]
 [-StagingEnvironmentPolicy <StagingEnvironmentPolicy>] [-TemplateRepositoryUrl <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzStaticWebApp -InputObject <IWebsitesIdentity> [-AllowConfigFileUpdate] [-ApiBuildCommand <String>]
 [-ApiLocation <String>] [-AppArtifactLocation <String>] [-AppBuildCommand <String>] [-AppLocation <String>]
 [-Branch <String>] [-ForkRepositoryDescription <String>] [-ForkRepositoryIsPrivate]
 [-ForkRepositoryName <String>] [-ForkRepositoryOwner <String>] [-GithubActionSecretNameOverride <String>]
 [-Kind <String>] [-OutputLocation <String>] [-RepositoryToken <String>] [-RepositoryUrl <String>]
 [-SkipGithubActionWorkflowGeneration] [-StagingEnvironmentPolicy <StagingEnvironmentPolicy>]
 [-TemplateRepositoryUrl <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## EXAMPLES

### Contoh 1: Memperbarui situs statis
```powershell
PS C:\> Update-AzStaticWebApp -ResourceGroupName 'resourceGroup' -Name 'staticweb00'

Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb00 Microsoft.Web/staticSites
```

Perintah ini memperbarui situs statis.

### Contoh 2: Memperbarui situs statis menurut saluran
```powershell
PS C:\> Get-AzStaticWebApp -ResourceGroupName 'resourceGroup' -Name 'staticweb00' | Update-AzStaticWebApp

Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb00 Microsoft.Web/staticSites
```

Perintah ini memperbarui situs statis menurut saluran.

## PARAMETERS

### -AllowConfigFileUpdate
\<code\>false\</code\> jika file konfigurasi dikunci untuk aplikasi web statis ini; jika tidak, \<code\>true\</code\>.

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

### -ApiBuildCommand
Perintah kustom untuk dijalankan selama penggunaan aplikasi API Fungsi Azure.

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

### -ApiLocation
Jalur ke kode api di dalam tempat penyimpanan.

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

### -AppArtifactLocation
Ditolak: Jalur artifak aplikasi setelah membangun (disusingkat agar dapat digunakan untuk OutputLocation)

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

### -AppBuildCommand
Perintah kustom untuk dijalankan selama penggunaan aplikasi konten statis.

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

### -AppLocation
Jalur ke kode aplikasi di dalam tempat penyimpanan.

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

### -Cabang
Cabang target di repositori.

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

### -ForkRepositoryDescription
Deskripsi penyimpanan yang baru dihasilkan.

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

### -ForkRepositoryIsPrivate
Apakah penyimpanan yang baru dihasilkan adalah penyimpanan pribadi.
Default untuk false (mis. publik).

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

### -ForkRepositoryName
Nama penyimpanan yang baru dihasilkan.

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

### -ForkRepositoryOwner
Pemilik tempat penyimpanan yang baru dihasilkan.

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

### -GithubActionSecretNameOverride
Github Action secret name override.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Kind
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
Nama situs statis untuk membuat atau memperbarui.

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

### -OutputLocation
Jalur output aplikasi setelah membuat.

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

### -RepositoryToken
Token repositori github pengguna.
This is used to setup the Github Actions workflow file and API secret.

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

### -RepositoryUrl
URL untuk penyimpanan situs statis.

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

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya tersebut berada.

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

### -SkipGithubActionWorkflowGeneration
Skip Github Action workflow generation.

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

### -StagingEnvironmentPolicy
Status mengindikasikan apakah pengaturan lingkungan diperbolehkan atau tidak diperbolehkan untuk aplikasi web statis.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Support.StagingEnvironmentPolicy
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

### -TemplateRepositoryUrl
URL tempat penyimpanan templat.
Penyimpanan yang baru dihasilkan akan didasarkan pada penyimpanan ini.

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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteArmResource

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

