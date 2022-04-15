---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 92F192A5-F75E-4EFE-B2D2-B0DF0B78D3B5
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/new-azurermvmssipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVmssIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVmssIpConfig.md
ms.openlocfilehash: 9c49fd381e1f63d60332eb42759cfb9dd187fbf5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142282502"
---
# New-AzureRmVmssIpConfig

## SYNOPSIS
Membuat konfigurasi IP untuk antarmuka jaringan VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmVmssIpConfig [[-Name] <String>] [[-Id] <String>] [[-SubnetId] <String>]
 [[-ApplicationGatewayBackendAddressPoolsId] <String[]>] [[-LoadBalancerBackendAddressPoolsId] <String[]>]
 [[-LoadBalancerInboundNatPoolsId] <String[]>] [-Primary] [-PrivateIPAddressVersion <String>]
 [-PublicIPAddressConfigurationName <String>] [-PublicIPAddressConfigurationIdleTimeoutInMinutes <Int32>]
 [-DnsSetting <String>] [-IpTag <VirtualMachineScaleSetIpTag[]>] [-PublicIPPrefix <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmVmssIpConfig** membuat objek konfigurasi IP untuk antarmuka jaringan Kumpulan Skala Mesin Virtual (VMSS).
Tentukan konfigurasi dari cmdlet ini sebagai parameter *KONFIGURASI IP* cmdlet Add-AzureRmVmssNetworkInterfaceConfiguration.

## EXAMPLES

### Contoh 1: Membuat objek konfigurasi IP untuk antarmuka VMSS
```
PS C:\> $IPConfiguration = New-AzureRmVmssIPConfig -Name "ContosoVmssInterface02" -SubnetId $SubnetId
```

Perintah ini membuat objek konfigurasi IP bernama ContosoVmssInterface02.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi dalam variabel $IPConfiguration untuk digunakan nanti dengan **Add-AzureRmVmssNetworkInterfaceConfiguration**.

### Contoh 2: Membuat objek konfigurasi IP yang menyertakan pengaturan kumpulan NAT
```
PS C:\> $IPConfiguration = New-AzureRmVmssIPConfig -Name "ContosoVmssInterface03" -LoadBalancerInboundNatPoolsId $expectedLb.InboundNatPools[0].Id -LoadBalancerBackendAddressPoolsId $expectedLb.BackendAddressPools[0].Id -SubnetId $SubnetId
```

Perintah ini membuat objek konfigurasi IP bernama ContosoVmssInterface03, lalu menyimpannya dalam variabel $IPConfiguration untuk digunakan nanti.
Perintah menggunakan ID subnet yang ditentukan sebelumnya yang disimpan di $SubnetId.
Perintah menyimpan pengaturan konfigurasi dalam variabel $IPConfiguration untuk digunakan nanti.
Perintah menentukan nilai untuk parameter *LoadBalancerInboundNatPoolsId* dan *LoadBalancerBackendAddressPoolsId* .

## PARAMETERS

### -ApplicationGatewayBackendAddressPoolsId
Menentukan array referensi ke kumpulan alamat backend dari load balancer.
Kumpulan skala dapat mereferensikan kumpulan alamat backend dari satu publik dan satu penyeimbang muatan internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muatan yang sama.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsSetting
Pengaturan dns yang akan diterapkan pada alamat publicIP.
Label nama domain pengaturan Dns yang akan diterapkan pada alamat publicIP.
Penggambatan label nama domain dan indeks vm akan menjadi label nama domain sumber daya Alamat IP Publik yang akan dibuat.

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
Menentukan array referensi ke kumpulan penerjemahan alamat jaringan masuk (NAT) dari penyeimbang muatan.
Kumpulan skala dapat mereferensikan kumpulan NAT masuk dari satu publik dan satu penyeimbang muatan internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muatan yang sama.

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
Menentukan array referensi ke kumpulan NAT masuk dari penyeimbang muatan.
Kumpulan skala dapat mereferensikan kumpulan NAT masuk dari satu publik dan satu penyeimbang muatan internal.
Beberapa kumpulan skala tidak dapat menggunakan penyeimbang muatan yang sama.

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

### -Primer
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
Tentukan konfigurasi ip adalah IPv4 atau IPv6. Default diambil sebagai IPv4.  Nilai yang memungkinkan adalah: 'IPv4' dan 'IPv6'.

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
Waktu habis menganggur alamat IP publik.

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
Menentukan ID subnet tempat konfigurasi membuat antarmuka jaringan VMSS.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Int32

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIpTag[]

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSetIPConfiguration

## CATATAN

## RELATED LINKS

[Add-AzureRmVmssNetworkInterfaceConfiguration](./Add-AzureRmVmssNetworkInterfaceConfiguration.md)


