---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azstaticwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebApp.md
ms.openlocfilehash: b5c1ae842473a90f929b3cf418f721afed032882
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434748"
---
# New-AzStaticWebApp

## SYNOPSIS
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## SYNTAX

```
New-AzStaticWebApp -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] -Location <String>
 [-AllowConfigFileUpdate] [-ApiBuildCommand <String>] [-ApiLocation <String>] [-AppArtifactLocation <String>]
 [-AppBuildCommand <String>] [-AppLocation <String>] [-Branch <String>] [-Capacity <Int32>]
 [-GithubActionSecretNameOverride <String>] [-IdentityType <ManagedServiceIdentityType>]
 [-IdentityUserAssignedIdentity <Hashtable>] [-Kind <String>] [-OutputLocation <String>]
 [-RepositoryToken <String>] [-RepositoryUrl <String>] [-SkipGithubActionWorkflowGeneration]
 [-SkuName <String>] [-StagingEnvironmentPolicy <StagingEnvironmentPolicy>] [-Tag <Hashtable>]
 [-ForkRepositoryDescription <String>] [-ForkRepositoryIsPrivate] [-ForkRepositoryOwner <String>]
 [-ForkRepositoryName <String>] [-TemplateRepositoryUrl <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada
```powershell
New-AzStaticWebApp -ResourceGroupName 'azure-rg-test' -Name 'staticweb-45asde' -Location 'Central US' -RepositoryUrl 'https://github.com/LucasYao93/blazor-starter' -RepositoryToken 'githubAccessToken' -Branch 'branch02' -AppLocation 'Client' -ApiLocation 'Api' -OutputLocation 'wwwroot' -SkuName 'Standard'
```

```output
Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb-45asde Microsoft.Web/staticSites
```

Perintah ini membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

### Contoh 2: Membuat situs statis baru dalam grup sumber daya yang sudah ada melalui penyimpanan templat tertentu
```powershell
New-AzStaticWebApp -ResourceGroupName 'azure-rg-test' -Name staticweb-pwsh01 -Location "Central US" -RepositoryToken  'xxxxxxxxxxxxxxxxx' -TemplateRepositoryUrl 'https://github.com/staticwebdev/blazor-starter' -ForkRepositoryDescription "Test template repository function of the azure static web." -ForkRepositoryName "test-blazor-starter" -ForkRepositoryOwner 'LucasYao93' -Branch 'main' -AppLocation 'Client' -ApiLocation 'Api' -OutputLocation 'wwwroot' -SkuName 'Standard'
```

```output
Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb-pwsh01 Microsoft.Web/staticSites
```

Perintah ini membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada melalui penyimpanan templat tertentu.

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

### -Kapasitas
Jumlah instans saat ini yang ditetapkan ke sumber daya.

```yaml
Type: System.Int32
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

### -IdentityType
Jenis identitas layanan terkelola.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Support.ManagedServiceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityUserAssignedIdentity
Daftar identitas yang ditetapkan pengguna yang terkait dengan sumber daya.
Referensi kunci kamus identitas pengguna akan berupa id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}

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

### -Lokasi
Lokasi Sumber Daya.

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

### -Nama
Nama situs statis untuk dibuat atau diperbarui.

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
Parameter Sets: (All)
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

### -SkuName
Nama SKU sumber daya.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteArmResource

## CATATAN

ALIAS

## RELATED LINKS
