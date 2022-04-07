---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/New-AzRecoveryServicesAsrVMNicConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
ms.openlocfilehash: 659a049180e63c0ae66a4781fa15e238bd28626a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140391719"
---
# New-AzRecoveryServicesAsrVMNicConfig

## SYNOPSIS
Membuat konfigurasi NIC ASR yang berisi detail konfigurasi terkait failover dan test failover.

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
Cmdlet **New-AzRecoveryServicesAsrVMNicConfig** membuat objek konfigurasi ASR NIC yang berisi detail terkait failover dan test failover. Dalam kasus semua informasi tidak diberikan, nilai yang terkait diambil dari replikasi item yang diproteksi untuk menghindari nilai-nilai ini diperbarui menjadi null.

> [!IMPORTANT]
> Kami telah menolak parameter yang terkait dengan Konfigurasi IP dari cmdlet, dan encapsulated parameter ke dalam objek cmdlet baru. Silakan buat objek baru menggunakan cmdlet **New-AzRecoveryServicesAsrVMNicIPConfig** dan langsung kirimkan sebagai parameter. Silakan lihat contoh di bawah ini untuk lebih jelasnya.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $ipConfig1 = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig1" -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.10" -TfoStaticIPAddress "10.3.4.33"
PS C:\> $ipConfig2 = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig2" -IsSelectedForFailover -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.13" -TfoStaticIPAddress "10.3.4.32"
PS C:\> $ipConfigs = @($ipConfig1, $ipConfig2)
PS C:\> $nicConfig = New-AzRecoveryServicesAsrVMNicConfig -NicId $AsrNicGuid -ReplicationProtectedItem $Rpi -RecoveryVMNetworkId $recoveryNetworkId `
    -TfoVMNetworkId $tfoNetworkId -IPConfig $ipConfigs
```

Membuat objek ASRVmNicConfig dengan pengaturan jaringan failover dan test failover yang dikonfigurasi untuk NIC. Properti apa pun yang tidak lolos di atas diambil dari item terproteksi yang lolos.

### Contoh 2
```powershell
PS C:\> $nicConfig = New-AzRecoveryServicesAsrVMNicConfig -NicId $AsrNicGuid -ReplicationProtectedItem $Rpi -TfoNicName $TfoNicName -TfoNicResourceGroupName $TfoNicRgName -TfoReuseExistingNic
```

Membuat objek ASRVmNicConfig dengan pengaturan jaringan samar-samar uji dikonfigurasi untuk penggantian nama NIC. Properti apa pun yang tidak lolos di atas diambil dari item terproteksi yang lolos.

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
Menentukan pengaturan uji failover/failover konfigurasi IP NIC.

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
Tentukan Item Terproteksi Replikasi ASR.

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
Menentukan apakah NIC yang sudah ada dapat digunakan selama failover.

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
Menentukan ID NSG terkait dengan uji failover NIC.

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
Menentukan nama grup sumber daya uji failover NIC.

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
Menentukan apakah NIC yang sudah ada dapat digunakan selama failover uji.

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

### -TfovMNetworkId
Menentukan ID dari jaringan virtual failover uji.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMNicConfig

## CATATAN

## RELATED LINKS
