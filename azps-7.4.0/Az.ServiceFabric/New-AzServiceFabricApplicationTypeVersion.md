---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricapplicationtypeversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricApplicationTypeVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricApplicationTypeVersion.md
ms.openlocfilehash: d6c59312c0b87812a8b89d828348d3d37849cf05
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144691960"
---
# New-AzServiceFabricApplicationTypeVersion

## SYNOPSIS
Buat versi jenis aplikasi baru di bawah grup sumber daya dan kluster yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/new-azservicefabricapplicationtypeversion) untuk informasi terbaru.

## SYNTAX

```
New-AzServiceFabricApplicationTypeVersion [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name] <String> [-Version] <String> -PackageUrl <String> [-DefaultParameter <Hashtable>] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini membuat versi jenis aplikasi baru menggunakan paket yang ditentukan dalam -PackageUrl, ini harus dapat diakses melalui titik akhir REST untuk Resource Manager Azure untuk digunakan selama penyebaran dan berisi Aplikasi yang dikemas dan di-zip dengan ekstensi .sfpkg. Perintah ini akan membuat jenis aplikasi jika belum ada.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appTypeName = "testAppType"
$version = "v1"
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testApp_1.0.sfpkg"
New-AzServiceFabricApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appTypeName -Version $version -PackageUrl $packageUrl -Verbose
```

Contoh ini akan membuat versi jenis aplikasi "v1" di bawah jenis "testAppType". Versi dalam manifes aplikasi yang terkandung dalam paket harus memiliki versi yang sama dengan yang ditentukan dalam -Version.

## PARAMETERS

### -ClusterName
Tentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultParameter
Tentukan nilai default parameter aplikasi sebagai pasangan kunci/nilai.
Parameter ini harus ada dalam manifes aplikasi.

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

### -Name
Tentukan nama jenis aplikasi

```yaml
Type: System.String
Parameter Sets: (All)
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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Tentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Tentukan versi jenis aplikasi

```yaml
Type: System.String
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSApplicationTypeVersion

## NOTES

## RELATED LINKS
