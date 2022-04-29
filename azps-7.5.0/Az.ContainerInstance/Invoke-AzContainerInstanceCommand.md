---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/invoke-azcontainerinstancecommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Invoke-AzContainerInstanceCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Invoke-AzContainerInstanceCommand.md
ms.openlocfilehash: 688396c5b0ca65fbf7ec7dc229921c5fcb0297a8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144219455"
---
# Invoke-AzContainerInstanceCommand

## SYNOPSIS
Menjalankan perintah untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

## SYNTAX

```
Invoke-AzContainerInstanceCommand -ContainerGroupName <String> -ContainerName <String>
 -ResourceGroupName <String> -Command <String> [-SubscriptionId <String>] [-TerminalSizeCol <Int32>]
 [-TerminalSizeRow <Int32>] [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menjalankan perintah untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

## EXAMPLES

### Contoh 1: Menjalankan perintah dalam instans kontainer tertentu
```powershell
Invoke-AzContainerInstanceCommand -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName test-rg -Command "echo hello"
```

```output
hello
```

Menjalankan perintah "echo hello" dalam instans `test-container`kontainer .

## PARAMETERS

### -Perintah
Perintah yang akan dijalankan.

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

### -ContainerGroupName
Nama grup kontainer.

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

### -ContainerName
Nama instans kontainer.

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

### -PassThru
Mengembalikan hasil eksekusi terakhir saat perintah berhasil.
Secara default cmdlet tidak mengembalikan apa pun.

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
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### -TerminalSizeCol
Ukuran kolom terminal

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $host.UI.RawUI.WindowSize.Width
Accept pipeline input: False
Accept wildcard characters: False
```

### -TerminalSizeRow
Ukuran baris terminal

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $host.UI.RawUI.WindowSize.Height
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

## OUTPUTS

### System.String

## NOTES

ALIAS

## RELATED LINKS

