---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricmanagedclusterapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedClusterApplication.md
ms.openlocfilehash: 8e0440de177100aafa0d4046ed79e6e80ec3fa72
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138167068"
---
# New-AzServiceFabricManagedClusterApplication

## SYNOPSIS
Create new service fabric managed application under the specified resource group and cluster.

## SYNTAX

### SkipAppTypeVersion (Default)
```
New-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationTypeName] <String> [-ApplicationTypeVersion] <String> -Name <String>
 [-ApplicationParameter <Hashtable>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateAppTypeVersion
```
New-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ApplicationTypeName] <String> [-ApplicationTypeVersion] <String> -Name <String>
 [-ApplicationParameter <Hashtable>] -PackageUrl <String> [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet creates a new service fabric managed application under the specified resource group and cluster. Parameter -PackageUrl dapat digunakan untuk membuat versi tipe, Jika versi tipe sudah keluar tetapi dalam status 'Gagal', cmdlet akan menanyakan apakah pengguna ingin membuat ulang versi tipe. Jika berlanjut dalam status 'Gagal', perintah akan menghentikan proses dan memberikan pengecualian.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $appTypeName = "testAppType"
PS C:\> $appTypeVersion = "v1"
PS C:\> $appParameters =  @{key0="value0";key1=$null;key2="value2"}
PS C:\> New-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeName $appTypeName -ApplicationTypeVersion $appTypeVersion -Name $appName -ApplicationParameter $appParameters
```

Contoh ini membuat aplikasi terkelola "testApp" di bawah grup sumber daya "testRG" dan kluster "testCluster". Tipe aplikasi terkelola "TestAppType" versi "v1" harus sudah ada dalam kluster, dan parameter aplikasi harus ditentukan dalam manifes aplikasi jika tidak cmdlet akan gagal.

### Contoh 2: Tentukan -PackageUrl untuk membuat versi tipe aplikasi sebelum membuat aplikasi.
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $appTypeName = "testAppType"
PS C:\> $appTypeVersion = "v1"
PS C:\> $appParameters =  @{key0="value0";key1=$null;key2="value2"}
PS C:\> $packageUrlV1 = "https://sftestapp.blob.core.windows.net/sftestapp/testApp_1.0.sfpkg"
PS C:\> New-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeName $appTypeName -ApplicationTypeVersion $appTypeVersion -Name $appName -PackageUrl $packageUrlV1 -ApplicationParameter $appParameters
```

Contoh ini membuat tipe aplikasi terkelola "testAppType" versi "v1" menggunakan url paket yang disediakan. Setelah ini, proses normal akan dilanjutkan untuk membuat aplikasi. Jika versi tipe aplikasi yang dikelola sudah keluar dan status penyediaan dalam 'Gagal' versi tersebut akan diminta untuk memutuskan apakah pengguna ingin membuat ulang versi tipe.

## PARAMETERS

### -ApplicationParameter
Tentukan parameter aplikasi sebagai pasangan kunci/nilai.
Parameter ini harus ada di manifes aplikasi.

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

### -ApplicationTypeName
Tentukan nama tipe aplikasi yang dikelola

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Tentukan versi tipe aplikasi yang dikelola

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: (All)
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

### -Nama
Tentukan nama dari aplikasi yang dikelola

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ApplicationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageUrl
Menentukan url file paket aplikasi

```yaml
Type: System.String
Parameter Sets: CreateAppTypeVersion
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

### -Tag
Tentukan tag sebagai pasangan kunci/nilai.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## CATATAN

## RELATED LINKS
