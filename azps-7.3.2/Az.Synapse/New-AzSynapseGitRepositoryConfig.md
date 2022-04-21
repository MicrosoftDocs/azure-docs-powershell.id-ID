---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsegitrepositoryconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseGitRepositoryConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseGitRepositoryConfig.md
ms.openlocfilehash: d42f7390ef4ea570a1ae0aaa418afb64ed418c30
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142754380"
---
# New-AzSynapseGitRepositoryConfig

## SYNOPSIS
Membuat konfigurasi penyimpanan Git.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/new-azsynapsegitrepositoryconfig) untuk informasi terbaru.

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

Perintah pertama membuat konfigurasi penyimpanan Git. Kemudian metode lainnya menggunakan konfigurasi untuk membuat ruang kerja Synapse baru.

## PARAMETERS

### -AccountName
GitHub atau nama akun DevOps yang digunakan untuk penyimpanan.

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
Pilih nama cabang tempat Anda akan berkolaborasi dengan orang lain dan dari mana Anda akan menerbitkan.

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
GitHub Nama host Enterprise.
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
Nama proyek yang Anda sambungkan, hanya tentukan ketika Anda memilih DevOps.

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
Nama repository yang Anda sambungkan.

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
Pilih tipe repositori yang ingin Anda gunakan untuk menyimpan artefak Anda untuk ruang kerja Analitik Synapse ini, tipenya termasuk DevOps dan GitHub.

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
Nilai defaultnya adalah /

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
Pilih Id penyewa yang akan digunakan saat masuk ke repository Git Azure DevOps.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSWorkspaceRepositoryConfiguration

## NOTES

## RELATED LINKS
