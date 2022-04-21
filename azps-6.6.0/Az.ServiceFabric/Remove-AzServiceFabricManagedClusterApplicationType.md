---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/remove-azservicefabricmanagedclusterapplicationtype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplicationType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplicationType.md
ms.openlocfilehash: 38b2316d1c827a4f35524874acc5387c20990326
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142707562"
---
# Remove-AzServiceFabricManagedClusterApplicationType

## SYNOPSIS
Menghapus tipe aplikasi yang dikelola dari kluster. Tindakan ini akan menghapus semua versi tipe di bawah sumber daya ini. Hanya mendukung ARM tipe aplikasi yang digunakan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/remove-azservicefabricmanagedclusterapplicationtype) untuk informasi terbaru.

## SYNTAX

### ByResourceGroup (Default)
```
Remove-AzServiceFabricManagedClusterApplicationType [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name <String>] [-PassThru] [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByResourceId
```
Remove-AzServiceFabricManagedClusterApplicationType -ResourceId <String> [-PassThru] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Remove-AzServiceFabricManagedClusterApplicationType -InputObject <PSManagedApplicationType> [-PassThru]
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini menghapus tipe aplikasi yang dikelola dari kluster dan akan menghapus semua versi tipe di bawah sumber daya ini, tetapi semua aplikasi di bawahnya harus dihapus sebelum menjalankan perintah ini.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appTypeName = "testAppType"
PS C:\> Remove-AzServiceFabricManagedClusterApplicationType -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Verbose
```

Contoh ini akan menghapus tipe aplikasi terkelola "testAppType" dan semua versi di bawahnya. Jika ada aplikasi yang dibuat dengan tipe ini, perintah akan memberikan pengecualian.

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appTypeName = "testAppType"
PS C:\> $appType = Get-AzServiceFabricManagedClusterApplicationType -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName
PS C:\> $appType | Remove-AzServiceFabricManagedClusterApplicationType -Verbose
```

Contoh ini akan menghapus tipe aplikasi terkelola "testAppType" dan semua versi di bawahnya. Jika ada aplikasi yang dibuat dengan tipe ini, perintah akan memberikan pengecualian.

### Contoh 3
```powershell
PS C:\> $resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applicationTypes/testAppType"
PS C:\> Remove-AzServiceFabricManagedClusterApplicationType -ResourceId $resourceId
```

Contoh ini akan menghapus detail tipe aplikasi terkelola dengan ID Sumber Daya ARM yang ditentukan.

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
Sumber daya tipe aplikasi terkelola.

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

### -Nama
Tentukan nama tipe aplikasi yang dikelola.

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
Arm ResourceId dari tipe aplikasi yang dikelola.

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

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationType

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
