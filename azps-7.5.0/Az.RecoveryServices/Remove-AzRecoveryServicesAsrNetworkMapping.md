---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/remove-azrecoveryservicesasrnetworkmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Remove-AzRecoveryServicesAsrNetworkMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Remove-AzRecoveryServicesAsrNetworkMapping.md
ms.openlocfilehash: 07fef7773a409a4116f2617821dc6ba8cf5b0e3d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244674"
---
# Remove-AzRecoveryServicesAsrNetworkMapping

## SYNOPSIS
Menghapus pemetaan jaringan ASR yang ditentukan dari vault Layanan Pemulihan.

## SYNTAX

```
Remove-AzRecoveryServicesAsrNetworkMapping -InputObject <ASRNetworkMapping>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzRecoveryServicesAsrNetworkMapping** menghapus pemetaan jaringan ASR yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
$currentJob = Remove-AzRecoveryServicesAsrNetworkMapping -NetworkMapping $networkmapping
```

Memulai penghapusan pemetaan jaringan ASR yang ditentukan dan mengembalikan pekerjaan ASR yang digunakan untuk melacak operasi.

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

### -InputObject
Objek input ke cmdlet: Objek pemetaan jaringan ASR yang sesuai dengan pemetaan jaringan ASR yang akan dihapus.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRNetworkMapping
Parameter Sets: (All)
Aliases: NetworkMapping

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRNetworkMapping

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRJob

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesAsrNetworkMapping](./Get-AzRecoveryServicesAsrNetworkMapping.md)

[New-AzRecoveryServicesAsrNetworkMapping](./New-AzRecoveryServicesAsrNetworkMapping.md)
