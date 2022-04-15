---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/remove-azproviderhubnotificationregistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Remove-AzProviderHubNotificationRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Remove-AzProviderHubNotificationRegistration.md
ms.openlocfilehash: f43bf1977767b41f8964a2606daff659d5ab3e1d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141949875"
---
# Remove-AzProviderHubNotificationRegistration

## SYNOPSIS
Menghapus pendaftaran pemberitahuan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.providerhub/remove-azproviderhubnotificationregistration) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzProviderHubNotificationRegistration -Name <String> -ProviderNamespace <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzProviderHubNotificationRegistration -InputObject <IProviderHubIdentity> [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus pendaftaran pemberitahuan.

## EXAMPLES

### Contoh 1: Menghapus pendaftaran pemberitahuan menurut nama.
```powershell
PS C:\> Remove-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso" -Name "notificationRegistrationTest"
```

Menghapus registrasi pemberitahuan berdasarkan nama.

### Contoh 2: Menghapus pendaftaran pemberitahuan menurut nama.
```powershell
PS C:\> Remove-AzProviderHubNotificationRegistration -ProviderNamespace "Microsoft.Contoso" -Name "notificationRegistrationTest"
```

Menghapus registrasi pemberitahuan berdasarkan nama.

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

### -Nama
Pendaftaran pemberitahuan.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: NotificationRegistrationName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IProviderHubIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[NestedResourceTypeFirst <String>]`: Tipe sumber daya anak pertama.
  - `[NestedResourceTypeSecond <String>]`: Tipe sumber daya anak kedua.
  - `[NestedResourceTypeThird <String>]`: Tipe sumber daya anak ketiga.
  - `[NotificationRegistrationName <String>]`: Registrasi pemberitahuan.
  - `[ProviderNamespace <String>]`: Nama penyedia sumber daya yang dihosting dalam ProviderHub.
  - `[ResourceType <String>]`: Tipe sumber daya.
  - `[RolloutName <String>]`: Nama peluncuran.
  - `[Sku <String>]`: SKU.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

