---
external help file: ''
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/test-azpurviewaccountnameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Test-AzPurviewAccountNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/help/Test-AzPurviewAccountNameAvailability.md
ms.openlocfilehash: 75d359f9bda75f6bb81cd47e8243b7040cfd7078
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143011529"
---
# Test-AzPurviewAccountNameAvailability

## SYNOPSIS
Memeriksa apakah nama akun tersedia.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.purview/test-azpurviewaccountnameavailability) untuk informasi terbaru.

## SYNTAX

```
Test-AzPurviewAccountNameAvailability -Name <String> -Type <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memeriksa apakah nama akun tersedia.

## EXAMPLES

### Contoh 1: Periksa apakah nama akun tersedia
```powershell
PS C:\> Test-AzPurviewAccountNameAvailability -Name test-pa -Type Tenant

Message                                                 NameAvailable Reason
-------                                                 ------------- ------
The name test-pa is invalid, please use another name. False         Invalid
```

Periksa apakah nama akun 'test-pa' tersedia.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya untuk memverifikasi ketersediaan

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

### -SubscriptionId
Pengidentifikasi langganan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Tipe sumber daya yang sepenuhnya memenuhi syarat yang mencakup ruang nama penyedia

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.Api20210701.ICheckNameAvailabilityResult

## NOTES

ALIAS

## RELATED LINKS

