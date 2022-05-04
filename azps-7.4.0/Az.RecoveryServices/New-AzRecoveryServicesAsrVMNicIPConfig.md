---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/New-AzRecoveryServicesAsrVMNicIPConfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicIPConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrVMNicIPConfig.md
ms.openlocfilehash: 7cbed007bb34769f3137bf27c60e9c59b0643d3d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144599054"
---
# New-AzRecoveryServicesAsrVMNicIPConfig

## SYNOPSIS
Membuat konfigurasi IP NIC ASR yang berisi detail konfigurasi failover dan pengujian failover untuk setiap Konfigurasi IP (Primer dan Sekunder) NIC.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/new-azrecoveryservicesasrvmnicipconfig) untuk informasi terbaru.

## SYNTAX

```
New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName <String> [-IsSelectedForFailover]
 [-RecoverySubnetName <String>] [-RecoveryStaticIPAddress <String>] [-RecoveryPublicIPAddressId <String>]
 [-RecoveryLBBackendAddressPoolId <String[]>] [-TfoSubnetName <String>] [-TfoStaticIPAddress <String>]
 [-TfoPublicIPAddressId <String>] [-TfoLBBackendAddressPoolId <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRecoveryServicesAsrVMNicIPConfig** membuat objek Konfigurasi IP yang berisi detail failover dan failover pengujian untuk setiap Konfigurasi IP (Primer dan Sekunder) NIC. Ini selanjutnya harus diteruskan sebagai parameter ke ** New-AzRecoveryServicesAsrVMNicConfig** untuk mengatur nilai-nilai ini di Objek Konfigurasi ASR NIC.

## EXAMPLES

### Contoh 1
```powershell
$ipConfig = New-AzRecoveryServicesAsrVMNicIPConfig -IpConfigName "ipconfig1" -RecoverySubnetName "default" `
-TfoSubnetName "default" -RecoveryStaticIPAddress "10.1.40.10" -TfoStaticIPAddress "10.3.4.33"
```

Membuat objek PSIPConfigInputDetails dengan pengaturan jaringan failover dan pengujian failover yang dikonfigurasi untuk konfigurasi IP NIC .

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
Tentukan nama konfigurasi IP.

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
Menentukan apakah konfigurasi IP yang ada dipilih untuk uji failover/failover.

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
Menentukan ID kumpulan alamat backend untuk konfigurasi IP pemulihan.

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
Menentukan ID kumpulan alamat backend untuk konfigurasi IP failover pengujian.

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
Menentukan ID alamat IP publik yang terkait dengan konfigurasi IP failover pengujian.

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
Menentukan alamat IP konfigurasi IP failover pengujian.

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
Menentukan nama subnet failover pengujian.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.PSIPConfigInputDetails

## NOTES

## RELATED LINKS
