---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/get-azservicefabricmanagedclusterapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Get-AzServiceFabricManagedClusterApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Get-AzServiceFabricManagedClusterApplication.md
ms.openlocfilehash: 8f96c0fa945b9c9b1efd5ce65757324a6072e472
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136573521"
---
# Get-AzServiceFabricManagedClusterApplication

## SYNOPSIS
Dapatkan Service Fabric aplikasi yang dikelola. Hanya mendukung aplikasi yang disebarkan ARM.

## SYNTAX

### ByResourceGroupAndCluster (Default)
```
Get-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceId
```
Get-AzServiceFabricManagedClusterApplication -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini mendapatkan detail aplikasi terkelola dalam grup dan kluster sumber daya yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> Get-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName
```

This example gets the managed application resource details for the managed application "testApp".

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> Get-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName
```

Contoh ini mendapatkan daftar aplikasi terkelola di bawah kluster "testCluster".

### Contoh 3
```powershell
PS C:\> $resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applications/testApp"
PS C:\> Get-AzServiceFabricManagedClusterApplication -ResourceId $resourceId
```

Contoh ini akan mendapatkan detail aplikasi yang dikelola dengan ID Sumber Daya ARM yang ditentukan, jika TIDAK menemukan sumber daya, hal itu akan pengecualian.

## PARAMETERS

### -ClusterName
Tentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: ByResourceGroupAndCluster, ByName
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

### -Nama
Tentukan nama dari aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: ApplicationName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResourceGroupAndCluster, ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Arm ResourceId dari aplikasi yang dikelola.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## CATATAN

## RELATED LINKS
