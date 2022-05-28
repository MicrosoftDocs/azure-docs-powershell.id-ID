---
external help file: ''
Module Name: Az.KubernetesConfiguration
online version: https://docs.microsoft.com/powershell/module/az.kubernetesconfiguration/new-azkubernetesconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesConfiguration.md
ms.openlocfilehash: 101832f53ab56de02a7c82fe2b0c377bcdc692d4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500524"
---
# New-AzKubernetesConfiguration

## SYNOPSIS
Buat Konfigurasi Kontrol Sumber Kubernetes baru.

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
New-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -Name azpstestk8s01 -RepositoryUrl http://github.com/xxxx
```

```output
Name          Type
----          ----
azpstestk8s01 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Perintah ini membuat konfigurasi untuk kluster kubernetes.

### Contoh 2: Membuat konfigurasi untuk kluster kubernetes dengan menentukan operatorNamespace paramter
```powershell
New-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -Name azpstestk8s02 -RepositoryUrl http://github.com/xxxx -OperatorNamespace namespace-t01
```

```output
Name          Type
----          ----
azpstestk8s02 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Perintah ini membuat konfigurasi di namespace operator baru untuk kluster kubernetes.
Catatan, Tidak dapat membuat konfigurasi di namespace operator yang ada.

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
Jika diteruskan, atur cakupan Konfigurasi ke Kluster (defaultnya adalah nameSpace).

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
Nama sumber daya kluster Kubernetes - baik managedClusters (untuk kluster AKS) atau connectedClusters (untuk kluster OnPrem K8S).

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
Pasangan nilai nama dari pengaturan konfigurasi yang dilindungi untuk konfigurasi

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
Nilai ditimpa untuk bagan Helm operator.

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

### -Name
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
Namespace tempat operator ini diinstal.
Maksimum 253 karakter alfanumerik huruf kecil, tanda hubung, dan titik saja.

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
Url Repositori SourceControl.

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
Jika diteruskan, atur cakupan Konfigurasi ke Kluster (defaultnya adalah nameSpace).

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
Atur ID Langganan Azure.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.Api20210301.ISourceControlConfiguration

## NOTES

ALIAS

New-AzK8sConfiguration

## RELATED LINKS

