---
external help file: ''
Module Name: Az.KubernetesConfiguration
online version: https://docs.microsoft.com/powershell/module/az.kubernetesconfiguration/new-azkubernetesconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesConfiguration.md
ms.openlocfilehash: 6cf1860a5ef224a0d1ed255d6c21e26bee37fed0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141787946"
---
# New-AzKubernetesConfiguration

## SYNOPSIS
Buat Konfigurasi Kontrol Sumber Kubernetes baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.kubernetesconfiguration/new-azkubernetesconfiguration) untuk informasi terbaru.

## SYNTAX

```
New-AzKubernetesConfiguration -ClusterName <String> -Name <String> -ResourceGroupName <String>
 -RepositoryUrl <String> [-ClusterType <String>] [-SubscriptionId <String>] [-ClusterScoped]
 [-ConfigurationProtectedSetting <Hashtable>] [-EnableHelmOperator] [-HelmOperatorChartValue <String>]
 [-HelmOperatorChartVersion <String>] [-OperatorInstanceName <String>] [-OperatorNamespace <String>]
 [-OperatorParameter <String>] [-SshKnownHost <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Buat Konfigurasi Kontrol Sumber Kubernetes baru.

## EXAMPLES

### Contoh 1: Membuat konfigurasi untuk kluster kubernetes
```powershell
PS C:\> New-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -Name azpstestk8s01 -RepositoryUrl http://github.com/xxxx

Name          Type
----          ----
azpstestk8s01 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Perintah ini membuat konfigurasi untuk kluster kubernetes.

### Contoh 2: Membuat konfigurasi untuk kluster kubernetes dengan menentukan paramter OperatorNamespace
```powershell
PS C:\> New-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -Name azpstestk8s02 -RepositoryUrl http://github.com/xxxx -OperatorNamespace namespace-t01

Name          Type
----          ----
azpstestk8s02 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Perintah ini membuat konfigurasi di namespace operator baru untuk kluster kubernetes.
Catatan, Tidak dapat membuat konfigurasi di ruang nama operator yang sudah ada.

## PARAMETERS

### -ClusterName
Nama kluster kubernetes.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterScoped
Jika lolos, atur lingkup Konfigurasi ke Kluster (defaultnya adalah nameSpace).

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

### -ClusterType
Nama sumber daya kluster Kubernetes - baik managedClusters (untuk kluster AKS) atau ConnectedClusters (untuk kluster OnPrem K8S).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationProtectedSetting
Pasangan nilai nama dari pengaturan konfigurasi yang diproteksi untuk konfigurasi

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHelmOperator
Opsi untuk mengaktifkan Operator Helm untuk konfigurasi git ini.

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

### -HelmOperatorChartValue
Nilai akan ditimpa untuk bagan Helm operator.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HelmOperatorChartVersion
Versi bagan Helm operator.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Konfigurasi Kontrol Sumber.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SourceControlConfigurationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatorInstanceName
Nama instans operator - mengidentifikasi konfigurasi tertentu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatorNamespace
Ruang nama tempat operator ini diinstal.
Maksimal 253 karakter alfanumerik huruf kecil, tanda hubung dan titik saja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperatorParameter
Parameter apa pun untuk instans Operator dalam format string.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepositoryUrl
Url Repository SourceControl.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshKnownHost
Jika lolos, atur lingkup Konfigurasi ke Kluster (defaultnya adalah nameSpace).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.Api20210301.ISourceControlConfiguration

## CATATAN

ALIAS

New-AzK8sConfiguration

## RELATED LINKS

