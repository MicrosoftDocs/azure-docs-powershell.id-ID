---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/update-azmapscreator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Update-AzMapsCreator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Update-AzMapsCreator.md
ms.openlocfilehash: 6c854abac9cbe922cd14b4490453ec3245a1457c
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136564844"
---
# Update-AzMapsCreator

## SYNOPSIS
Memperbarui sumber Peta Creator Anda.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Tag.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzMapsCreator -AccountName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-StorageUnit <Int32>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzMapsCreator -InputObject <IMapsIdentity> [-StorageUnit <Int32>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui sumber Peta Creator Anda.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Tag.

## EXAMPLES

### Contoh 1: Memperbarui sumber Peta Creator
```powershell
PS C:\> Update-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount03 -Name creator-01 -Tag @{'key1'='value1'; 'key2'='value2'}

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini memperbarui sumber daya Peta Creator.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Tag.

### Contoh 2: Memperbarui sumber Peta Creator menurut saluran
```powershell
PS C:\> Get-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount03 -Name creator-01 | Update-AzMapsCreator -Tag @{'key1'='value1'; 'key2'='value2'}

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini memperbarui sumber Peta Creator menurut saluran.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Tag.

## PARAMETERS

### -Nama Akun
Nama akun Peta Anda.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama instans Peta Creator.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: CreatorName

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
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageUnit
Unit penyimpanan yang akan dialokasikan.
Nilai bilangan bulat dari 1 sampai 100, inklusif.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Mendapatkan atau mengatur daftar pasangan nilai kunci yang menjelaskan sumber daya.
Tag ini bisa digunakan dalam menampilkan dan mengelompokkan sumber daya ini (di seluruh grup sumber daya).
Maksimal 15 tag dapat disediakan untuk sumber daya.
Setiap tag harus mempunyai kunci tidak lebih besar dari 128 karakter dan nilai tidak lebih besar dari 256 karakter.

```yaml
Type: System.Collections.Hashtable
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.ICreator

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity> : Parameter Identitas
  - `[AccountName <String>]`: Nama Peta Anda.
  - `[CreatorName <String>]`: Nama Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

