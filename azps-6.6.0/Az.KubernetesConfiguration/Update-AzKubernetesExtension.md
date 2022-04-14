---
external help file: ''
Module Name: Az.KubernetesConfiguration
online version: https://docs.microsoft.com/powershell/module/az.kubernetesconfiguration/update-azkubernetesextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/Update-AzKubernetesExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/Update-AzKubernetesExtension.md
ms.openlocfilehash: 790691f3f30551443c042dfea679ec3e1b072947
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142230751"
---
# Update-AzKubernetesExtension

## SYNOPSIS
Patch Ekstensi Kluster Kubernetes yang sudah ada.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.kubernetesconfiguration/update-azkubernetesextension) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzKubernetesExtension -ClusterName <String> -ClusterType <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-AutoUpgradeMinorVersion]
 [-ConfigurationProtectedSetting <Hashtable>] [-ConfigurationSetting <Hashtable>] [-ReleaseTrain <String>]
 [-Version <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzKubernetesExtension -InputObject <IKubernetesConfigurationIdentity> [-AutoUpgradeMinorVersion]
 [-ConfigurationProtectedSetting <Hashtable>] [-ConfigurationSetting <Hashtable>] [-ReleaseTrain <String>]
 [-Version <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Patch Ekstensi Kluster Kubernetes yang sudah ada.

## EXAMPLES

### Contoh 1: Update Ekstensi Kluster Kubernetes yang sudah ada.
```powershell
PS C:\>  Update-AzKubernetesExtension -ClusterName azps_test_cluster -ClusterType ConnectedClusters -Name azps_test_extension -ResourceGroupName azps_test_group -ConfigurationProtectedSetting @{"aa"="bb"}

Name                ExtensionType             Version      ProvisioningState AutoUpgradeMinorVersion ReleaseTrain ResourceGroupName
----                -------------             -------      ----------------- ----------------------- ------------ -----------------
azps_test_extension microsoft.arcdataservices 1.0.16701001 Succeeded         True                    Stable       azps_test_group
```

Memperbarui Ekstensi Kluster Kubernetes yang sudah ada.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -AutoUpgradeMinorVersion
Benderai untuk diperhatikan jika ekstensi ini berpartisipasi dalam pemutakhiran otomatis versi minor, atau tidak.

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
Nama kluster kubernetes.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationProtectedSetting
Pengaturan konfigurasi yang sensitif, sebagai pasangan nilai nama untuk mengonfigurasi ekstensi ini.

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

### -ConfigurationSetting
Pengaturan konfigurasi, sebagai pasangan nilai nama untuk mengonfigurasi ekstensi ini.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.IKubernetesConfigurationIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Ekstensi.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ExtensionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -ReleaseTrain
ReleaseTrain ekstensi ini berpartisipasi untuk pemutakhiran otomatis (misalnya Stabil, Pratinjau, dll.) - hanya jika autoUpgradeMinorVersion adalah 'true'.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Versi
Versi ekstensi untuk ekstensi ini, jika 'disematkan' ke versi tertentu.
autoUpgradeMinorVersion harus 'false'.

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

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.IKubernetesConfigurationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.Api20210901.IExtension

## CATATAN

ALIAS

Update-AzK8sExtension

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

