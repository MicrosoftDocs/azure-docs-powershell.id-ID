---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/remove-azservicefabricmanagedclusterapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplication.md
ms.openlocfilehash: 7545070483060a534832832fb5748e03a604ec75
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141990174"
---
# Remove-AzServiceFabricManagedClusterApplication

## SYNOPSIS
Hapus aplikasi yang dikelola dari kluster. Tindakan ini akan menghapus semua layanan terkelola di bawah aplikasi. Hanya mendukung aplikasi arm yang digunakan.

## SYNTAX

### ByResourceGroup (Default)
```
Remove-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name] <String> [-PassThru] [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByResourceId
```
Remove-AzServiceFabricManagedClusterApplication -ResourceId <String> [-PassThru] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Remove-AzServiceFabricManagedClusterApplication -InputObject <PSManagedApplication> [-PassThru] [-Force]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini menghapus aplikasi terkelola dari kluster. Tindakan ini akan menghapus semua layanan yang dikelola, jika ada, di bawah sumber daya aplikasi.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
Remove-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName
```

Contoh ini menghapus aplikasi terkelola "testApp" di bawah grup sumber daya "testRG" dan kluster "testCluster".

### Contoh 2
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
$app = Get-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName
$app | Remove-AzServiceFabricManagedClusterApplication
```

Contoh ini menghapus aplikasi terkelola "testApp" di bawah grup sumber daya "testRG" dan kluster "testCluster".

### Contoh 3
```powershell
$resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applications/testApp/services/testService"
Remove-AzServiceFabricManagedClusterApplication -ResourceId $resourceId
```

Contoh ini menghapus aplikasi terkelola "testApp" dengan ID Sumber Daya ARM yang ditentukan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Job untuk melacak kemajuan.

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

### -Paksa
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
Sumber daya aplikasi terkelola.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Tentukan nama aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationName

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
{{ Fill PassThru Description }}

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

### System.String

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
