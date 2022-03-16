---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/add-azcontainerinstanceoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Add-AzContainerInstanceOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Add-AzContainerInstanceOutput.md
ms.openlocfilehash: 6cb10bc4b4d5840d193ea9b16d4d15f56a970be9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140078507"
---
# Add-AzContainerInstanceOutput

## SYNOPSIS
Lampirkan ke aliran output contoh wadah tertentu dalam grup sumber daya dan grup wadah yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.containerinstance/add-azcontainerinstanceoutput) untuk informasi terkini.

## SYNTAX

```
Add-AzContainerInstanceOutput -GroupName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Lampirkan ke aliran output contoh wadah tertentu dalam grup sumber daya dan grup wadah yang ditentukan.

## EXAMPLES

### Contoh 1: Lampirkan ke output contoh wadah tertentu
```powershell
PS C:\>Add-AzContainerInstanceOutput -GroupName $env.containerGroupName -Name $env.containerInstanceName -ResourceGroupName $env.resourceGroupName

Add-AzContainerInstanceOutput -GroupName bez-cg2 -Name test-container -ResourceGroupName bez-rg

Password                         WebSocketUri
--------                         ------------
****************** wss://********.eastus.atlas.cloudapp.azure.com:19390/logstream/sessionId/00000000-0000-0000-0000-000000000000?api-version=1.0
```

Lampirkan ke aliran output contoh wadah tertentu dalam grup sumber daya dan grup wadah yang ditentukan.

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

### -GroupName
Nama grup wadah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ContainerGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama contoh wadah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ContainerName

Required: True
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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.IContainerAttachResponse

## CATATAN

ALIAS

## RELATED LINKS

