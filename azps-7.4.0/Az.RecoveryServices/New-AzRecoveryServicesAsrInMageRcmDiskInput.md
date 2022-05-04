---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/new-azrecoveryservicesasrinmagercmdiskinput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrInMageRcmDiskInput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrInMageRcmDiskInput.md
ms.openlocfilehash: 7f6f25ec3f85cf0945ff905eda0aaa36eb2cd877
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144728888"
---
# New-AzRecoveryServicesAsrInMageRcmDiskInput

## SYNOPSIS
Membuat konfigurasi replikasi Azure Site Recovery Disk untuk replikasi VMware Ke Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/new-azrecoveryservicesasrinmagercmdiskinput) untuk informasi terbaru.

## SYNTAX

```
New-AzRecoveryServicesAsrInMageRcmDiskInput -DiskId <String> -LogStorageAccountId <String> -DiskType <String>
 [-DiskEncryptionSetId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek pemetaan disk yang memetakan disk komputer virtual VMware ke akun penyimpanan cache dan jenis disk terkelola target (wilayah pemulihan) yang akan digunakan untuk mereplikasi disk.

## EXAMPLES

### Contoh 1
```powershell
New-AzRecoveryServicesAsrInMageRcmDiskInput -DiskId $diskId -LogStorageAccountId $logStorageAccountId -DiskType $diskType -DiskEncryptionSetId $diskEncryptionSetId
```

```output
DiskId              : 6000C296-91a1-f649-6714-a02903020cbc
LogStorageAccountId : /subscriptions/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/resourceGroups/xxxxxxxxxxxx/providers/Microsoft.Storage/storageAccounts/xxxxxxxxxxxx
DiskType            : Standard_LRS
DiskEncryptionSetId : 8010C296-91a1-a639-6714-a02903020cbc
```

Buat objek pemetaan disk untuk disk komputer virtual VMware yang akan direplikasi. Digunakan selama mengaktifkan perlindungan untuk komputer VMware.

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

### -DiskEncryptionSetId
Menentukan ID ARM set enkripsi disk.

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

### -DiskId
Tentukan DiskId disk yang sesuai dengan pemetaan ini.

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

### -DiskType
Menentukan jenis disk Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Standard_LRS, Premium_LRS, StandardSSD_LRS

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogStorageAccountId
Menentukan ID akun penyimpanan log atau cache yang akan digunakan untuk menyimpan log replikasi.

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

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRInMageRcmDiskInput

## NOTES

## RELATED LINKS
