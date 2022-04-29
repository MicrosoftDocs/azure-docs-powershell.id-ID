---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapseworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseWorkspace.md
ms.openlocfilehash: dc917dce69298c26f5aca423d8c62aef31e400b0
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144197324"
---
# New-AzSynapseWorkspace

## SYNOPSIS
Membuat ruang kerja Synapse Analytics.

## SYNTAX

```
New-AzSynapseWorkspace -ResourceGroupName <String> -Name <String> -Location <String> [-Tag <Hashtable>]
 -DefaultDataLakeStorageAccountName <String> -DefaultDataLakeStorageFilesystem <String>
 -SqlAdministratorLoginCredential <PSCredential> [-ManagedVirtualNetwork <PSManagedVirtualNetworkSettings>]
 [-EncryptionKeyName <String>] [-EncryptionKeyIdentifier <String>] [-AsJob]
 [-ManagedResourceGroupName <String>] [-GitRepository <PSWorkspaceRepositoryConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseWorkspace** membuat ruang kerja Azure Synapse Analytics.

## EXAMPLES

### Contoh 1
```powershell
$password = ConvertTo-SecureString "Password123!" -AsPlainText -Force
$creds = New-Object System.Management.Automation.PSCredential ("ContosoUser", $password)
New-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -Name ContosoWorkspace -Location northeurope -DefaultDataLakeStorageAccountName ContosoAdlGen2Storage -DefaultDataLakeStorageFilesystem ContosoFileSystem -SqlAdministratorLoginCredential $creds
```

Perintah ini membuat ruang kerja Synapse Analytics bernama ContosoWorkspace yang menggunakan Penyimpanan Data ContosoAdlGenStorage, di grup sumber daya bernama ContosoResourceGroup.

### Contoh 2
```powershell
$config = New-AzSynapseManagedVirtualNetworkConfig -PreventDataExfiltration -AllowedAadTenantIdsForLinking ContosoTenantId
$password = ConvertTo-SecureString "Password123!" -AsPlainText -Force
$creds = New-Object System.Management.Automation.PSCredential ("ContosoUser", $password)
New-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -Name ContosoWorkspace -Location northeurope -DefaultDataLakeStorageAccountName ContosoAdlGen2Storage -DefaultDataLakeStorageFilesystem ContosoFileSystem -SqlAdministratorLoginCredential $creds -ManagedVirtualNetwork $config
```

Perintah pertama membuat konfigurasi jaringan virtual terkelola. Kemudian metode lainnya menggunakan konfigurasi untuk membuat ruang kerja Synapse baru.

### Contoh 3
```powershell
$password = ConvertTo-SecureString "Password123!" -AsPlainText -Force
$creds = New-Object System.Management.Automation.PSCredential ("ContosoUser", $password)
$config = New-AzSynapseGitRepositoryConfig -RepositoryType GitHub -AccountName ContosoAccount -RepositoryName ContosoRepo -CollaborationBranch main
New-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -Name ContosoWorkspace -Location northeurope -DefaultDataLakeStorageAccountName ContosoAdlGen2Storage -DefaultDataLakeStorageFilesystem ContosoFileSystem -SqlAdministratorLoginCredential $creds -GitRepository $config
```

Perintah ini membuat ruang kerja Synapse Analytics bernama ContosoWorkspace yang menggunakan Penyimpanan Data ContosoAdlGenStorage, di grup sumber daya bernama ContosoResourceGroup. Dan ruang kerja terhubung ke Repositori Git yang disebut ContosoRepo.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -DefaultDataLakeStorageAccountName
Nama akun penyimpanan ADLS Gen2 default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultDataLakeStorageFilesystem
Sistem file ADLS Gen2 default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -EncryptionKeyIdentifier
Pengidentifikasi kunci harus dalam format: https://{keyvaultname}.vault.azure.net/keys/{keyname}.

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

### -EncryptionKeyName
Nama kunci enkripsi ruang kerja.

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

### -GitRepository
Repositori Git Pengaturan. Koneksi ruang kerja ke repositori untuk kontrol sumber dan kolaborasi untuk bekerja pada alur ruang kerja Anda

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSWorkspaceRepositoryConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Wilayah Azure tempat sumber daya harus dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedResourceGroupName
Kontainer yang menyimpan sumber daya tambahan. Dibuat secara default sementara nama dapat ditentukan. Perhatikan bahwa bidang ini tidak boleh sama dengan ResourceGroupName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedVirtualNetwork
Nama jaringan virtual yang dikelola Synapse yang didedikasikan untuk ruang kerja Azure Synapse.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSManagedVirtualNetworkSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: WorkspaceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SqlAdministratorLoginCredential
SQL kredensial administrator.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
String, kamus string tag yang terkait dengan sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Management.Automation.PSCredential

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## NOTES

## RELATED LINKS
