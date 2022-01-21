---
external help file: ''
Module Name: Az.Communication
online version: https://docs.microsoft.com/powershell/module/az.communication/test-azcommunicationservicenameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Communication/help/Test-AzCommunicationServiceNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Communication/help/Test-AzCommunicationServiceNameAvailability.md
ms.openlocfilehash: 6ab1a52cd30d1012f50eea1d1387955f2d374e77
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136532561"
---
# Test-AzCommunicationServiceNameAvailability

## SYNOPSIS
Memeriksa bahwa nama CommunicationService valid dan belum digunakan.

## SYNTAX

```
Test-AzCommunicationServiceNameAvailability -Name <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memeriksa bahwa nama CommunicationService valid dan belum digunakan.

## EXAMPLES

### Contoh 1: Periksa jika sudah menggunakan nama sumber daya ContosoAcsResource1 tersedia
```powershell
PS C:\> Test-AzCommunicationServiceNameAvailability -Name ContosoAcsResource1

Message                               NameAvailable Reason
-------                               ------------- ------
Requested name is unavailable for the requested type False         AlreadyExists
```

Memverifikasi bahwa nama Layanan Komunikasi valid dan belum digunakan.

### Contoh 2: Memeriksa apakah nama sumber daya baru ContosoAcsResource2 tersedia
```powershell
PS C:\> Test-AzCommunicationServiceNameAvailability -Name ContosoAcsResource2

Message                               NameAvailable Reason
-------                               ------------- ------
Requested name is available for the requested type True         NameAvailable
```

Memverifikasi bahwa nama Layanan Komunikasi yang diminta sudah digunakan.

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
Nama LayananKom communicationservice untuk memvalidasi.
mis."my-CommunicationService-name-here"

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
ID langganan target.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Communication.Models.Api20200820.INameAvailability

## CATATAN

ALIAS

## RELATED LINKS

