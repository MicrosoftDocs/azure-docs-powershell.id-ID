---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/get-azservicefabricmanagedclusterservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Get-AzServiceFabricManagedClusterService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Get-AzServiceFabricManagedClusterService.md
ms.openlocfilehash: 154286da8f42ca5aed49d7606de5cfa0fc2bcb8f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140371055"
---
# Get-AzServiceFabricManagedClusterService

## SYNOPSIS
Dapatkan Service Fabric layanan terkelola dalam aplikasi dan kluster yang ditentukan. Hanya mendukung layanan ARM yang disebarkan.

## SYNTAX

### ByResourceGroupAndCluster (Default)
```
Get-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzServiceFabricManagedClusterService [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationName] <String> [-Name] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceId
```
Get-AzServiceFabricManagedClusterService -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini akan mendapatkan detail layanan terkelola dalam aplikasi dan kluster yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $serviceName = "testService"
PS C:\> Get-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName
```

Contoh ini mendapatkan detail sumber daya layanan terkelola untuk layanan terkelola "testService".

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> Get-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName
```

Contoh ini mendapatkan daftar layanan terkelola di bawah aplikasi "testApp".

### Contoh 3
```powershell
PS C:\> $resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applications/testApp/services/testService"
PS C:\> Get-AzServiceFabricManagedClusterService -ResourceId $resourceId
```

Contoh ini akan mendapatkan detail layanan yang dikelola dengan ID Sumber Daya ARM yang ditentukan, jika tidak menemukan sumber daya, hal itu akan pengecualian.

## PARAMETERS

### -ApplicationName
Tentukan nama dari aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: ByResourceGroupAndCluster, ByName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Tentukan nama layanan terkelola.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: ServiceName

Required: True
Position: 3
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
Arm ResourceId dari layanan yang dikelola.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedService

## CATATAN

## RELATED LINKS
