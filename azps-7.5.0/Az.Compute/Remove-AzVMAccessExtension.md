---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 22C490C2-0135-4375-897E-7224DBBE13A7
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azvmaccessextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVMAccessExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzVMAccessExtension.md
ms.openlocfilehash: b555115686b4195605c2c4bc9b120d8eff40e1bc
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145977209"
---
# Remove-AzVMAccessExtension

## SYNOPSIS
Menghapus ekstensi VMAccess dari komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/remove-azvmaccessextension) untuk informasi terbaru.

## SYNTAX

```
Remove-AzVMAccessExtension [-ResourceGroupName] <String> [-VMName] <String> [-Name] <String> [-Force] [-NoWait]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVMAccessExtension** menghapus Ekstensi Komputer Virtual Akses Komputer Virtual (VMAccess) dari komputer virtual.

## EXAMPLES

### Contoh 1

Menghapus ekstensi VMAccess dari komputer virtual. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Remove-AzVMAccessExtension -Name 'AgentPool01' -ResourceGroupName myresourcegroup -VMName 'VM01'
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
Menentukan nama ekstensi yang dihapus cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoWait
Memulai operasi dan segera kembali, sebelum operasi selesai. Untuk menentukan apakah operasi telah berhasil diselesaikan, gunakan beberapa mekanisme lain.

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
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama komputer virtual.
Cmdlet ini menghapus VMAccess untuk komputer virtual yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzVMAccessExtension](./Get-AzVMAccessExtension.md)

[Set-AzVMAccessExtension](./Set-AzVMAccessExtension.md)

[Remove-AzVMExtension](./Remove-AzVMExtension.md)
