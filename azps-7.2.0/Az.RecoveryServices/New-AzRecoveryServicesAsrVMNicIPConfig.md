---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/New-AzRecoveryServicesAsrVMNicIPConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicIPConfig.md
ms.openlocfilehash: 09c90b26058eb61b6e7e74ba03234d9d092fba5f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138300908"
---
# New-AzRecoveryServicesAsrVMNicIPConfig

## SYNOPSIS
Membuat konfigurasi IP ASR NIC yang berisi detail konfigurasi failover dan test failover untuk setiap IP Config (Primary dan Secondary) dari NIC.

## SYNTAX

```
New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName <String> [-IsSelectedForFailover]
 [-RecoverySubnetName <String>] [-RecoveryStaticIPAddress <String>] [-RecoveryPublicIPAddressId <String>]
 [-RecoveryLBBackendAddressPoolId <String[]>] [-TfoSubnetName <String>] [-TfoStaticIPAddress <String>]
 [-TfoPublicIPAddressId <String>] [-TfoLBBackendAddressPoolId <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesAsrVMNicIPConfig** membuat objek IP Config yang berisi detail failover dan test failover untuk setiap IP Config (Primary dan Secondary) dari NIC. This further should be passed as a parameter to ** New-AzRecoveryServicesAsrVMNicConfig** for setting these values in the ASR NIC Config Object.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $ipConfig = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig1" -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.10" -TfoStaticIPAddress "10.3.4.33"
```

Membuat objek PSIPConfigInputDetails dengan pengaturan jaringan failover dan test failover yang dikonfigurasi untuk ip config of a NIC.

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

### -IpConfigName
Specify the IP config name.

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

### -IsSelectedForFailover
Menentukan apakah konfigurasi IP yang sudah ada dipilih untuk menguji failover/failover.

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

### -RecoveryLBBackendAddressPoolId
Menentukan NOMOR kolam renang alamat backend untuk konfigurasi IP pemulihan.

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

### -RecoveryPublicIPAddressId
Menentukan ID alamat IP publik yang terkait dengan konfigurasi IP pemulihan.

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

### -RecoveryStaticIPAddress
Menentukan alamat IP konfigurasi IP pemulihan.

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

### -RecoverySubnetName
Menentukan nama subnet pemulihan.

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

### -TfoLBBackendAddressPoolId
Menentukan NOMOR kolam renang alamat backend untuk konfigurasi IP failover uji.

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

### -TfoPublicIPAddressId
Menentukan ID alamat IP publik yang terkait dengan konfigurasi IP failover uji.

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

### -TfoStaticIPAddress
Menentukan alamat IP uji konfigurasi IP failover.

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

### -TfoSubnetName
Menentukan nama subnet failover uji.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.PSIPConfigInputDetails

## CATATAN

## RELATED LINKS
