---
external help file: ''
Module Name: Az.Maps
online version: https://docs.microsoft.com/powershell/module/az.maps/update-azmapsaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Update-AzMapsAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Maps/help/Update-AzMapsAccount.md
ms.openlocfilehash: 743cd33fe2e76f880e106221fc5e8098012794e9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140136177"
---
# Update-AzMapsAccount

## SYNOPSIS
Memperbarui Akun Peta Anda.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Sku, Tag, Properti.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.maps/update-azmapsaccount) untuk informasi terkini.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzMapsAccount -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-DisableLocalAuth]
 [-Kind <Kind>] [-SkuName <Name>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzMapsAccount -InputObject <IMapsIdentity> [-DisableLocalAuth] [-Kind <Kind>] [-SkuName <Name>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Akun Peta Anda.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Sku, Tag, Properti.

## EXAMPLES

### Contoh 1: Memperbarui Peta Anda
```powershell
PS C:\> Update-AzMapsAccount -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount03 -Tag @{'key1'='value1'; 'key2'='value2'}

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount03 Microsoft.Maps/accounts Gen1
```

Perintah ini memperbarui akun Peta Anda.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Sku, Tag, Properti.

### Contoh 2: Memperbarui Peta saluran
```powershell
PS C:\> Get-AzMapsAccount -ResourceGroupName azure-rg-test -Name pwsh-mapsAccount03 | Update-AzMapsAccount -Tag @{'key1'='value1'; 'key2'='value2'}

Location Name               Type                    Kind
-------- ----               ----                    ----
eastus   pwsh-mapsAccount03 Microsoft.Maps/accounts Gen1
```

Perintah ini memperbarui Peta tersebut menurut saluran.
Hanya subset parameter yang dapat diperbarui setelah pembuatan, seperti Sku, Tag, Properti.

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

### -DisableLocalAuth
Memungkinkan fungsi pengalih pada Kebijakan Azure untuk menonaktifkan Azure Peta dukungan autentikasi lokal.
Ini akan menonaktifkan autentikasi Kunci Bersama dari setiap penggunaan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

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

### -Kind
Properti Get atau Set Kind.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Maps.Support.Kind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama akun Peta Anda.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: AccountName

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

### -SkuName
Nama SKU, dalam format standar (seperti S0).

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Maps.Support.Name
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.IMapsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Peta. Models.Api20210201.IMapsAccount

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMapsIdentity>: Parameter Identitas
  - `[AccountName <String>]`: Nama akun Peta Anda.
  - `[CreatorName <String>]`: Nama instans Peta Creator.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

