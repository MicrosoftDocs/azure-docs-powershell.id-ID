---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/remove-azservicefabricmanagedclusterapplicationtypeversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplicationTypeVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Remove-AzServiceFabricManagedClusterApplicationTypeVersion.md
ms.openlocfilehash: 9dafd6c1febf9721a227fa7bddf7020984daf91a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142252927"
---
# Remove-AzServiceFabricManagedClusterApplicationTypeVersion

## SYNOPSIS
Menghapus versi tipe aplikasi terkelola dari kluster. Hanya mendukung ARM versi tipe aplikasi yang digunakan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/remove-azservicefabricmanagedclusterapplicationtypeversion) untuk informasi terbaru.

## SYNTAX

### ByResourceGroup (Default)
```
Remove-AzServiceFabricManagedClusterApplicationTypeVersion [-ResourceGroupName] <String>
 [-ClusterName] <String> -Name <String> -Version <String> [-PassThru] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Remove-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceId <String> [-PassThru] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Remove-AzServiceFabricManagedClusterApplicationTypeVersion -InputObject <PSManagedApplicationTypeVersion>
 [-PassThru] [-Force] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini akan menghapus versi tipe aplikasi yang dikelola dari kluster. Semua aplikasi di bawah sumber daya ini harus dihapus sebelum menjalankan perintah ini.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appTypeName = "testAppType"
PS C:\> $version = "v1"
PS C:\> Remove-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Version $version -Force -PassThru -Verbose
```

Contoh ini akan menghapus versi terkelola "v1" di bawah tipe "testAppType". Ini ada aplikasi apa pun di bawah sumber daya ini perintah akan memberikan pengecualian.

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appTypeName = "testAppType"
PS C:\> $version = "v1"
PS C:\> $appTypeVersion = Get-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Version $appTypeVersion
PS C:\> $appTypeVersion | Remove-AzServiceFabricManagedClusterApplicationTypeVersion -Force -PassThru -Verbose
```

Contoh ini akan menghapus versi terkelola "v1" di bawah tipe "testAppType". Ini ada aplikasi apa pun di bawah sumber daya ini perintah akan memberikan pengecualian.

### Contoh 3
```powershell
PS C:\> $resourceId = "/subscriptions/13ad2c84-84fa-4798-ad71-e70c07af873f/resourcegroups/testRG/providers/Microsoft.ServiceFabric/managedClusters/testCluster/applicationTypes/testAppType/versions/v1"
PS C:\> Remove-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceId $resourceId
```

Contoh ini akan menghapus detail versi tipe aplikasi terkelola dengan ID Sumber Daya ARM yang ditentukan.

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
Sumber daya versi tipe aplikasi terkelola.

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

### -Nama
Tentukan nama tipe aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationTypeName

Required: True
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
Arm ResourceId dari versi tipe aplikasi yang dikelola.

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

### -Versi
Tentukan versi tipe aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases: ApplicationTypeVersion

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

### System.String

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplicationTypeVersion

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
