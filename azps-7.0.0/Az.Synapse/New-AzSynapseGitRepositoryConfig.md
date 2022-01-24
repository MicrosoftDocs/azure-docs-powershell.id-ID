---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsegitrepositoryconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseGitRepositoryConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseGitRepositoryConfig.md
ms.openlocfilehash: a45bfec4b819dfa91eff69468de75e01958adea7
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136530200"
---
# New-AzSynapseGitRepositoryConfig

## SYNOPSIS
Membuat konfigurasi repositori Git.

## SYNTAX

```
New-AzSynapseGitRepositoryConfig -RepositoryType <String> [-HostName <String>] -AccountName <String>
 [-ProjectName <String>] -RepositoryName <String> -CollaborationBranch <String> [-RootFolder <String>]
 [-TenantId <Guid>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseGitRepositoryConfig** ini membuat konfigurasi repositori Git yang dapat digunakan dalam membuat atau memperbarui ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $config = New-AzSynapseGitRepositoryConfig -RepositoryType GitHub -AccountName ContosoAccount -RepositoryName ContosoRepo -CollaborationBranch main
PS C:\> $password = ConvertTo-SecureString "Password123!" -AsPlainText -Force
PS C:\> $creds = New-Object System.Management.Automation.PSCredential ("ContosoUser", $password)
PS C:\> New-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -Name ContosoWorkspace -Location northeurope -DefaultDataLakeStorageAccountName ContosoAdlGen2Storage -DefaultDataLakeStorageFilesystem ContosoFileSystem -SqlAdministratorLoginCredential $creds -AsJob -GitRepository $config
```

Perintah pertama membuat konfigurasi repositori Git. Lalu metode lainnya menggunakan konfigurasi untuk membuat ruang kerja Synapse yang baru.

## PARAMETERS

### -Nama Akun
GitHub atau DevOps digunakan untuk tempat penyimpanan.

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

### -CollaborationBranch
Pilih nama cabang tempat Anda akan berkolaborasi dengan orang lain dan dari mana Anda akan menerbitkannya.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
GitHub host Enterprise.
Misalnya: `https://github.mydomain.com`

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

### -ProjectName
Nama proyek yang Anda sambungkan, hanya tentukan saat Anda memilih DevOps.

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

### -RepositoryName
Nama penyimpanan yang Anda sambungkan.

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

### -RepositoryType
Pilih tipe penyimpanan yang ingin Anda gunakan untuk menyimpan artifak Anda untuk ruang kerja Analitik Synapse ini, tipenya meliputi DevOps dan GitHub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: GitHub, AzureDevOpsGit

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RootFolder
Menampilkan nama folder ke lokasi sumber daya JSON Azure Data Factory Anda diimpor.
Nilai default adalah /

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

### -TenantId
Pilih Id penyewa untuk digunakan saat masuk ke Azure DevOps repositori Git.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSWorkspaceRepositoryConfiguration

## CATATAN

## RELATED LINKS
