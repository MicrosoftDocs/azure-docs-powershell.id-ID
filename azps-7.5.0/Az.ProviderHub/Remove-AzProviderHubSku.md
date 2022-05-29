---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/remove-azproviderhubsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Remove-AzProviderHubSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Remove-AzProviderHubSku.md
ms.openlocfilehash: 6fddd2268b996eff6a0b4448a84a5e0ea0ee8bc9
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145656742"
---
# Remove-AzProviderHubSku

## SYNOPSIS
Menghapus sku jenis sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.providerhub/remove-azproviderhubsku) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzProviderHubSku -ProviderNamespace <String> -ResourceType <String> -Sku <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzProviderHubSku -InputObject <IProviderHubIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus sku jenis sumber daya.

## EXAMPLES

### Contoh 1: Menghapus definisi SKU sumber daya.
```powershell
Remove-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType" -Sku "default"
```

Menghapus definisi SKU jenis sumber daya.

### Contoh 2: Menghapus definisi SKU sumber daya berlapis.
```powershell
Remove-AzProviderHubSku -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType/nestedResourceType" -Sku "default"
```

Menghapus definisi SKU jenis sumber daya berlapis.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ProviderNamespace
Nama penyedia sumber daya yang dihosting dalam ProviderHub.

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

### -ResourceType
Jenis sumber daya.

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

### -Sku
The SKU.

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
ID langganan target.

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

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IProviderHubIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[NestedResourceTypeFirst <String>]`: Jenis sumber daya anak pertama.
  - `[NestedResourceTypeSecond <String>]`: Jenis sumber daya anak kedua.
  - `[NestedResourceTypeThird <String>]`: Jenis sumber daya anak ketiga.
  - `[NotificationRegistrationName <String>]`: Pendaftaran pemberitahuan.
  - `[ProviderNamespace <String>]`: Nama penyedia sumber daya yang dihosting dalam ProviderHub.
  - `[ResourceType <String>]`: Jenis sumber daya.
  - `[RolloutName <String>]`: Nama peluncuran.
  - `[Sku <String>]`: SKU.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

