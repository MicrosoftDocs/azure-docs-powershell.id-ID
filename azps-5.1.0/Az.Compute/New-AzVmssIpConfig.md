---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 92F192A5-F75E-4EFE-B2D2-B0DF0B78D3B5
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/new-azvmssipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/New-AzVmssIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/New-AzVmssIpConfig.md
ms.openlocfilehash: e2ca08746ab9b4dc2ef2265a59cdab00ac42cf33
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136023019"
---
# New-AzVmssIpConfig

## SYNOPSIS
Membuat konfigurasi IP untuk antarmuka jaringan VMSS.

## SINTAKS

```
New-AzVmssIpConfig [[-Name] <String>] [[-Id] <String>] [[-SubnetId] <String>]
 [[-ApplicationGatewayBackendAddressPoolsId] <String[]>] [[-LoadBalancerBackendAddressPoolsId] <String[]>]
 [[-LoadBalancerInboundNatPoolsId] <String[]>] [-Primary] [-PrivateIPAddressVersion <String>]
 [-PublicIPAddressConfigurationName <String>] [-PublicIPAddressConfigurationIdleTimeoutInMinutes <Int32>]
 [-DnsSetting <String>] [-IpTag <VirtualMachineScaleSetIpTag[]>] [-PublicIPPrefix <String>]
 [-PublicIPAddressVersion <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzVmssIpConfig** membuat objek konfigurasi IP untuk antarmuka jaringan Virtual Machine Scale Set (VMSS).
Tentukan konfigurasi dari cmdlet ini sebagai parameter *IPConfiguration* cmdlet Add-AzVmssNetworkInterfaceConfiguration cmdlet.

## CONTOH

### Contoh 1: Membuat objek konfigurasi IP untuk antarmuka VMSS
```
PS C:\> $IPConfiguration = New-AzVmssIPConfig -Name "ContosoVmssInterface02" -SubnetId $SubnetId
```

Perintah ini membuat objek konfigurasi IP bernama ContosoVmssInterface02.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi di variabel $IPConfiguration untuk digunakan nanti dengan **Add-AzVmssNetworkInterfaceConfiguration**.

### Contoh 2: Buat objek konfigurasi IP yang mencakup pengaturan pool NAT
```
PS C:\> $IPConfiguration = New-AzVmssIPConfig -Name "ContosoVmssInterface03" -LoadBalancerInboundNatPoolsId $expectedLb.InboundNatPools[0].Id -LoadBalancerBackendAddressPoolsId $expectedLb.BackendAddressPools[0].Id -SubnetId $SubnetId
```

Perintah ini akan membuat objek konfigurasi IP bernama ContosoVmssInterface03, lalu menyimpannya dalam variabel $IPConfiguration untuk digunakan nanti.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi di variabel $IPConfiguration digunakan nanti.
Perintah menentukan nilai untuk parameter *LoadBalancerInboundNatPoolsId* dan *LoadBalancerBackendAddressPoolsId.*

## PARAMETERS

### -ApplicationGatewayBackendAddressPoolsId
Menentukan array referensi ke alamat backend yang memuat keseimbangan.
Kumpulan skala bisa merujuk ke kolam renang alamat backend dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DnsSetting
Pengaturan dns yang akan diterapkan pada alamat publicIP.
Label nama domain dari pengaturan Dns yang akan diterapkan pada alamat publicIP.
Penggabungan label nama domain dan indeks vm akan menjadi label nama domain dari sumber daya Alamat IP Publik yang akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PublicIPAddressDomainNameLabel

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Menentukan ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpTag
Menentukan array objek Tag Ip.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIpTag[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerBackendAddressPoolsId
Menentukan array referensi ke kolam renang nat alamat jaringan masuk (NAT, Incoming Network Address Translation) dari keseimbangan muat.
Kumpulan skala dapat merujuk ke kolam renang NAT yang masuk dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancerInboundNatPoolsId
Menentukan array referensi ke kolam renang NAT yang masuk dari keseimbangan muat.
Kumpulan skala dapat merujuk ke kolam renang NAT yang masuk dari satu publik dan satu penyeimbang muat internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muat yang sama.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi IP.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Utama
Menentukan Konfigurasi IP utama jika antarmuka jaringan memiliki lebih dari satu Konfigurasi IP.

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

### -PrivateIPAddressVersion
Tentukan konfigurasi IP untuk alamat IP privat.  Default dianggap sebagai IPv4.  Nilai yang mungkin adalah: 'IPv4' dan 'IPv6'.

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

### -PublicIPAddressConfigurationIdleTimeoutInMinutes
Waktu diam habis dari alamat IP publik.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: PublicIPAddressIdleTimeoutInMinutes

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIPAddressConfigurationName
Nama konfigurasi alamat publicIP.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PublicIPAddressName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicIPAddressVersion
Tentukan konfigurasi IP untuk alamat IP publik.  Default dianggap sebagai IPv4.  Nilai yang mungkin adalah: 'IPv4' dan 'IPv6'.

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

### -PublicIPPrefix
ID Prefiks IP Publik

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

### -SubnetId
Menentukan ID subnet yang digunakan untuk membuat antarmuka jaringan VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

## INPUT

### System.String

### System.String[]

### System.Int32

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIpTag[]

## OUTPUT

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIPConfiguration

## CATATAN

## LINK TERKAIT

[Add-AzVmssNetworkInterfaceConfiguration](./Add-AzVmssNetworkInterfaceConfiguration.md)


