---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesasralertsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrAlertSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesAsrAlertSetting.md
ms.openlocfilehash: 635f6b893c3ad8d888c10c3589cc62698065e935
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145971877"
---
# Set-AzRecoveryServicesAsrAlertSetting

## SYNOPSIS
Mengonfigurasi pengaturan pemberitahuan Azure Site Recovery (pemberitahuan email) untuk vault.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/set-azrecoveryservicesasralertsetting) untuk informasi terbaru.

## SYNTAX

### Set (Default)
```
Set-AzRecoveryServicesAsrAlertSetting [-CustomEmailAddress <String[]>] [-LocaleID <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EmailToSubscriptionOwner
```
Set-AzRecoveryServicesAsrAlertSetting [-EnableEmailSubscriptionOwner] [-CustomEmailAddress <String[]>]
 [-LocaleID <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableEmailToSubcriptionOwner
```
Set-AzRecoveryServicesAsrAlertSetting [-DisableEmailToSubscriptionOwner] [-CustomEmailAddress <String[]>]
 [-LocaleID <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nonaktifkan
```
Set-AzRecoveryServicesAsrAlertSetting [-DisableNotification] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRecoveryServicesAsrNotificationSetting** mengonfigurasi pengaturan pemberitahuan Azure Site Recovery (pemberitahuan email) untuk vault.

## EXAMPLES

### Contoh 1
```powershell
Set-AzRecoveryServicesAsrAlertSetting -DisableNotification
```

```output
CustomEmailAddress EmailSubscriptionOwner Locale
------------------ ---------------------- ------
{}                 Off                    en-US
```

Nonaktifkan pemberitahuan.

### Contoh 2
```powershell
Set-AzRecoveryServicesAsrAlertSetting -CustomEmailAddress "abcxxxx@xxxx.com" -EnableEmailSubscriptionOwner
```

```output
CustomEmailAddress     EmailSubscriptionOwner Locale
------------------     ---------------------- ------
{abcxxxx@xxxx.com} On                     en-US
```

Atur pemberitahuan untuk alamat email kustom dan untuk pemilik langganan.

### Contoh: 3

Mengonfigurasi pengaturan pemberitahuan Azure Site Recovery (pemberitahuan email) untuk vault. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzRecoveryServicesAsrAlertSetting -CustomEmailAddress 'abcxxxx@xxxx.com' -DisableEmailToSubscriptionOwner
```

## PARAMETERS

### -CustomEmailAddress
Pemberitahuan / Pemberitahuan yang dikirim ke email.

```yaml
Type: System.String[]
Parameter Sets: Set, EmailToSubscriptionOwner, DisableEmailToSubcriptionOwner
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -DisableEmailToSubscriptionOwner
Parameter pengalihan menentukan aktifkan pemberitahuan kepada pemilik langganan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DisableEmailToSubcriptionOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableNotification
Bendera untuk menonaktifkan semua pemberitahuan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Disable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEmailSubscriptionOwner
Parameter pengalihan menentukan aktifkan pemberitahuan kepada pemilik langganan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EmailToSubscriptionOwner
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocaleID
Bahasa email pemberitahuan /pemberitahuan kepada pengguna(kode budaya yang didukung dari microsoft).

```yaml
Type: System.String
Parameter Sets: Set, EmailToSubscriptionOwner, DisableEmailToSubcriptionOwner
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRAlertSetting

## NOTES

## RELATED LINKS
