---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/new-azmapsaccountkey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/New-AzMapsAccountKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/New-AzMapsAccountKey.md
ms.openlocfilehash: 25189ec6740dbc543a02e3f56c51cf58673459ee
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136710294"
---
# New-AzMapsAccountKey

## SYNOPSIS
Meregenerasi kunci utama atau sekunder untuk digunakan dengan Peta API.
Kunci lama akan langsung berhenti bekerja.

## SYNTAX

### RegenerasiExpanded (Default)
```
New-AzMapsAccountKey -Name <String> -ResourceGroupName <String> -KeyType <KeyType> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### RegenerateViaIdentityExpanded
```
New-AzMapsAccountKey -InputObject <IMapsIdentity> -KeyType <KeyType> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kunci utama atau sekunder untuk digunakan dengan Peta API.
Kunci lama akan langsung berhenti bekerja.

## EXAMPLES

### Contoh 1: Meregenerasi kunci primer atau sekunder untuk digunakan dengan Peta API
```powershell
PS C:\> New-AzMapsAccountKey -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount01 -KeyType primary

PrimaryKey                                  PrimaryKeyLastUpdated        SecondaryKey                                SecondaryKeyLastUpdated
----------                                  ---------------------        ------------                                -----------------------
W5VYcbrpyt4urV2-4C-lXepnHoy6EIOHnoLL_wjEtaw 2021-05-20T05:50:27.1509422Z zi6W1bw4zIYLjDj_DRRrC3jBkX-APgBebwx4cZBKJOU 2021-05-20T05:41:03.452571Z
```

Perintah ini meregenerasi kunci primer atau sekunder untuk digunakan dengan Peta API.
Kunci lama akan langsung berhenti bekerja.

### Contoh 2: Meregenerasi kunci utama atau sekunder untuk digunakan dengan API Peta melalui pipeline
```powershell
PS C:\> Get-AzMapsAccount -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount01 | New-AzMapsAccountKey -KeyType primary

PrimaryKey                                  PrimaryKeyLastUpdated        SecondaryKey                                SecondaryKeyLastUpdated
----------                                  ---------------------        ------------                                -----------------------
xoGsuTFWuG6xq0re7EdA7nCbDhvRoisZfLHvKfdzIhQ 2021-05-20T05:55:21.7797268Z zi6W1bw4zIYLjDj_DRRrC3jBkX-APgBebwx4cZBKJOU 2021-05-20T05:41:03.452571Z
```

Perintah ini meregenerasi kunci utama atau sekunder untuk digunakan dengan PETA API melalui pipeline.
Kunci lama akan langsung berhenti bekerja.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Maps.Models.IMapsIdentity
Parameter Sets: RegenerateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyType
Apakah operasi merujuk pada tombol utama atau sekunder.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Maps.Support.KeyType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama akun Peta Anda.

```yaml
Type: System.String
Parameter Sets: RegenerateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: RegenerateExpanded
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
Parameter Sets: RegenerateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.IMapsAccountKeys

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama akun Peta Anda.
  - `[CreatorName <String>]`: Nama Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

