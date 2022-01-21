---
external help file: ''
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azstaticwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzStaticWebApp.md
ms.openlocfilehash: 1c89ca292fa1b033f7cc0f9693d8ac26eace29b9
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136554596"
---
# New-AzStaticWebApp

## SYNOPSIS
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## SYNTAX

```
New-AzStaticWebApp -Name <String> -ResourceGroupName <String> -Location <String> [-SubscriptionId <String>]
 [-AllowConfigFileUpdate] [-ApiBuildCommand <String>] [-ApiLocation <String>] [-AppArtifactLocation <String>]
 [-AppBuildCommand <String>] [-AppLocation <String>] [-Branch <String>] [-Capacity <Int32>]
 [-ForkRepositoryDescription <String>] [-ForkRepositoryIsPrivate] [-ForkRepositoryName <String>]
 [-ForkRepositoryOwner <String>] [-GithubActionSecretNameOverride <String>]
 [-IdentityType <ManagedServiceIdentityType>] [-IdentityUserAssignedIdentity <Hashtable>] [-Kind <String>]
 [-OutputLocation <String>] [-RepositoryToken <String>] [-RepositoryUrl <String>]
 [-SkipGithubActionWorkflowGeneration] [-SkuName <String>]
 [-StagingEnvironmentPolicy <StagingEnvironmentPolicy>] [-Tag <Hashtable>] [-TemplateRepositoryUrl <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Deskripsi untuk Membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

## EXAMPLES

### Contoh 1: Membuat situs statis baru dalam grup sumber daya yang ada, atau memperbarui situs statis yang sudah ada
```powershell
PS C:\> New-AzStaticWebApp -ResourceGroupName 'azure-rg-test' -Name 'staticweb-45asde' -Location 'Central US' -RepositoryUrl 'https://github.com/LucasYao93/blazor-starter' -RepositoryToken 'githubAccessToken' -Branch 'branch02' -AppLocation 'Client' -ApiLocation 'Api' -OutputLocation 'wwwroot' -SkuName 'Standard'

Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb-45asde Microsoft.Web/staticSites
```

Perintah ini akan membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada.

### Contoh 2: Membuat situs statis baru dalam grup sumber daya yang ada melalui penyimpanan templat tertentu
```powershell
PS C:\> New-AzStaticWebApp -ResourceGroupName 'azure-rg-test' -Name staticweb-pwsh01 -Location "Central US" -RepositoryToken  'xxxxxxxxxxxxxxxxx' -TemplateRepositoryUrl 'https://github.com/staticwebdev/blazor-starter' -ForkRepositoryDescription "Test template repository function of the azure static web." -ForkRepositoryName "test-blazor-starter" -ForkRepositoryOwner 'LucasYao93' -Branch 'main' -AppLocation 'Client' -ApiLocation 'Api' -OutputLocation 'wwwroot' -SkuName 'Standard'

Kind Location   Name             Type
---- --------   ----             ----
     Central US staticweb-pwsh01 Microsoft.Web/staticSites
```

Perintah ini akan membuat situs statis baru dalam grup sumber daya yang sudah ada, atau memperbarui situs statis yang sudah ada melalui penyimpanan templat tertentu.

## PARAMETERS

### -AllowConfigFileUpdate
\<code\>false \</code\> jika file konfigurasi dikunci untuk aplikasi web statis ini; jika tidak, true \<code\> \</code\> .

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

### -Kapasitas
Jumlah contoh saat ini yang ditetapkan ke sumber daya.

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

### -IdentityType
Tipe identitas layanan terkelola.

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
Referensi kunci kamus identitas pengguna akan menjadi ID sumber daya ARM di formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}

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
Nama situs statis untuk membuat atau memperbarui.

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
Menjalankan perintah secara asinkron

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
Parameter Sets: (All)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20201201.IStaticSiteArmResource

## CATATAN

ALIAS

## RELATED LINKS

