---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/set-azservicefabricmanagedclusterapplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/Set-AzServiceFabricManagedClusterApplication.md
ms.openlocfilehash: d75b16e5ec6e4bc3f24536ccd6e8d5df8297b94c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136215242"
---
# Set-AzServiceFabricManagedClusterApplication

## SYNOPSIS
Update a service fabric managed application. Hal ini memungkinkan untuk memperbarui parameter aplikasi dan/atau memutakhirkan versi tipe aplikasi yang akan memicu pemutakhiran aplikasi atau pembaruan konfigurasi lainnya saja. Hanya mendukung aplikasi yang disebarkan ARM.

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
Cmdlet ini dapat digunakan untuk memperbarui parameter aplikasi dan memutakhirkan versi tipe aplikasi bersama dengan pembaruan konfigurasi lainnya saja. Memperbarui parameter hanya akan mengubah model di sisi ARM, hanya jika versi tipe baru digunakan, perintah akan memicu pemutakhiran aplikasi. Versi tipe yang ditentukan harus sudah dibuat di kluster menggunakan **New-AzServiceFabricManagedClusterApplicationTypeVersion.**

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $version = "v2"
PS C:\> $packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v2.sfpkg"
PS C:\> New-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -Version $version -PackageUrl $packageUrl -Verbose
PS C:\> Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeVersion $version -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"} -Tags @{tag0="updated"}
```

Contoh ini akan memulai pemutakhiran aplikasi terkelola untuk memperbarui versi tipe ke "v2" yang dibuat dengan **New-AzServiceFabricManagedClusterApplicationTypeVersion**. Parameter aplikasi yang harus ditentukan dalam manifes aplikasi.

### Contoh 2
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -FailureAction Rollback -ForceRestart:$false -Verbose
```

Contoh ini akan memperbarui Bagian Kegagalan dan mengatur ForceRestart ke false.

### Contoh 3
```powershell
PS C:\> $resourceGroupName = "testRG"
PS C:\> $clusterName = "testCluster"
PS C:\> $appName = "testApp"
PS C:\> $version = "v2"
PS C:\> $packageUrl = "https://sftestapp.blob.core.windows.net/sftestapp/testAppType_v2.sfpkg"
PS C:\> New-AzServiceFabricManagedClusterApplicationTypeVersion -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -Version $version -PackageUrl $packageUrl -Verbose
PS C:\> Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationTypeVersion $version -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"} -HealthCheckStableDurationSec 0 -HealthCheckWaitDurationSec 0 -HealthCheckRetryTimeoutSec 0 -UpgradeDomainTimeoutSec 5000 -UpgradeTimeoutSec 7000 -FailureAction Rollback -UpgradeReplicaSetCheckTimeoutSec 300 -ForceRestart
```

Contoh ini akan memulai pemutakhiran aplikasi untuk memperbarui versi tipe ke "v2" dan juga mengatur beberapa parameter kebijakan pemutakhiran yang akan berlaku dari pemutakhiran saat ini.

### Contoh 4
```powershell
PS C:\> Set-AzServiceFabricManagedClusterApplication -ResourceGroupName $resourceGroupName -ClusterName $clusterName -Name $appName -ApplicationParameter @{key0="value0";key1=$null;key2="value2"}
```

Contoh ini memperbarui parameter aplikasi tapi perubahan ini hanya akan berlaku hingga versi berikutnya diupgrade ke aplikasi.

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationTypeVersion
Menentukan versi tipe aplikasi

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
Menunjukkan apakah akan memperlakukan kejadian kesehatan peringatan sebagai kejadian kesalahan selama evaluasi kesehatan.

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
Menentukan persen maksimum partisi tidak membantu per layanan yang diperbolehkan oleh kebijakan kesehatan untuk tipe layanan default yang digunakan untuk pemutakhiran yang dipantau.

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
Menentukan persentase maksimum replika yang tidak membantu per layanan yang diizinkan oleh kebijakan kesehatan untuk tipe layanan default yang akan digunakan untuk pemutakhiran yang dipantau.

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
Menentukan persentase maksimum layanan bantuan yang diperbolehkan oleh kebijakan kesehatan untuk tipe layanan default yang akan digunakan untuk pemutakhiran yang dipantau.

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
Menentukan tindakan yang akan diambil jika pemutakhiran yang dipantau gagal.
Nilai yang dapat diterima untuk parameter ini adalah Rollback atau Manual.

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
Menunjukkan bahwa host layanan memulai ulang meskipun pemutakhiran hanya sebagai perubahan konfigurasi.

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
Menentukan durasi, dalam detik, setelah Service Fabric lagi memeriksa kesehatan jika pemeriksaan kesehatan sebelumnya gagal.

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
Menentukan durasi, dalam detik, Service Fabric tunggu untuk memverifikasi bahwa aplikasi stabil sebelum pindah ke domain pemutakhiran berikutnya atau menyelesaikan pemutakhiran.
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
Menentukan durasi, dalam detik, Service Fabric tunggu sebelum menjalankan pemeriksaan kesehatan awal setelah menyelesaikan pemutakhiran pada domain pemutakhiran.

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
Sumber daya aplikasi yang dikelola.

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
Menentukan durasi dalam detik, untuk menunggu sebelum instans tanpa status ditutup, untuk memungkinkan permintaan aktif menguras dengan baik.

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

### -Nama
Menentukan nama aplikasi

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
Menentukan apakah aplikasi harus dibuat kembali pada pembaruan.
Jika value=true, parameter kebijakan pemutakhiran lainnya tidak diperbolehkan.

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

### -ServiceTypeHealthPolicyMap
Menentukan peta kebijakan kesehatan yang akan digunakan untuk tipe layanan lain sebagai tabel hash dalam format berikut ini: @ {"ServiceTypeName" : "MaxPercentUnhealthyPartitionsPerService,MaxPercentUnhealthyReplicasPerPartition,MaxPercentUnhealthyServices"}.
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
Menentukan persentase maksimum instans aplikasi yang digunakan di simpul dalam kluster yang memiliki status kesehatan kesalahan sebelum status kesehatan aplikasi untuk kluster adalah kesalahan.

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
Menentukan waktu maksimum, dalam detik, Service Fabric diperlukan untuk memutakhirkan satu domain pemutakhiran.
Setelah periode ini, pemutakhiran gagal.

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
Mode yang digunakan untuk memantau kesehatan selama pemutakhiran berguling.
Nilainya Dipantau, dan Tanpa PengawasanAuto.

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
Menentukan waktu maksimum Service Fabric tunggu hingga layanan mengonfigurasi ulang ke keadaan aman, jika belum dalam keadaan aman, sebelum Service Fabric melanjutkan pemutakhiran.

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
Menentukan waktu maksimum, dalam detik, Service Fabric diperlukan untuk seluruh pemutakhiran.
Setelah periode ini, pemutakhiran gagal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedApplication

## CATATAN

## RELATED LINKS
