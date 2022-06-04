---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/new-aznetappfilesexportpolicyobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesExportPolicyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesExportPolicyObject.md
ms.openlocfilehash: 3464f9cfdbf3a64b4079ec58e32fed70f85b7d9d
ms.sourcegitcommit: 7694b86b71e0246a30757731dc3978641aecee40
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/04/2022
ms.locfileid: "146083676"
---
# New-AzNetAppFilesExportPolicyObject

## SYNOPSIS
Membuat objek kebijakan ekspor.

## SYNTAX

```
New-AzNetAppFilesExportPolicyObject -Rule <PSNetAppFilesExportPolicyRule[]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
New-AzNetAppFilesExportPolicyObject adalah cmdlet pembantu yang membuat objek kebijakan ekspor yang dapat digunakan dengan New-AzNetAppFilesVolume.
Setiap objek ExportPolicy terdiri dari sekumpulan aturan ExportPolicy yang dapat diterapkan ke volume ANF.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $exportPolicyRule = New-NetAppFilesAzExportPolicyRuleObject -RuleIndex 1 -AllowedClients '0.0.0.0/0' -UnixReadOnly -UnixReadWrite -Cifs -Nfsv3
PS C:\> $exportPolicyRules = $($exportPolicyRule)
PS C:\> $newExportPolicy = New-NetAppFilesAzExportPolicyObject -Rules $exportPolicyRules
PS C:\> New-AzNetAppFilesVolume -ResourceGroupName "MyRG" -AccountName "MyAnfAccount" -PoolName "MyAnfPool" -Name "MyAnfVolume" -l "westus2" -CreationToken "MyAnfVolume" -UsageThreshold 1099511627776 -ServiceLevel "Premium" -SubnetId "/subscriptions/subsId/resourceGroups/MyRG/providers/Microsoft.Network/virtualNetworks/MyVnetName/subnets/MySubNetName" -ExportPolicy $newExportPolicy
```

Contoh ini membuat ExportPolicyRule dalam variabel $exportPolicyRule, menetapkan objek kebijakan ekspor $exportPolicyRules yang kemudian digunakan dalam pembuatan volume AFN "MyAnfVolume""

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Aturan
Daftar item yang perlu dimasukkan ke dalam cakupan endpont.

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesExportPolicyRule[]
Parameter Sets: (All)
Aliases:

Required: True
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolumeExportPolicy

## NOTES

## RELATED LINKS

[Get-AzNetAppFilesVolume](./Get-AzNetAppFilesVolume.md)
 [New-AzNetAppFilesVolume](./New-AzNetAppFilesVolume.md)
 [Update-AzNetAppFilesVolume](./Update-AzNetAppFilesVolume.md)
 [Remove-AzNetAppFilesVolume](./Remove-AzNetAppFilesVolume.md)