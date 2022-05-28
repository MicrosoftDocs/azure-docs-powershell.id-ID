---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 880D321E-30F2-4CAE-B14A-5F6DD8E1DB99
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzResourceGroup.md
ms.openlocfilehash: 7ecd386ef1a664a9f84f9686313e69ebb1a1af9e
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145639682"
---
# Remove-AzResourceGroup

## SYNOPSIS
Menghapus kunci sumber daya

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/remove-azresourcegroup) untuk informasi terbaru.

## SYNTAX

### RemoveByResourceGroupName (Default)
```
Remove-AzResourceGroup [-Name] <String> [-Force] [-AsJob] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByResourceGroupId
```
Remove-AzResourceGroup -Id <String> [-Force] [-AsJob] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzResourceGroup** menghapus grup sumber daya Azure dan sumber dayanya dari langganan saat ini.
Untuk menghapus sumber daya, tetapi tinggalkan grup sumber daya, gunakan cmdlet Remove-AzResource.

## EXAMPLES

### Contoh 1: Menghapus grup sumber daya
```powershell
Remove-AzResourceGroup -Name "ContosoRG01"
```

Perintah ini menghapus grup sumber daya ContosoRG01 dari langganan.
Cmdlet meminta konfirmasi Anda dan tidak menghasilkan output.

### Contoh 2: Menghapus grup sumber daya tanpa konfirmasi
```powershell
Get-AzResourceGroup -Name "ContosoRG01" | Remove-AzResourceGroup -Force
```

Perintah ini menggunakan cmdlet Get-AzResourceGroup untuk mendapatkan grup sumber daya ContosoRG01, lalu meneruskannya ke **Remove-AzResourceGroup** dengan menggunakan operator alur. Parameter *Paksa* menekan prompt konfirmasi.

### Contoh 3: Menghapus semua grup sumber daya
```powershell
Get-AzResourceGroup | Remove-AzResourceGroup
```

Perintah ini menggunakan cmdlet **Get-AzResourceGroup** untuk mendapatkan semua grup sumber daya, lalu meneruskannya ke **Remove-AzResourceGroup** dengan menggunakan operator alur.

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda dapat menentukan versi yang berbeda dari versi default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Id
Menentukan ID grup sumber daya yang akan dihapus.
Karakter kartubebas tidak diizinkan.

```yaml
Type: System.String
Parameter Sets: RemoveByResourceGroupId
Aliases: ResourceGroupId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama grup sumber daya yang akan dihapus.
Karakter kartubebas tidak diizinkan.

```yaml
Type: System.String
Parameter Sets: RemoveByResourceGroupName
Aliases: ResourceGroupName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pre
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[Baru-AzResourceGroup](./New-AzResourceGroup.md)

[Set-AzResourceGroup](./Set-AzResourceGroup.md)


