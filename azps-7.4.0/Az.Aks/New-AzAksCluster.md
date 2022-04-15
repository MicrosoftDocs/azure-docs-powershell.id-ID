---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Aks.dll-Help.xml
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/new-azakscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/New-AzAksCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/New-AzAksCluster.md
ms.openlocfilehash: 7f4371c916047bb2293d6fe0257a5a8d3eac0e08
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142427387"
---
# New-AzAksCluster

## SYNOPSIS
Buat kluster Kubernetes terkelola baru.

Cmdlet dapat memanggil di bawah Api Graph Microsoft sesuai dengan parameter input:

- POST /servicePrincipals

## SYNTAX

```
New-AzAksCluster [-NodeVmSetType <String>] [-NodeVnetSubnetID <String>] [-NodeMaxPodCount <Int32>]
 [-NodeSetPriority <String>] [-NodePoolMode <String>] [-NodeScaleSetEvictionPolicy <String>]
 [-AddOnNameToBeEnabled <String[]>] [-WorkspaceResourceId <String>] [-SubnetName <String>] [-EnableRbac]
 [-WindowsProfileAdminUserName <String>] [-WindowsProfileAdminUserPassword <SecureString>]
 [-NetworkPlugin <String>] [-NetworkPolicy <String>] [-PodCidr <String>] [-ServiceCidr <String>]
 [-DnsServiceIP <String>] [-DockerBridgeCidr <String>] [-NodePoolLabel <Hashtable>]
 [-AksCustomHeader <Hashtable>] [-LoadBalancerSku <String>] [-Force] [-GenerateSshKey] [-EnableNodePublicIp]
 [-NodePublicIPPrefixID <String>] [-ResourceGroupName] <String> [-Name] <String>
 [[-ServicePrincipalIdAndSecret] <PSCredential>] [-Location <String>] [-LinuxProfileAdminUserName <String>]
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

## DESCRIPTION

Buat klaster Azure Kubernetes Service(AKS) baru.

## EXAMPLES

### Baru AKS dengan param default.

```powershell
New-AzAksCluster -ResourceGroupName myResourceGroup -Name myCluster
```

### Buat kontainer Server Windows di AKS.
Untuk membuat kontainer server Windows di AKS, Anda harus menentukan setidaknya empat parameter berikut ini saat membuat AKS, dan nilai untuk `NetworkPlugin` dan `NodeVmSetType` harus `azure` serta `VirtualMachineScaleSets` masing-masing.
`-WindowsProfileAdminUserName *** -WindowsProfileAdminUserPassword *** -NetworkPlugin azure -NodeVmSetType VirtualMachineScaleSets`

```powershell
$cred = ConvertTo-SecureString -AsPlainText "Password!!123" -Force
New-AzAksCluster -ResourceGroupName myResourceGroup -Name myCluster -WindowsProfileAdminUserName azureuser -WindowsProfileAdminUserPassword $cred -NetworkPlugin azure -NodeVmSetType VirtualMachineScaleSets
New-AzAksNodePool -ResourceGroupName myResourceGroup -ClusterName myCluster -Name win1 -OsType Windows -VmSetType VirtualMachineScaleSets
```

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

### -AddOnNameToBeEnabled
Nama add-on yang akan diaktifkan saat kluster dibuat.

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

### -AksCustomHeader
Aks header kustom yang digunakan untuk membangun jaringan Kubernetes.

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
Prefiks nama DNS untuk kluster. Panjangnya harus <= 9 jika pengguna berencana menambahkan wadah windows.

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

### -DnsServiceIP
IP layanan DNS yang digunakan untuk membangun jaringan Kubernetes.

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

### -DockerBridgeCidr
Docker bridge cidr digunakan untuk membangun jaringan Kubernetes.

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

### -EnableNodePublicIp
Apakah mengaktifkan IP publik untuk node.

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

### -EnableRbac
Apakah mengaktifkan Kubernetes Role-Based Access

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

### -Paksa
Buat kluster meskipun sudah ada

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

### -GenerateSshKey
Hasilkan file kunci ssh ke {HOME}/.ssh/id_rsa.

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

### -LoadBalancersku
Sku load balancer untuk kluster yang dikelola.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkPlugin
Plugin jaringan yang digunakan untuk membangun jaringan Kubernetes.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: azure
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkPolicy
Kebijakan jaringan yang digunakan untuk membangun jaringan Kubernetes.

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

### -NodeMaxPodCount
Jumlah maksimum pod yang dapat dijalankan pada node.

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
Ukuran dalam GB disk OS untuk setiap simpul dalam kumpulan simpul. Minimal 30 GB.

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

### -NodePoolLabel
Node pool label yang digunakan untuk membangun jaringan Kubernetes.

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

### -NodePublicIPPrefixID
Id sumber daya prefiks IP publik untuk kumpulan simpul.

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

### -NodeScaleSetEvictionPolicy
ScaleSetEvictionPolicy yang akan digunakan untuk menentukan kebijakan penggusuran untuk kumpulan skala mesin virtual prioritas rendah. Default ke Hapus.

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

### -NodeSetPriority
ScaleSetPriority yang akan digunakan untuk menentukan prioritas rangkaian skala mesin virtual. Default ke reguler.

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

### -NodeVmSetType
AgentPoolType mewakili tipe kumpulan agen. Nilai yang memungkinkan termasuk: 'VirtualMachineScaleSets', 'AvailabilitySet'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: VirtualMachineScaleSets
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeVmSize
Ukuran Mesin Virtual. Nilai default adalah Standard_D2_v2.

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

### -NodeVnetSubnetID
VNet SubnetID menentukan pengidentifikasi subnet VNet.

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

### -PodCidr
Pod cidr digunakan untuk membangun jaringan Kubernetes.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceCidr
Service cidr digunakan untuk membangun jaringan Kubernetes.

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

### -ServicePrincipalIdAndSecret
Id klien dan rahasia klien yang terkait dengan aplikasi AAD / prinsipal layanan.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
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

### -SubnetName
Nama subnet add-on VirtualNode.

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

### -WindowsProfileAdminUserName
Nama pengguna administrator yang digunakan untuk Windows VM.

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

### -WindowsProfileAdminUserPassword
Kata sandi administrator untuk digunakan untuk Windows VM, panjangnya harus setidaknya 12, berisi setidaknya satu karakter huruf kecil, yaitu `[a-z]`, satu `[A-Z]` dan satu karakter `[!@#$%^&*()]`khusus .

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceResourceId
Id Sumber Daya ruang kerja add-on Pemantauan.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Aks.Models.PSKubernetesCluster

## CATATAN

## RELATED LINKS
