---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/New-AzRecoveryServicesAsrVMNicConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicConfig.md
ms.openlocfilehash: ea99c4c852ffa1702dace827e7c34c90cdad8a27
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142759960"
---
# New-AzRecoveryServicesAsrVMNicConfig

## SYNOPSIS
Membuat konfigurasi ASR NIC yang berisi failover dan menguji failover detail konfigurasi terkait.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/new-azrecoveryservicesasrvmnicconfig) untuk informasi terbaru.

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
Cmdlet **New-AzRecoveryServicesAsrVMNicConfig** membuat objek konfigurasi ASR NIC yang berisi failover dan menguji detail terkait failover. Jika informasi apa pun tidak dikirimkan, nilai terkait dipilih dari item yang diproteksi replikasi untuk menghindari nilai ini diperbarui menjadi null.

> [!IMPORTANT]
> Kami telah menghapus parameter yang terkait dengan IP Configs dari cmdlet, dan merangkumnya ke dalam objek cmdlet baru. Buat objek baru menggunakan cmdlet **New-AzRecoveryServicesAsrVMNicIPConfig** dan berikan sebagai parameter. Silakan lihat contoh di bawah ini untuk penjelasan selengkapnya.

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

Membuat objek ASRVmNicConfig dengan failover dan menguji pengaturan jaringan failover yang dikonfigurasi untuk NIC. Properti apa pun yang tidak lolos di atas akan diperoleh dari item terproteksi yang dilewati.

### Contoh 2
```powershell
PS C:\> $nicConfig = New-AzRecoveryServicesAsrVMNicConfig -NicId $AsrNicGuid -ReplicationProtectedItem $Rpi -TfoNicName $TfoNicName -TfoNicResourceGroupName $TfoNicRgName -TfoReuseExistingNic
```

Membuat objek ASRVmNicConfig dengan pengaturan jaringan faiover uji yang dikonfigurasi untuk penggantian nama NIC. Properti apa pun yang tidak lolos di atas akan diperoleh dari item terproteksi yang dilewati.

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
Menentukan apakah jaringan yang dipercepat diaktifkan pada pemulihan NIC.

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

### -EnableAcceleratedNetworkingOntfo
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
Menentukan pengaturan failover/failover uji NIC IP configs.

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
Menentukan ID NSG yang terkait dengan NIC pemulihan.

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
Menentukan apakah NIC yang sudah ada bisa digunakan selama failover.

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
Menentukan ID NSG yang terkait dengan NIC failover pengujian.

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
Menentukan nama grup sumber daya NIC failover uji.

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
Menentukan apakah NIC yang sudah ada dapat digunakan selama kegagalan pengujian.

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
Menentukan ID jaringan virtual failover uji coba.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMNicConfig

## NOTES

## RELATED LINKS
