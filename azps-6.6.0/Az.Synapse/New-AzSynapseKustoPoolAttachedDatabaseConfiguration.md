---
external help file: ''
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsekustopoolattacheddatabaseconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKustoPoolAttachedDatabaseConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKustoPoolAttachedDatabaseConfiguration.md
ms.openlocfilehash: 17dcee6f2e9245f5f34af012880ca960d7b82569
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140275511"
---
# New-AzSynapseKustoPoolAttachedDatabaseConfiguration

## SYNOPSIS
Membuat atau memperbarui konfigurasi database terlampir.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.synapse/new-azsynapsekustopoolattacheddatabaseconfiguration) untuk informasi terkini.

## SYNTAX

```
New-AzSynapseKustoPoolAttachedDatabaseConfiguration -AttachedDatabaseConfigurationName <String>
 -KustoPoolName <String> -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String>]
 [-DatabaseName <String>] [-DefaultPrincipalsModificationKind <DefaultPrincipalsModificationKind>]
 [-KustoPoolResourceId <String>] [-Location <String>]
 [-TableLevelSharingPropertyExternalTablesToExclude <String[]>]
 [-TableLevelSharingPropertyExternalTablesToInclude <String[]>]
 [-TableLevelSharingPropertyMaterializedViewsToExclude <String[]>]
 [-TableLevelSharingPropertyMaterializedViewsToInclude <String[]>]
 [-TableLevelSharingPropertyTablesToExclude <String[]>] [-TableLevelSharingPropertyTablesToInclude <String[]>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui konfigurasi database terlampir.

## EXAMPLES

### Contoh 1: Create a new AttachedDatabaseConfiguration
```powershell
PS C:\> New-AzSynapseKustoPoolAttachedDatabaseConfiguration -ResourceGroupName testrg -WorkspaceName testws -KustoPoolName testfollowerkustopool -Name followerconfiguration -KustoPoolResourceId /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/testrg/providers/Microsoft.Synapse/workspaces/testws/kustoPools/testkustopool -DatabaseName testdatabase -DefaultPrincipalsModificationKind Union -Location eastus2

Name                                               Type                                                                   Location
----                                               ----                                                                   --------
testws/testfollowerkustopool/followerconfiguration Microsoft.Synapse/workspaces/kustoPools/AttachedDatabaseConfigurations East US 2
```

Perintah di atas membuat database ReadOnly "testdatabase" di kluster "testfollowerkustopool".
Database mengikuti "testdatabase" dari kluster "testkustopool"

## PARAMETERS

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

### -AttachedDatabaseConfigurationName
Nama konfigurasi database yang dilampirkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Nama database yang ingin Anda lampirkan, gunakan * jika Anda ingin mengikuti semua database sekarang dan yang akan datang.

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

### -DefaultPrincipalsModificationKind
Jenis modifikasi prinsipal default

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Synapse.Support.DefaultPrincipalsModificationKind
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

### -KustoPoolName
Nama pool Kusto.

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

### -KustoPoolResourceId
Id sumber daya kusto pool tempat database yang ingin Anda lampirkan berada.

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
Lokasi sumber daya.

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -SubscriptionId
ID langganan target.

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

### -TableLevelSharingPropertyExternalTablesToExclude
Daftar tabel eksternal kecuali dari database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableLevelSharingPropertyExternalTablesToInclude
Daftar tabel eksternal untuk disertakan dalam database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableLevelSharingPropertyMaterializedViewsToExclude
Daftar tampilan yang di materialisasi kecuali dari database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableLevelSharingPropertyMaterializedViewsToInclude
Daftar tampilan yang di materialisasi untuk disertakan dalam database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableLevelSharingPropertyTablesToExclude
Daftar tabel untuk dikecualikan dari database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableLevelSharingPropertyTablesToInclude
Daftar tabel untuk disertakan dalam database pengikut

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Synapse.Models.Api20210601Preview.IAttachedDatabaseConfiguration

## CATATAN

ALIAS

## RELATED LINKS

