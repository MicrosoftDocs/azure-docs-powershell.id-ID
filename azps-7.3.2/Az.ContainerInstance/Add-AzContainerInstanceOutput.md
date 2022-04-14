---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/add-azcontainerinstanceoutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Add-AzContainerInstanceOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Add-AzContainerInstanceOutput.md
ms.openlocfilehash: 513030ce228775ad71582a6bf1f189358da39b5f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142217341"
---
# Add-AzContainerInstanceOutput

## SYNOPSIS
Lampirkan ke aliran output instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/add-azcontainerinstanceoutput) untuk informasi terbaru.

## SYNTAX

```
Add-AzContainerInstanceOutput -GroupName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Lampirkan ke aliran output instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

## EXAMPLES

### Contoh 1: Melampirkan ke output instans kontainer tertentu
```powershell
$response = Add-AzContainerInstanceOutput -GroupName test-cg -Name test-container -ResourceGroupName test-rg
$response
```

```output
Password                         WebSocketUri
--------                         ------------
****************** wss://********.eastus.atlas.cloudapp.azure.com:19390/logstream/sessionId/00000000-0000-0000-0000-000000000000?api-version=1.0
```

Perintah ini dilampirkan ke aliran output instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.
Silakan kirim `Password` sebagai nilai header Otorisasi ketika menyambungkan `WebSocketUri`ke .

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
Nama instans kontainer.

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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerAttachResponse

## CATATAN

ALIAS

## RELATED LINKS

