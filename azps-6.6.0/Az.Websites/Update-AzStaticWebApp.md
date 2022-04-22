---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/update-azstaticwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Update-AzStaticWebApp.md
ms.openlocfilehash: 7df5b3833614f43416dd9f21748c50ec1f87e9c3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142894222"
---
# Update-AzStaticWebApp

## SYNOPSIS
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/update-azstaticwebapp) untuk informasi terbaru.

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
Perintah kustom untuk dijalankan selama penyebaran aplikasi api Azure Functions.

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

### -ApiLokasi
Jalur ke kode api dalam repository.

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
Tidak digunakan lagi: Jalur artefak aplikasi setelah pembangun (tidak digunakan lagi untuk OutputLocation)

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
Perintah kustom untuk dijalankan selama penyebaran aplikasi konten statis.

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
Jalur ke kode aplikasi dalam repository.

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

### -Branch
Cabang target di repository.

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
Deskripsi repositori yang baru dibuat.

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
Apakah repositori yang baru dibuat atau tidak adalah repositori privat.
Default ke false (misalnya publik).

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
Nama repositori yang baru dibuat.

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
Pemilik repositori yang baru dibuat.

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
Github Action nama rahasia menimpa.

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
Nama situs statis untuk dibuat atau diperbarui.

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
Jalur output aplikasi setelah pembuatan.

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
Token penyimpanan github pengguna.
Ini digunakan untuk menyetel file alur kerja Tindakan Github dan rahasia API.

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

### -SkipGithubActionWorkflowGeneration
Lewati pembuatan alur kerja Tindakan Github.

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
Negara mengindikasikan apakah lingkungan pementasan diizinkan atau tidak diperbolehkan untuk aplikasi web statis.

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
URL penyimpanan templat.
Repositori yang baru dibuat akan didasarkan pada repositori ini.

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
  - `[Location <String>]`: Lokasi tempat Anda berencana untuk membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.

## RELATED LINKS

