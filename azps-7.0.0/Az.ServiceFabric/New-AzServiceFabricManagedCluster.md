---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ServiceFabric.dll-Help.xml
Module Name: Az.ServiceFabric
online version: https://docs.microsoft.com/powershell/module/az.servicefabric/new-azservicefabricmanagedcluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceFabric/ServiceFabric/help/New-AzServiceFabricManagedCluster.md
ms.openlocfilehash: e3aeeaddaa8bb7a574eb0dbfe732b04f87854369
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136546961"
---
# New-AzServiceFabricManagedCluster

## SYNOPSIS
Membuat kluster terkelola baru.

## SYNTAX

### ClientCertByTp (Default)
```
New-AzServiceFabricManagedCluster [-ResourceGroupName] <String> [-Name] <String> -Location <String>
 [-UpgradeMode <ClusterUpgradeMode>] [-CodeVersion <String>] [-UpgradeCadence <PSClusterUpgradeCadence>]
 [-ClientCertIsAdmin] -ClientCertThumbprint <String> -AdminPassword <SecureString> [-AdminUserName <String>]
 [-HttpGatewayConnectionPort <Int32>] [-ClientConnectionPort <Int32>] [-DnsName <String>]
 [-Sku <ManagedClusterSku>] [-UseTestExtension] [-ZonalResiliency] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientCertByCn
```
New-AzServiceFabricManagedCluster [-ResourceGroupName] <String> [-Name] <String> -Location <String>
 [-UpgradeMode <ClusterUpgradeMode>] [-CodeVersion <String>] [-UpgradeCadence <PSClusterUpgradeCadence>]
 [-ClientCertIsAdmin] -ClientCertCommonName <String> [-ClientCertIssuerThumbprint <String[]>]
 -AdminPassword <SecureString> [-AdminUserName <String>] [-HttpGatewayConnectionPort <Int32>]
 [-ClientConnectionPort <Int32>] [-DnsName <String>] [-Sku <ManagedClusterSku>] [-UseTestExtension]
 [-ZonalResiliency] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini akan membuat sumber daya kluster terkelola tanpa tipe node. Untuk bootstrap tipe node utama A harus ditambahkan menggunakan [New-AzServiceFabricManagedNodeType](./New-AzServiceFabricManagedNodeType.md).

## EXAMPLES

### Contoh 1
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$password = ConvertTo-SecureString -AsPlainText -Force "testpass1234!@#$"
New-AzServiceFabricManagedCluster -ResourceGroupName $rgName -Location centraluseuap -ClusterName $clusterName -AdminPassword $password -Verbose
```

Perintah ini membuat sumber daya kluster dengan sku dasar default.

### Contoh 2
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$password = ConvertTo-SecureString -AsPlainText -Force "testpass1234!@#$"
New-AzServiceFabricManagedCluster -ResourceGroupName $rgName -Location centraluseuap -ClusterName $clusterName -ClientCertThumbprint XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX -ClientCertIsAdmin -AdminPassword $password -Sku Standard -Verbose
```

Perintah ini membuat sumber daya kluster di centraluseuap dengan sertifikat klien admin awal dan sku standar.

### Contoh 3
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$password = ConvertTo-SecureString -AsPlainText -Force "testpass1234!@#$"
New-AzServiceFabricManagedCluster -ResourceGroupName $rgName -Location centraluseuap -ClusterName $clusterName -AdminPassword $password -Sku Standard -UpgradeMode Automatic -UpgradeCadence Wave1 -ZonalResiliency -Verbose
```

Perintah ini membuat kluster dengan irama pemutakhiran dalam gelombang1 dan ketahanan zonal yang diaktifkan.

### Contoh 4
```powershell
$rgName = "testRG"
$clusterName = "testCluster"
$password = ConvertTo-SecureString -AsPlainText -Force "testpass1234!@#$"
New-AzServiceFabricManagedCluster -ResourceGroupName $rgName -Location centraluseuap -ClusterName $clusterName -AdminPassword $password -Sku Standard -UpgradeMode Manual -CodeVersion 7.2.477.9590 -Verbose
```

Perintah ini membuat kluster dengan mode pemutakhiran manual dan versi kode 7.2.477.9590.

## PARAMETERS

### -AdminPassword
Kata sandi admin yang digunakan untuk mesin virtual.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminUserName
Kata sandi admin yang digunakan untuk mesin virtual.
Default: vmadmin.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "vmadmin"
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

### -ClientCertCommonName
Nama umum sertifikat klien.

```yaml
Type: System.String
Parameter Sets: ClientCertByCn
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertIsAdmin
Gunakan untuk menentukan jika sertifikat klien memiliki tingkat administrator.

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

### -ClientCertIssuerThumbprint
Daftar thumbprint Penerbit untuk sertifikat klien.
Hanya gunakan dalam kombinasi dengan ClientCertCommonName.

```yaml
Type: System.String[]
Parameter Sets: ClientCertByCn
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertThumbprint
Thumbprint sertifikat klien.

```yaml
Type: System.String
Parameter Sets: ClientCertByTp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientConnectionPort
Port yang digunakan untuk koneksi klien ke kluster.
Default: 19000.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 19000
Accept pipeline input: False
Accept wildcard characters: False
```

### -CodeVersion
Cluster service fabric code version.
Hanya gunakan jika mode pemutakhiran manual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClusterCodeVersion

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

### -DnsName
Nama dns kluster.

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

### -httpGatewayConnectionPort
Port digunakan untuk koneksi http ke kluster.
Default: 19080.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 19080
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Tentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
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

### -Sku
Kluster Sku, opsinya adalah Dasar: layanan akan memiliki minimal 3 node awal dan hanya mengizinkan 1 tipe node dan Standar: layanan akan memiliki minimal 5 node awal dan mengizinkan beberapa tipe node.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.ManagedClusterSku
Parameter Sets: (All)
Aliases:
Accepted values: Basic, Standard

Required: False
Position: Named
Default value: Basic
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeCadence
Menunjukkan kapan pemutakhiran versi runtime kluster baru akan diterapkan setelah dirilis. Secara default adalah Wave0.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.PSClusterUpgradeCadence
Parameter Sets: (All)
Aliases: ClusterUpgradeCadence
Accepted values: Wave0, Wave1, Wave2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradeMode
Cluster service fabric code version upgrade mode.
Otomatis atau Manual.

```yaml
Type: Microsoft.Azure.Commands.ServiceFabric.Models.ClusterUpgradeMode
Parameter Sets: (All)
Aliases: ClusterUpgradeMode
Accepted values: Automatic, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTestExtension
Jika Tentukan Kluster akan dikurasi dengan ekstensi vmss uji layanan.

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

### -ZonalResiliency
Menunjukkan jika kluster memiliki resiliensi zona.

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

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSManagedCluster

## CATATAN

## RELATED LINKS

[New-AzServiceFabricManagedNodeType](./New-AzServiceFabricManagedNodeType.md)