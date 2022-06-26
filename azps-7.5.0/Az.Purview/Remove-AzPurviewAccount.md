---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/remove-azpurviewaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Remove-AzPurviewAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Remove-AzPurviewAccount.md
ms.openlocfilehash: e70244264241d151267f363c15ea760ed642c5cc
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146609086"
---
# Remove-AzPurviewAccount

## SYNOPSIS
Menghapus sumber daya akun

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/remove-azpurviewaccount) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzPurviewAccount -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzPurviewAccount -InputObject <IPurviewIdentity> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus sumber daya akun

## EXAMPLES

### Contoh 1: Menghapus akun purview
```powershell
Remove-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg
```

Menghapus akun purview bernama 'test-pa'

### Contoh 2: Menghapus akun purview dengan InputObject
```powershell
$get = Get-AzPurviewAccount -Name test-pa -ResourceGroupName test-rg
Remove-AzPurviewAccount -InputObject $get
```

Menghapus akun purview bernama 'test-pa' oleh InputObject

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama akun.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Delete
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
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.Purview.Models.IPurviewIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IPurviewIdentity>`: Parameter Identitas
  - `[AccountName <String>]`: Nama akun.
  - `[GroupId <String>]`: Pengidentifikasi grup.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[SubscriptionId <String>]`: Pengidentifikasi langganan

## RELATED LINKS
