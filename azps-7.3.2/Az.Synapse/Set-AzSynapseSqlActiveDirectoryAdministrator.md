---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsesqlactivedirectoryadministrator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlActiveDirectoryAdministrator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlActiveDirectoryAdministrator.md
ms.openlocfilehash: 8b1acc5349fab427d36ad8c755e20a96ad55b26c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143235719"
---
# Set-AzSynapseSqlActiveDirectoryAdministrator

## SYNOPSIS
Menyediakan administrator Azure AD untuk kumpulan SQL Analitik Synapse.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/set-azsynapsesqlactivedirectoryadministrator) untuk informasi terbaru.

## SYNTAX

### SetByNameAndDisplayNameParameterSet (Default)
```
Set-AzSynapseSqlActiveDirectoryAdministrator [-ResourceGroupName <String>] -WorkspaceName <String>
 -DisplayName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByNameAndObjectIdParameterSet
```
Set-AzSynapseSqlActiveDirectoryAdministrator [-ResourceGroupName <String>] -WorkspaceName <String>
 -ObjectId <Guid> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByInputObjectAndDisplayNameParameterSet
```
Set-AzSynapseSqlActiveDirectoryAdministrator -InputObject <PSSynapseWorkspace> -DisplayName <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByInputObjectAndObjectIdParameterSet
```
Set-AzSynapseSqlActiveDirectoryAdministrator -InputObject <PSSynapseWorkspace> -ObjectId <Guid> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceIdAndDisplayNameParameterSet
```
Set-AzSynapseSqlActiveDirectoryAdministrator -ResourceId <String> -DisplayName <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByResourceIdAndObjectIdParameterSet
```
Set-AzSynapseSqlActiveDirectoryAdministrator -ResourceId <String> -ObjectId <Guid> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSynapseSqlActiveDirectoryAdministrator** menyediakan administrator Azure Active Directory (Azure AD) untuk ruang kerja analitik Azure Synapse dalam langganan saat ini.
Anda hanya bisa menyediakan satu administrator dalam satu waktu.
Anggota Azure AD berikut dapat ditetapkan sebagai administrator Ruang Kerja Analitik Sinapsis:
- Anggota asli Azure AD 
- Anggota gabungan Azure AD 
- Anggota yang diimpor dari AZURE AD lain yang merupakan anggota asli atau gabungan 
- Azure AD grup yang dibuat sebagai grup keamanan akun Microsoft, seperti yang ada di domain Outlook.com, Hotmail.com, atau Live.com, tidak didukung sebagai administrator.
Akun tamu lain, seperti yang ada di domain Gmail.com atau Yahoo.com, tidak didukung sebagai administrator.
Kami menyarankan agar Anda menyediakan grup Azure AD khusus sebagai administrator.

Cmdlet dapat memanggil di bawah Api Graph Microsoft sesuai dengan parameter input:

* GET /users/{id}
* GET /servicePrincipals/{id}
* GET /groups/{id}

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSynapseSqlActiveDirectoryAdministrator -WorkspaceName ContosoWorkspace -DisplayName "DBAs"
```

Perintah ini menyediakan grup administrator Azure AD bernama DBAs untuk ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Set-AzSynapseSqlActiveDirectoryAdministrator -WorkspaceName ContosoWorkspace -ObjectId "40b79501-b343-44ed-9ce7-da4c8cc7353b"
```

Perintah ini menyediakan administrator Azure AD menurut objectId untuk ruang kerja bernama ContosoWorkspace.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -DisplayName
Menentukan nama tampilan pengguna atau grup yang akan memberikan izin.
Nama tampilan ini harus ada di direktori aktif yang terkait dengan langganan saat ini.

```yaml
Type: System.String
Parameter Sets: SetByNameAndDisplayNameParameterSet, SetByInputObjectAndDisplayNameParameterSet, SetByResourceIdAndDisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: SetByInputObjectAndDisplayNameParameterSet, SetByInputObjectAndObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId
Menentukan ID objek pengguna atau grup di Azure Active Directory untuk memberikan izin.

```yaml
Type: System.Guid
Parameter Sets: SetByNameAndObjectIdParameterSet, SetByInputObjectAndObjectIdParameterSet, SetByResourceIdAndObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SetByNameAndDisplayNameParameterSet, SetByNameAndObjectIdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdAndDisplayNameParameterSet, SetByResourceIdAndObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: SetByNameAndDisplayNameParameterSet, SetByNameAndObjectIdParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSWorkspaceAadAdminInfo

## NOTES

## RELATED LINKS
