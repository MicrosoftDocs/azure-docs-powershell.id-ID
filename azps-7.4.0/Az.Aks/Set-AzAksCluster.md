---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Aks.dll-Help.xml
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/set-azakscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Set-AzAksCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Set-AzAksCluster.md
ms.openlocfilehash: 4d97fc48251dc8ac2463b066d7670b6ceceba1cf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142688680"
---
# Set-AzAksCluster

## SYNOPSIS
Memperbarui atau membuat kluster Kubernetes terkelola.

## SYNTAX

### defaultParameterSet (Default)
```
Set-AzAksCluster [-NodePoolMode <String>] [-AcrNameToDetach <String>] [-NodeImageOnly] [-ControlPlaneOnly]
 [-ResourceGroupName] <String> [-Name] <String> [[-ServicePrincipalIdAndSecret] <PSCredential>]
 [-Location <String>] [-LinuxProfileAdminUserName <String>] [-DnsNamePrefix <String>]
 [-KubernetesVersion <String>] [-NodeName <String>] [-NodeMinCount <Int32>] [-NodeMaxCount <Int32>]
 [-EnableNodeAutoScaling] [-NodeCount <Int32>] [-NodeOsDiskSize <Int32>] [-NodeVmSize <String>]
 [-SshKeyValue <String>] [-AcrNameToAttach <String>] [-AsJob] [-Tag <Hashtable>]
 [-LoadBalancerAllocatedOutboundPort <Int32>] [-LoadBalancerManagedOutboundIpCount <Int32>]
 [-LoadBalancerOutboundIp <String[]>] [-LoadBalancerOutboundIpPrefix <String[]>]
 [-LoadBalancerIdleTimeoutInMinute <Int32>] [-ApiServerAccessAuthorizedIpRange <String[]>]
 [-EnableApiServerAccessPrivateCluster] [-ApiServerAccessPrivateDnsZone <String>]
 [-EnableApiServerAccessPrivateClusterPublicFQDN] [-FqdnSubdomain <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### InputObjectParameterSet
```
Set-AzAksCluster -InputObject <PSKubernetesCluster> [-NodePoolMode <String>] [-AcrNameToDetach <String>]
 [-NodeImageOnly] [-ControlPlaneOnly] [-Location <String>] [-LinuxProfileAdminUserName <String>]
 [-DnsNamePrefix <String>] [-KubernetesVersion <String>] [-NodeName <String>] [-NodeMinCount <Int32>]
 [-NodeMaxCount <Int32>] [-EnableNodeAutoScaling] [-NodeCount <Int32>] [-NodeOsDiskSize <Int32>]
 [-NodeVmSize <String>] [-SshKeyValue <String>] [-AcrNameToAttach <String>] [-AsJob] [-Tag <Hashtable>]
 [-LoadBalancerAllocatedOutboundPort <Int32>] [-LoadBalancerManagedOutboundIpCount <Int32>]
 [-LoadBalancerOutboundIp <String[]>] [-LoadBalancerOutboundIpPrefix <String[]>]
 [-LoadBalancerIdleTimeoutInMinute <Int32>] [-ApiServerAccessAuthorizedIpRange <String[]>]
 [-EnableApiServerAccessPrivateCluster] [-ApiServerAccessPrivateDnsZone <String>]
 [-EnableApiServerAccessPrivateClusterPublicFQDN] [-FqdnSubdomain <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### IdParameterSet
```
Set-AzAksCluster [-NodePoolMode <String>] [-AcrNameToDetach <String>] [-NodeImageOnly] [-ControlPlaneOnly]
 [-Id] <String> [-Location <String>] [-LinuxProfileAdminUserName <String>] [-DnsNamePrefix <String>]
 [-KubernetesVersion <String>] [-NodeName <String>] [-NodeMinCount <Int32>] [-NodeMaxCount <Int32>]
 [-EnableNodeAutoScaling] [-NodeCount <Int32>] [-NodeOsDiskSize <Int32>] [-NodeVmSize <String>]
 [-SshKeyValue <String>] [-AcrNameToAttach <String>] [-AsJob] [-Tag <Hashtable>]
 [-LoadBalancerAllocatedOutboundPort <Int32>] [-LoadBalancerManagedOutboundIpCount <Int32>]
 [-LoadBalancerOutboundIp <String[]>] [-LoadBalancerOutboundIpPrefix <String[]>]
 [-LoadBalancerIdleTimeoutInMinute <Int32>] [-ApiServerAccessAuthorizedIpRange <String[]>]
 [-EnableApiServerAccessPrivateCluster] [-ApiServerAccessPrivateDnsZone <String>]
 [-EnableApiServerAccessPrivateClusterPublicFQDN] [-FqdnSubdomain <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui atau membuat kluster Kubernetes terkelola.

## EXAMPLES

### Contoh 1
```powershell
Get-AzAksCluster -ResourceGroupName group -Name myCluster | Set-AzAksCluster -NodeCount 5
```

Atur jumlah node dalam kluster Kubernetes menjadi 5.

## PARAMETERS

### -AcrNameToAttach
Berikan peran 'acrpull' dari ACR yang ditentukan untuk AKS Service Principal, misalnya myacr

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

### -AcrNameToDetach
Menonaktifkan penetapan peran 'acrpull' ke ACR yang ditentukan menurut nama atau ID sumber daya, misalnya myacr

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

### -ApiServerAccessAuthorizedIpRange
Rentang IP yang diotorisasi untuk mengakses server API Kubernetes.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApiServerAccessPrivateDnsZone
Mode zona DNS pribadi untuk kluster.

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

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -ControlPlaneOnly
Hanya akan meningkatkan pesawat kontrol ke versi target.

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

### -DnsNamePrefix
Prefiks nama DNS untuk kluster.

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

### -EnableApiServerAccessPrivateCluster
Apakah akan membuat kluster sebagai kluster privat atau tidak.

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

### -EnableApiServerAccessPrivateClusterPublicFQDN
Apakah akan membuat FQDN publik tambahan untuk klaster privat atau tidak.

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

### -EnableNodeAutoScaling
Apakah mengaktifkan penskalakan otomatis

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

### -FqdnSubdomain
Subdomain FQDN dari kluster privat dengan zona dns pribadi kustom.

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

### -Id
Id dari kluster Kubernetes yang dikelola

```yaml
Type: System.String
Parameter Sets: IdParameterSet
Aliases: ResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Sebuah objek PSKubernetesCluster, biasanya melewati pipeline.

```yaml
Type: Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KubernetesVersion
Versi Kubernetes yang digunakan untuk membuat kluster.

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

### -LinuxProfileAdminUserName
Nama pengguna untuk Virtual Machines Linux.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AdminUserName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerAllocatedOutboundPort
Jumlah port SNAT yang dialokasikan per VM yang diinginkan.

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

### -LoadBalancerIdleTimeoutInMinute
Waktu habis aliran keluar yang diinginkan habis dalam hitungan menit.

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

### -LoadBalancerManagedOutboundIpCount
Jumlah IP keluar terkelola yang diinginkan untuk kluster load balancer.

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

### -LoadBalancerOutboundIp
Sumber daya IP keluar yang diinginkan untuk kluster load balancer.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerOutboundIpPrefix
Sumber daya Outbound IP Prefix yang diinginkan untuk kluster load balancer.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Azure untuk kluster.
Default ke lokasi grup sumber daya.

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
Nama kluster terkelola Kubernetes.

```yaml
Type: System.String
Parameter Sets: defaultParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeCount
Jumlah node default untuk kumpulan simpul.

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

### -NodeImageOnly
Hanya akan memutakhirkan versi node pool untuk meratakan bidang kontrol.

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

### -NodeMaxCount
Jumlah node maksimum untuk penskalaan otomatis

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

### -NodeMinCount
Jumlah node minimum untuk penskalaan otomatis.

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

### -NodeName
Nama unik profil kumpulan agen dalam konteks langganan dan grup sumber daya.

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

### -NodeOsDiskSize
Menentukan ukuran, dalam GB, disk sistem operasi.

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

### -NodePoolMode
NodePoolMode mewakili mode kumpulan simpul.

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

### -NodeVmSize
Ukuran Mesin Virtual.

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
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: defaultParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipalIdAndSecret
Id klien dan rahasia klien yang terkait dengan aplikasi AAD / prinsipal layanan.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: defaultParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshKeyValue
Nilai file kunci SSH atau jalur file kunci.
Default ke {HOME}/.ssh/id_rsa.pub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SshKeyPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengesampingkan langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak mempengaruhi cmdlet berikutnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tag yang akan diterapkan ke sumber daya

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

### Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster

## NOTES

## RELATED LINKS
