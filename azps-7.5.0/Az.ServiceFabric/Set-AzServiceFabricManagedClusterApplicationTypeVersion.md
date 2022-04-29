---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplicationtypeversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplicationTypeVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplicationTypeVersion.md
ms.openlocfilehash: a6c35e13a49d04a975b73e6c31f347d092d7ba18
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144195938"
---
# Set-AzServiceFabricManagedClusterApplicationTypeVersion

## SYNOPSIS
Memperbarui versi jenis aplikasi terkelola service fabric. Ini memungkinkan Anda memperbarui tag dan Url paket. Hanya mendukung versi jenis aplikasi yang disebarkan ARM.

## SYNTAX

### ByResourceGroup (Default)
```
Set-AzServiceFabricManagedClusterApplicationTypeVersion [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name] <String> [-Version] <String> [-PackageUrl <String>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Set-AzServiceFabricManagedClusterApplicationTypeVersion [-PackageUrl <String>] [-Tag <Hashtable>]
 -ResourceId <String> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInputObject
```
Set-AzServiceFabricManagedClusterApplicationTypeVersion [-PackageUrl <String>] [-Tag <Hashtable>]
 -InputObject <PSManagedApplicationTypeVersion> [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini dapat digunakan untuk memperbarui tag versi jenis aplikasi.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appTypeName = "testAppType"
$version = "v1"
$newTags = @{new="tags"}
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v1.sfpkg"
Set-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Version $version -Tags $newTags -PackageUrl $packageUrl -Verbose
```

Contoh ini akan memperbarui tag dan packageUrl versi aplikasi terkelola versi "v1".

### Contoh 2
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appTypeName = "testAppType"
$newTags = @{new="tags"}
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v1.sfpkg"
$appType = Get-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Version $version
$appType | Set-AzServiceFabricManagedClusterApplicationTypeVersion -Tags $newTags -PackageUrl $packageUrl -Verbose
```

Contoh ini akan memperbarui tag dan packageUrl versi aplikasi terkelola versi "v1".

### Contoh 3
```powershell
$newTags = @{new="tags"}
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v1.sfpkg"
$resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applicationTypes/testAppType/versions/v1"
Set-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceId $resourceId -Tags $newTags -PackageUrl $packageUrl -Verbose
```

Contoh ini akan memperbarui detail jenis aplikasi terkelola dengan ID Sumber Daya ARM yang ditentukan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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
Lanjutkan tanpa perintah

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
Sumber daya versi jenis aplikasi terkelola.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationTypeVersion
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Tentukan nama jenis aplikasi terkelola

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationTypeName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageUrl
Tentukan url file sfpkg paket aplikasi

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
Arm ResourceId dari versi jenis aplikasi terkelola.

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

### -Versi
Tentukan versi jenis aplikasi terkelola

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationTypeVersion

Required: True
Position: 3
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationTypeVersion

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationTypeVersion

## NOTES

## RELATED LINKS
