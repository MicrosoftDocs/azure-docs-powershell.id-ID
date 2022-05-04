---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplication.md
ms.openlocfilehash: 0a44f834362bd8186e0ab3306e70fed4bfce9efd
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144613580"
---
# Set-AzServiceFabricManagedClusterApplication

## SYNOPSIS
Memperbarui aplikasi yang dikelola service fabric. Ini memungkinkan untuk memperbarui parameter aplikasi dan/atau meningkatkan versi jenis aplikasi yang akan memicu peningkatan aplikasi atau pembaruan konfigurasi lainnya saja. Hanya mendukung aplikasi yang disebarkan ARM.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplication) untuk informasi terbaru.

## SYNTAX

### ByResourceGroup (Default)
```
Set-AzServiceFabricManagedClusterApplication [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Name] <String> [[-ApplicationTypeVersion] <String>] [-ApplicationParameter <Hashtable>] [-ForceRestart]
 [-RecreateApplication] [-UpgradeReplicaSetCheckTimeoutSec <Int32>] [-InstanceCloseDelayDurationSec <Int32>]
 [-UpgradeMode <ApplicationUpgradeMode>] [-FailureAction <FailureAction>] [-HealthCheckRetryTimeoutSec <Int32>]
 [-HealthCheckWaitDurationSec <Int32>] [-HealthCheckStableDurationSec <Int32>]
 [-UpgradeDomainTimeoutSec <Int32>] [-UpgradeTimeoutSec <Int32>] [-ConsiderWarningAsError]
 [-DefaultServiceTypeMaxPercentUnhealthyPartitionsPerService <Int32>]
 [-DefaultServiceTypeMaxPercentUnhealthyReplicasPerPartition <Int32>]
 [-DefaultServiceTypeUnhealthyServicesMaxPercent <Int32>] [-UnhealthyDeployedApplicationsMaxPercent <Int32>]
 [-ServiceTypeHealthPolicyMap <Hashtable>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Set-AzServiceFabricManagedClusterApplication [[-ApplicationTypeVersion] <String>]
 [-ApplicationParameter <Hashtable>] [-ForceRestart] [-RecreateApplication]
 [-UpgradeReplicaSetCheckTimeoutSec <Int32>] [-InstanceCloseDelayDurationSec <Int32>]
 [-UpgradeMode <ApplicationUpgradeMode>] [-FailureAction <FailureAction>] [-HealthCheckRetryTimeoutSec <Int32>]
 [-HealthCheckWaitDurationSec <Int32>] [-HealthCheckStableDurationSec <Int32>]
 [-UpgradeDomainTimeoutSec <Int32>] [-UpgradeTimeoutSec <Int32>] [-ConsiderWarningAsError]
 [-DefaultServiceTypeMaxPercentUnhealthyPartitionsPerService <Int32>]
 [-DefaultServiceTypeMaxPercentUnhealthyReplicasPerPartition <Int32>]
 [-DefaultServiceTypeUnhealthyServicesMaxPercent <Int32>] [-UnhealthyDeployedApplicationsMaxPercent <Int32>]
 [-ServiceTypeHealthPolicyMap <Hashtable>] [-Tag <Hashtable>] -ResourceId <String> [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Set-AzServiceFabricManagedClusterApplication [[-ApplicationTypeVersion] <String>]
 [-ApplicationParameter <Hashtable>] [-ForceRestart] [-RecreateApplication]
 [-UpgradeReplicaSetCheckTimeoutSec <Int32>] [-InstanceCloseDelayDurationSec <Int32>]
 [-UpgradeMode <ApplicationUpgradeMode>] [-FailureAction <FailureAction>] [-HealthCheckRetryTimeoutSec <Int32>]
 [-HealthCheckWaitDurationSec <Int32>] [-HealthCheckStableDurationSec <Int32>]
 [-UpgradeDomainTimeoutSec <Int32>] [-UpgradeTimeoutSec <Int32>] [-ConsiderWarningAsError]
 [-DefaultServiceTypeMaxPercentUnhealthyPartitionsPerService <Int32>]
 [-DefaultServiceTypeMaxPercentUnhealthyReplicasPerPartition <Int32>]
 [-DefaultServiceTypeUnhealthyServicesMaxPercent <Int32>] [-UnhealthyDeployedApplicationsMaxPercent <Int32>]
 [-ServiceTypeHealthPolicyMap <Hashtable>] [-Tag <Hashtable>] -InputObject <PSManagedApplication> [-Force]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini dapat digunakan untuk memperbarui parameter aplikasi dan meningkatkan versi jenis aplikasi bersama dengan pembaruan konfigurasi lain saja. Memperbarui parameter hanya akan mengubah model di sisi ARM, hanya ketika versi jenis baru digunakan, perintah akan memicu peningkatan aplikasi. Versi jenis yang ditentukan harus sudah dibuat di kluster menggunakan **New-AzServiceFabricManagedClusterApplicationTypeVersion**.

## EXAMPLES

### Contoh 1
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
$version = "v2"
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v2.sfpkg"
New-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -Version $version -PackageUrl $packageUrl -Verbose
Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeVersion $version -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"} -Tags @{tag0="updated"}
```

Contoh ini akan memulai peningkatan aplikasi terkelola untuk memperbarui versi jenis ke "v2" yang dibuat dengan **New-AzServiceFabricManagedClusterApplicationTypeVersion**. Parameter aplikasi yang digunakan harus ditentukan dalam manifes aplikasi.

### Contoh 2
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -FailureAction Rollback -ForceRestart:$false -Verbose
```

Contoh ini akan memperbarui FailureAction dan mengatur ForceRestart ke false.

### Contoh 3
```powershell
$resourceGroupName = "testRG"
$clusterName = "testCluster"
$appName = "testApp"
$version = "v2"
$packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v2.sfpkg"
New-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -Version $version -PackageUrl $packageUrl -Verbose
Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeVersion $version -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"} -HealthCheckStableDurationSec 0 -HealthCheckWaitDurationSec 0 -HealthCheckRetryTimeoutSec 0 -UpgradeDomainTimeoutSec 5000 -UpgradeTimeoutSec 7000 -FailureAction Rollback -UpgradeReplicaSetCheckTimeoutSec 300 -ForceRestart
```

Contoh ini akan memulai peningkatan aplikasi untuk memperbarui versi jenis ke "v2" dan juga menetapkan beberapa parameter kebijakan peningkatan yang akan berlaku dari peningkatan saat ini.

### Contoh 4
```powershell
Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"}
```

Contoh ini memperbarui parameter aplikasi tetapi perubahan ini hanya akan berlaku sampai peningkatan versi berikutnya ke aplikasi.

## PARAMETERS

### -ApplicationParameter
Tentukan parameter aplikasi sebagai pasangan kunci/nilai.
Parameter ini harus ada dalam manifes aplikasi.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Tentukan versi jenis aplikasi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: ByResourceGroup
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConsiderWarningAsError
Menunjukkan apakah akan memperlakukan peristiwa kesehatan peringatan sebagai peristiwa kesalahan selama evaluasi kesehatan.

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

### -DefaultServiceTypeMaxPercentUnhealthyPartitionsPerService
Menentukan persentase maksimum partisi yang tidak baik per layanan yang diizinkan oleh kebijakan kesehatan untuk jenis layanan default yang digunakan untuk peningkatan yang dipantau.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultServiceTypeMaxPercentUnhealthyReplicasPerPartition
Menentukan persentase maksimum replika yang tidak disengaja per layanan yang diizinkan oleh kebijakan kesehatan untuk jenis layanan default yang digunakan untuk peningkatan yang dipantau.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultServiceTypeUnhealthyServicesMaxPercent
Menentukan persentase maksimum layanan yang tidak disengaja yang diizinkan oleh kebijakan kesehatan untuk jenis layanan default yang akan digunakan untuk peningkatan yang dipantau.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailureAction
Menentukan tindakan yang akan diambil jika peningkatan yang dipantau gagal.
Nilai yang dapat diterima untuk parameter ini adalah Putar Kembali atau Manual.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.FailureAction
Parameter Sets: (All)
Aliases:
Accepted values: Rollback, Manual

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

### -ForceRestart
Menunjukkan bahwa host layanan dimulai ulang meskipun peningkatan adalah perubahan khusus konfigurasi.

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

### -HealthCheckRetryTimeoutSec
Menentukan durasi, dalam detik, setelah itu Service Fabric mencoba kembali pemeriksaan kesehatan jika pemeriksaan kesehatan sebelumnya gagal.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckStableDurationSec
Menentukan durasi, dalam detik, yang Service Fabric tunggu untuk memverifikasi bahwa aplikasi stabil sebelum pindah ke domain peningkatan berikutnya atau menyelesaikan peningkatan.
Durasi tunggu ini mencegah perubahan kesehatan yang tidak terdeteksi tepat setelah pemeriksaan kesehatan dilakukan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthCheckWaitDurationSec
Menentukan durasi, dalam hitungan detik, yang Service Fabric tunggu sebelum melakukan pemeriksaan kesehatan awal setelah menyelesaikan peningkatan pada domain peningkatan.

```yaml
Type: System.Int32
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

### -InstanceCloseDelayDurationSec
Menentukan durasi dalam hitungan detik, untuk menunggu sebelum instans stateless ditutup, untuk memungkinkan permintaan aktif terkuras dengan lancar.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Tentukan nama aplikasi

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

### -RecreateApplication
Menentukan apakah aplikasi harus dibuat ulang saat pembaruan.
Jika value=true, parameter kebijakan peningkatan lainnya tidak diizinkan.

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
Arm ResourceId dari aplikasi terkelola.

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

### -ServiceTypeHealthPolicyMap
Menentukan peta kebijakan kesehatan yang akan digunakan untuk jenis layanan yang berbeda sebagai tabel hash dalam format berikut: @ {"ServiceTypeName" : "MaxPercentUnhealthyPartitionsPerService,MaxPercentUnhealthyReplicasPerPartition,MaxPercentUnhealthyServices"}.
Misalnya: @{ "ServiceTypeName01" = "5,10,5"; "ServiceTypeName02" = "5,5,5" }

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -UnhealthyDeployedApplicationsMaxPercent
Menentukan persentase maksimum instans aplikasi yang disebarkan pada simpul dalam kluster yang memiliki status kesehatan kesalahan sebelum status kesehatan aplikasi untuk kluster adalah kesalahan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeDomainTimeoutSec
Menentukan waktu maksimum, dalam detik, yang Service Fabric ambil untuk meningkatkan satu domain peningkatan.
Setelah periode ini, peningkatan gagal.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeMode
Mode yang digunakan untuk memantau kesehatan selama peningkatan yang sedang bergulir.
Nilainya dipantau, dan UnmonitoredAuto.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.ApplicationUpgradeMode
Parameter Sets: (All)
Aliases:
Accepted values: Monitored, UnmonitoredAuto

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeReplicaSetCheckTimeoutSec
Menentukan waktu maksimum yang Service Fabric menunggu layanan dikonfigurasi ulang ke status aman, jika belum dalam keadaan aman, sebelum Service Fabric melanjutkan peningkatan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeTimeoutSec
Menentukan waktu maksimum, dalam detik, yang Service Fabric ambil untuk seluruh peningkatan.
Setelah periode ini, peningkatan gagal.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## NOTES

## RELATED LINKS
