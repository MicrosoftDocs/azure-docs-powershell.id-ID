---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/New-AzRecoveryServicesAsrVMNicConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
ms.openlocfilehash: a62b8306fd284cfb2edb711755614cd79a2538ff
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145648894"
---
# New-AzRecoveryServicesAsrVMNicConfig

## SYNOPSIS
Membuat konfigurasi ASR NIC yang berisi failover dan detail konfigurasi terkait failover pengujian.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/new-azrecoveryservicesasrvmnicconfig) untuk informasi terbaru.

## SYNTAX

```
New-AzRecoveryServicesAsrVMNicConfig -NicId <String> -ReplicationProtectedItem <ASRReplicationProtectedItem>
 [-RecoveryVMNetworkId <String>] [-RecoveryNicName <String>] [-RecoveryNicResourceGroupName <String>]
 [-ReuseExistingNic] [-RecoveryNetworkSecurityGroupId <String>] [-EnableAcceleratedNetworkingOnRecovery]
 [-TfoVMNetworkId <String>] [-TfoNicName <String>] [-TfoNicResourceGroupName <String>] [-TfoReuseExistingNic]
 [-TfoNetworkSecurityGroupId <String>] [-EnableAcceleratedNetworkingOnTfo]
 [-IPConfig <PSIPConfigInputDetails[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesAsrVMNicConfig** membuat objek konfigurasi ASR NIC yang berisi detail terkait failover dan pengujian failover. Jika informasi apa pun tidak diteruskan, nilai terkait dipilih dari item yang dilindungi replikasi untuk menghindari nilai-nilai ini diperbarui ke null.

> [!IMPORTANT]
> Kami telah menghentikan parameter yang sesuai dengan Konfigurasi IP dari cmdlet, dan merangkumnya ke dalam objek cmdlet baru. Buat objek baru menggunakan cmdlet **New-AzRecoveryServicesAsrVMNicIPConfig** dan teruskan sebagai parameter. Silakan lihat contoh di bawah ini untuk lebih jelasnya.

## EXAMPLES

### Contoh 1
```powershell
$ipConfig1 = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig1" -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.10" -TfoStaticIPAddress "10.3.4.33"
$ipConfig2 = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig2" -IsSelectedForFailover -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.13" -TfoStaticIPAddress "10.3.4.32"
$ipConfigs = @($ipConfig1, $ipConfig2)
$nicConfig = New-AzRecoveryServicesAsrVMNicConfig -NicId $AsrNicGuid -ReplicationProtectedItem $Rpi -RecoveryVMNetworkId $recoveryNetworkId `
    -TfoVMNetworkId $tfoNetworkId -IPConfig $ipConfigs
```

Membuat objek ASRVmNicConfig dengan pengaturan jaringan failover dan pengujian failover yang dikonfigurasi untuk NIC. Properti apa pun yang tidak diteruskan di atas diambil dari item yang dilindungi yang diteruskan.

### Contoh 2
```powershell
$nicConfig = New-AzRecoveryServicesAsrVMNicConfig -NicId $AsrNicGuid -ReplicationProtectedItem $Rpi -TfoNicName $TfoNicName -TfoNicResourceGroupName $TfoNicRgName -TfoReuseExistingNic
```

Membuat objek ASRVmNicConfig dengan pengaturan jaringan faiover pengujian yang dikonfigurasi untuk penggantian nama NIC. Properti apa pun yang tidak diteruskan di atas diambil dari item yang dilindungi yang diteruskan.

## PARAMETERS

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

### -EnableAcceleratedNetworkingOnRecovery
Menentukan apakah jaringan yang dipercepat diaktifkan pada NIC pemulihan.

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

### -EnableAcceleratedNetworkingOnTfo
Menentukan apakah jaringan yang dipercepat diaktifkan pada uji failover NIC.

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

### -IPConfig
Menentukan pengaturan failover/failover pengujian konfigurasi IP NIC.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.PSIPConfigInputDetails[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NicId
Tentukan ASR NIC GUID.

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

### -RecoveryNetworkSecurityGroupId
Menentukan ID NSG yang terkait dengan pemulihan NIC.

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

### -RecoveryNicName
Menentukan nama NIC pemulihan.

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

### -RecoveryNicResourceGroupName
Menentukan nama grup sumber daya NIC pemulihan.

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

### -RecoveryVMNetworkId
Menentukan ID jaringan virtual pemulihan.

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

### -ReplicationProtectedItem
Tentukan Item yang Dilindungi Replikasi ASR.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRReplicationProtectedItem
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReuseExistingNic
Menentukan apakah NIC yang ada dapat digunakan selama failover.

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

### -TfoNetworkSecurityGroupId
Menentukan ID NSG yang terkait dengan uji failover NIC.

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

### -TfoNicName
Menentukan nama uji failover NIC.

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

### -TfoNicResourceGroupName
Menentukan nama grup sumber daya NIC failover pengujian.

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

### -TfoReuseExistingNic
Menentukan apakah NIC yang ada dapat digunakan selama pengujian failover.

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

### -TfoVMNetworkId
Menentukan ID jaringan virtual failover pengujian.

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMNicConfig

## NOTES

## RELATED LINKS
