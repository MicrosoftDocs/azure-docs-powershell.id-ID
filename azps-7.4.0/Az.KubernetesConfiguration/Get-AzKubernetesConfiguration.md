---
external help file: ''
Module Name: Az.KubernetesConfiguration
online version: https://docs.microsoft.com/powershell/module/az.kubernetesconfiguration/get-azkubernetesconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/Get-AzKubernetesConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/Get-AzKubernetesConfiguration.md
ms.openlocfilehash: c6a8228f890ed266aec568d89cc205070a1eb40f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142424986"
---
# Get-AzKubernetesConfiguration

## SYNOPSIS
Mendapatkan detail Konfigurasi Kontrol Sumber.

## SYNTAX

### Daftar (Default)
```
Get-AzKubernetesConfiguration -ClusterName <String> -ClusterType <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzKubernetesConfiguration -ClusterName <String> -ClusterType <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzKubernetesConfiguration -InputObject <IKubernetesConfigurationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail Konfigurasi Kontrol Sumber.

## EXAMPLES

### Contoh 1: Mencantumkan detail Konfigurasi Kontrol Sumber.
```powershell
Get-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -ClusterType ConnectedClusters
```

```output
Name          Type
----          ----
azpstestk8s01 Microsoft.KubernetesConfiguration/sourceControlConfigurations
azpstestk8s02 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Daftar detail Konfigurasi Kontrol Sumber.

### Contoh 2: Mendapatkan detail Konfigurasi Kontrol Sumber.
```powershell
Get-AzKubernetesConfiguration -ResourceGroupName azps_test_group -ClusterName azps_test_cluster -ClusterType ConnectedClusters -Name azpstestk8s01
```

```output
Name          Type
----          ----
azpstestk8s01 Microsoft.KubernetesConfiguration/sourceControlConfigurations
```

Mendapatkan detail Konfigurasi Kontrol Sumber.

## PARAMETERS

### -ClusterName
Nama kluster kubernetes.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterType
Nama sumber daya kluster Kubernetes - baik managedClusters (untuk kluster AKS) atau ConnectedClusters (untuk kluster OnPrem K8S).

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.IKubernetesConfigurationIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Konfigurasi Kontrol Sumber.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: SourceControlConfigurationName

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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000)

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.IKubernetesConfigurationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.Api20210301.ISourceControlConfiguration

## CATATAN

ALIAS

Get-AzK8sConfiguration

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IKubernetesConfigurationIdentity>: Parameter Identitas
  - `[ClusterName <String>]`: Nama kluster kubernetes.
  - `[ClusterResourceName <String>]`: Nama sumber daya kluster Kubernetes - baik managedClusters (untuk kluster AKS) atau ConnectedClusters (untuk kluster OnPrem K8S).
  - `[ClusterRp <String>]`: RP kluster Kubernetes - baik Microsoft.ContainerService (untuk kluster AKS) atau Microsoft.Kubernetes (untuk kluster OnPrem K8S).
  - `[ExtensionName <String>]`: Nama Ekstensi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OperationId <String>]`: id operasi
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SourceControlConfigurationName <String>]`: Nama Konfigurasi Kontrol Sumber.
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-000000000000)

## RELATED LINKS

