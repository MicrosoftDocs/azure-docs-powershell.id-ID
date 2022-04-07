---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/new-azmapscreator
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/New-AzMapsCreator.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/New-AzMapsCreator.md
ms.openlocfilehash: fb3a80cd1b1d399b4b0afbe1b6a7f21b84337671
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140332889"
---
# New-AzMapsCreator

## SYNOPSIS
Buat atau perbarui sumber Peta Creator Anda.
Sumber daya pembuat akan mengelola sumber daya Azure yang diperlukan untuk mengisi kumpulan data pemetaan kustom.
Akun harus ada sebelum dapat dibuat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.maps/new-azmapscreator) untuk informasi terkini.

## SYNTAX

```
New-AzMapsCreator -AccountName <String> -Name <String> -ResourceGroupName <String> -Location <String>
 -StorageUnit <Int32> [-SubscriptionId <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat atau perbarui sumber Peta Creator Anda.
Sumber daya pembuat akan mengelola sumber daya Azure yang diperlukan untuk mengisi kumpulan data pemetaan kustom.
Akun harus ada sebelum dapat dibuat.

## EXAMPLES

### Contoh 1: Membuat sumber Peta Pembuat Konten
```powershell
PS C:\> New-AzMapsCreator -ResourceGroupName azure-rg-test -AccountName pwsh-mapsAccount02 -Name creator-01 -Location eastus2 -StorageUnit 3

Location Name       Type
-------- ----       ----
eastus2  creator-01 Microsoft.Maps/accounts/creators
```

Perintah ini akan membuat sumber daya Peta Creator.
Sumber daya pembuat akan mengelola sumber daya Azure yang diperlukan untuk mengisi kumpulan data pemetaan kustom.
Akun harus ada sebelum dapat dibuat.

## PARAMETERS

### -Nama Akun
Nama akun Peta Anda.

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

### -Lokasi
Lokasi geo-location di mana sumber daya berada

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

### -Nama
Nama instans Peta Creator.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
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

### -Tag
Tag sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.ICreator

## CATATAN

ALIAS

## RELATED LINKS

