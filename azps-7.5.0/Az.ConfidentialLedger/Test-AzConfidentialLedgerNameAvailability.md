---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.confidentialledger/test-azconfidentialledgernameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Test-AzConfidentialLedgerNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/Test-AzConfidentialLedgerNameAvailability.md
ms.openlocfilehash: 6f04e32a50e6ee7cb952f08b25bac944617d46e3
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144244391"
---
# Test-AzConfidentialLedgerNameAvailability

## SYNOPSIS
Untuk memeriksa apakah nama sumber daya tersedia.

## SYNTAX

```
Test-AzConfidentialLedgerNameAvailability [-SubscriptionId <String>] [-Name <String>] [-Type <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Untuk memeriksa apakah nama sumber daya tersedia.

## EXAMPLES

### Contoh 1: Nama tersedia
```powershell
PS C:\> Test-AzConfidentialLedgerNameAvailability `
  -NameAvailabilityRequest `
      @{
          Name="available-name";
          Type="Microsoft.ConfidentialLedger/ledgers"
      }

Message       :
NameAvailable : True
Reason        :
```

Memeriksa untuk melihat apakah nama Confidential Ledger yang ditentukan tersedia.
Dalam hal ini, nama tersedia.
Nama Confidential Ledger harus unik secara global.

### Contoh 2: Nama tidak tersedia
```powershell
PS C:\> Test-AzConfidentialLedgerNameAvailability `
  -NameAvailabilityRequest `
      @{
          Name="not-available-name";
          Type="Microsoft.ConfidentialLedger/ledgers"
      }

Message       : Resource name already exists
NameAvailable : False
Reason        : AlreadyExists
```

Memeriksa untuk melihat apakah nama Confidential Ledger yang ditentukan tersedia.
Dalam hal ini, nama tidak tersedia.
Nama Confidential Ledger harus unik secara global.

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

### -Name
Nama sumber daya yang ketersediaannya perlu diperiksa.

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

### -SubscriptionId
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

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

### -Type
Jenis sumber daya.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20.ICheckNameAvailabilityResponse

## NOTES

ALIAS

## RELATED LINKS

