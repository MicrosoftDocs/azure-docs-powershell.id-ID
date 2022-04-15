---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicySqlSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicySqlSetting.md
ms.openlocfilehash: 8180208501512fd4bf97dd7276d6f1cfc7075ab6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142491101"
---
# New-AzFirewallPolicySqlSetting

## SYNOPSIS
Membuat Pengaturan SQL baru untuk Kebijakan Azure Firewall

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azfirewallpolicysqlsetting) untuk informasi terbaru.

## SYNTAX

```
New-AzFirewallPolicySqlSetting [-AllowSqlRedirect] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzFirewallPolicySqlSetting** membuat SQL Mengatur Objek untuk Kebijakan Azure Firewall

## EXAMPLES

### 1. Buat pengaturan SQL yang memungkinkan lalu lintas mode pengalihan server SQL
```powershell
PS C:\> New-AzFirewallPolicySqlSetting -AllowSqlRedirect
```

Contoh ini membuat objek pengaturan SQL dengan pengaturan izinkan pengalihan sql.

## PARAMETERS

### -AllowSqlRedirect
Izinkan lalu lintas mode pengalihan server SQL.
Secara default, jenis lalu lintas ini tidak diperbolehkan.

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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicySqlSetting

## CATATAN

## RELATED LINKS
