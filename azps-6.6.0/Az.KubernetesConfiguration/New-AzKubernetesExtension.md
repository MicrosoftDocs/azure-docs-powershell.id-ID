---
external help file: ''
Module Name: Az.KubernetesConfiguration
online version: https://docs.microsoft.com/powershell/module/az.kubernetesconfiguration/new-azkubernetesextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KubernetesConfiguration/help/New-AzKubernetesExtension.md
ms.openlocfilehash: 5a629b16a49e98847b18ae9172b54b66be636586
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142084405"
---
# New-AzKubernetesExtension

## SYNOPSIS
Buat Ekstensi Kluster Kubernetes baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.kubernetesconfiguration/new-azkubernetesextension) untuk informasi terbaru.

## SYNTAX

```
New-AzKubernetesExtension -ClusterName <String> -ClusterType <String> -Name <String>
 -ResourceGroupName <String> -ExtensionType <String> [-SubscriptionId <String>]
 [-AkAssignedIdentityType <ResourceIdentityType>] [-AutoUpgradeMinorVersion]
 [-ClusterReleaseNamespace <String>] [-ConfigurationProtectedSetting <Hashtable>]
 [-ConfigurationSetting <Hashtable>] [-IdentityType <ResourceIdentityType>]
 [-NamespaceTargetNamespace <String>] [-ReleaseTrain <String>] [-Version <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat Ekstensi Kluster Kubernetes baru.

## EXAMPLES

### Contoh 1: Create a new Kubernetes Cluster Extension.
```powershell
PS C:\> New-AzKubernetesExtension -ClusterName azps_test_cluster -ClusterType ConnectedClusters -Name azps_test_extension -ResourceGroupName azps_test_group -ExtensionType Microsoft.Arcdataservices

Name                ExtensionType             Version      ProvisioningState AutoUpgradeMinorVersion ReleaseTrain ResourceGroupName
----                -------------             -------      ----------------- ----------------------- ------------ -----------------
azps_test_extension microsoft.arcdataservices 1.0.16701001 Succeeded         True                    Stable       azps_test_group
```

Buat Ekstensi Kluster Kubernetes baru.

## PARAMETERS

### -AkAssignedIdentityType
Tipe identitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Support.ResourceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterReleaseNamespace
Ruang nama tempat Rilis ekstensi harus diletakkan, untuk ekstensi Kluster yang tercakup.
Jika ruang nama ini tidak ada, ruang nama ini akan dibuat

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

### -ClusterType
Nama sumber daya kluster Kubernetes - baik managedClusters (untuk kluster AKS) atau ConnectedClusters (untuk kluster OnPrem K8S).

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

### -ExtensionType
Tipe Ekstensi, di mana sumber daya ini merupakan contohnya.
Ini harus menjadi salah satu Tipe Ekstensi yang terdaftar di Microsoft.KubernetesConfiguration oleh penerbit Ekstensi.

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

### -IdentityType
Tipe identitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Support.ResourceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NamespaceTargetNamespace
Ruang nama tempat ekstensi akan dibuat untuk ekstensi ruang nama yang dilingkup.
Jika ruang nama ini tidak ada, ruang nama ini akan dibuat

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.KubernetesConfiguration.Models.Api20210901.IExtension

## CATATAN

ALIAS

New-AzK8sExtension

## RELATED LINKS

