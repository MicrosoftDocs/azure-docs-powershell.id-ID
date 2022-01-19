---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/new-azrecoveryservicesasrinmagercmdiskinput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrInMageRcmDiskInput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/New-AzRecoveryServicesAsrInMageRcmDiskInput.md
ms.openlocfilehash: 7efc6fc8cee060b8127ded0c9630739ca49080d5
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136162518"
---
# New-AzRecoveryServicesAsrInMageRcmDiskInput

## SYNOPSIS
Membuat konfigurasi replikasi Disk Pemulihan Situs Azure untuk replikasi VMware Ke Azure.

## SYNTAX

```
New-AzRecoveryServicesAsrInMageRcmDiskInput -DiskId <String> -LogStorageAccountId <String> -DiskType <String>
 [-DiskEncryptionSetId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek pemetaan disk yang memetakan disk mesin virtual VMware ke akun penyimpanan cache dan tipe disk terkelola target (kawasan pemulihan) untuk digunakan untuk mereplikasi disk.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzRecoveryServicesAsrInMageRcmDiskInput -DiskId $diskId -LogStorageAccountId $logStorageAccountId -DiskType $diskType -DiskEncryptionSetId $diskEncryptionSetId

DiskId              : 6000C296-91a1-f649-6714-a02903020cbc
LogStorageAccountId : /subscriptions/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/resourceGroups/xxxxxxxxxxxx/providers/Microsoft.Storage/storageAccounts/xxxxxxxxxxxx
DiskType            : Standard_LRS
DiskEncryptionSetId : 8010C296-91a1-a639-6714-a02903020cbc
```

Buat objek pemetaan disk untuk disk mesin virtual VMware agar direplikasi. Digunakan selama perlindungan yang diaktifkan untuk mesin VMware.

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
Menentukan kumpulan enkripsi disk ID ARM.

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
Tentukan DiskId dari disk yang sesuai dengan pemetaan ini.

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
Menentukan tipe disk Pemulihan.

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
Menentukan Id akun penyimpanan log atau cache yang akan digunakan untuk menyimpan log replikasi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRInMageRcmDiskInput

## CATATAN

## RELATED LINKS
