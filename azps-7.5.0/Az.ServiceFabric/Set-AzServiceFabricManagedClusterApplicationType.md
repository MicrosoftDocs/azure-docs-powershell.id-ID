---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplicationtype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplicationType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplicationType.md
ms.openlocfilehash: 78e32a76a0d430414e830a48995bc7b6a0a73bc3
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145630250"
---
# Set-AzServiceFabricManagedClusterApplicationType

## SYNOPSIS
Memperbarui jenis aplikasi yang dikelola service fabric. Ini memungkinkan Anda memperbarui tag. Hanya mendukung jenis aplikasi yang disebarkan ARM.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplicationtype) untuk informasi terbaru.

## SYNTAX

### ByResourceGroup (Default)
```
Set-AzServiceFabricManagedClusterApplicationType [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name <String>] [-Tag <Hashtable>] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInputObject
```
Set-AzServiceFabricManagedClusterApplicationType [-Tag <Hashtable>] -InputObject <PSManagedApplicationType>
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Set-AzServiceFabricManagedClusterApplicationType [-Tag <Hashtable>] -ResourceId <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini dapat digunakan untuk memperbarui tag jenis aplikasi.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appTypeName = "testAppType"
$newTags = @{new="tags"}
Set-AzServiceFabricManagedClusterApplicationType -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Tags $newTags -Verbose
```

Contoh ini akan memperbarui tag "testAppType" jenis aplikasi terkelola.

### Contoh 2
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appTypeName = "testAppType"
$newTags = @{new="tags"}
$appType = Get-AzServiceFabricManagedClusterApplicationType -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName
$appType | Set-AzServiceFabricManagedClusterApplicationType -Tags $newTags -Verbose
```

Contoh ini akan memperbarui tag "testAppType" jenis aplikasi terkelola.

### Contoh: 3
```powershell
$newTags = @{new="tags"}
$resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applicationTypes/testAppType"
Set-AzServiceFabricManagedClusterApplicationType -ResourceId $resourceId -Tags $newTags
```

Contoh ini akan memperbarui detail jenis aplikasi terkelola dengan ID Sumber Daya ARM yang ditentukan.

## PARAMETERS

### -ClusterName
Tentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases:

Required: True
Position: 1
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

### -Force
Hapus tanpa perintah.

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

### -InputObject
Sumber daya jenis aplikasi terkelola.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationType
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Tentukan nama jenis aplikasi terkelola.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationTypeName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Arm ResourceId dari jenis aplikasi terkelola.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tentukan tag sebagai pasangan kunci/nilai.

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

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationType

## OUTPUTS

### System.Boolean

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationType

## NOTES

## RELATED LINKS
