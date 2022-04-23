---
external help file: ''
Module Name: Az.BotService
online version: https://docs.microsoft.com/powershell/module/az.botservice/remove-azbotservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BotService/help/Remove-AzBotService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BotService/help/Remove-AzBotService.md
ms.openlocfilehash: 90033af2d5bdcb18f61bcab33b363b2c79befa9e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143363285"
---
# Remove-AzBotService

## SYNOPSIS
Menghapus Bot Service dari grup sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.botservice/remove-azbotservice) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzBotService -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzBotService -InputObject <IBotServiceIdentity> [-DefaultProfile <PSObject>] [-PassThru] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus Bot Service dari grup sumber daya.

## EXAMPLES

### Contoh 1: Hapus BotService Menurut Nama dan ResourceGroupName
```powershell
Remove-AzBotService -Name youri-bot -ResourceGroupName youriBotTest

```

Menghapus BotService Menurut Nama dan ResourceGroupName

### Contoh 2: Hapus BotService Menurut InputObject
```powershell
$getservice = Get-AzBotService -Name youriechobottest -ResourceGroupName youriBotTest
Remove-AzBotService -InputObject $getservice

```

Menghapus BotService Dengan InputObject

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
Type: Microsoft.Azure.PowerShell.Cmdlets.BotService.Models.IBotServiceIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya Bot.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: BotName

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
Nama grup sumber daya Bot dalam langganan pengguna.

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
ID Langganan Azure.

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

### Microsoft.Azure.PowerShell.Cmdlets.BotService.Models.IBotServiceIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IBotServiceIdentity>: Parameter Identitas
  - `[ChannelName <ChannelName?>]`: Nama sumber daya Saluran.
  - `[ConnectionName <String>]`: Nama sumber daya Pengaturan Koneksi Bot Service
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya Bot dalam langganan pengguna.
  - `[ResourceName <String>]`: Nama sumber daya Bot.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

## RELATED LINKS

