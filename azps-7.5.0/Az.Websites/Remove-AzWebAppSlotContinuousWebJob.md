---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/remove-azwebappslotcontinuouswebjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppSlotContinuousWebJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppSlotContinuousWebJob.md
ms.openlocfilehash: b47de2403ff30a6057cca052a200d501abf79461
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144227955"
---
# Remove-AzWebAppSlotContinuousWebJob

## SYNOPSIS
Menghapus pekerjaan web berkelanjutan untuk slot penyebaran.

## SYNTAX

### Hapus (Default)
```
Remove-AzWebAppSlotContinuousWebJob -AppName <String> -Name <String> -ResourceGroupName <String>
 -SlotName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzWebAppSlotContinuousWebJob -InputObject <IWebsitesIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus pekerjaan web berkelanjutan untuk slot penyebaran.

## EXAMPLES

### Contoh 1: Menghapus pekerjaan web berkelanjutan untuk slot penyebaran
```powershell
PS C:\> Remove-AzWebAppSlotContinuousWebJob -ResourceGroupName webjob-rg-test -AppName appService-test01 -SlotName slot01 -Name slotcontinuousjob-03
```

Perintah ini menghapus pekerjaan web berkelanjutan untuk slot penyebaran.

### Contoh 2: Menghapus pekerjaan web berkelanjutan untuk slot penyebaran menurut alur
```powershell
PS C:\> Get-AzWebAppSlotContinuousWebJob -ResourceGroupName webjob-rg-test -AppName appService-test01 -SlotName slot01 -Name slotcontinuousjob-04 | Remove-AzWebAppSlotContinuousWebJob
```

Perintah ini menghapus pekerjaan web berkelanjutan untuk slot penyebaran menurut alur.

## PARAMETERS

### -AppName
Nama situs.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Pekerjaan Web.

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

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya berada.

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

### -SlotName
Nama slot penyebaran.
Jika slot tidak ditentukan, API akan menghapus penyebaran untuk slot produksi.

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
ID langganan Azure Anda.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000).

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

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IWebsitesIdentity>: Parameter Identitas
  - `[Authprovider <String>]`: Penyedia autentikasi untuk pengguna.
  - `[DomainName <String>]`: Nama domain kustom.
  - `[EnvironmentName <String>]`: Pengidentifikasi situs tahapan.
  - `[FunctionAppName <String>]`: Nama aplikasi fungsi yang terdaftar dengan build situs statis.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobHistoryId <String>]`: ID Riwayat.
  - `[Location <String>]`: Lokasi tempat Anda berencana membuat situs statis.
  - `[Name <String>]`: Nama situs statis.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya berada.
  - `[Slot <String>]`: Nama slot penyebaran. Jika slot tidak ditentukan, API akan menghapus penyebaran untuk slot produksi.
  - `[SubscriptionId <String>]`: ID langganan Azure Anda. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: Id pengguna pengguna.
  - `[WebJobName <String>]`: Nama Pekerjaan Web.

## RELATED LINKS
