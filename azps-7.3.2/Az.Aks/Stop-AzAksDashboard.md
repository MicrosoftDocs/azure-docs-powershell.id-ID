---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Aks.dll-Help.xml
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/stop-azaksdashboard
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Stop-AzAksDashboard.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Stop-AzAksDashboard.md
ms.openlocfilehash: 7d4706d26f0163565b1c8854f53387ed03069254
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143292257"
---
# Stop-AzAksDashboard

## SYNOPSIS
Hentikan terowongan Kubectl SSH yang dibuat di Start-AzKubernetesDashboard.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.aks/stop-azaksdashboard) untuk informasi terbaru.

## SYNTAX

```
Stop-AzAksDashboard [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Hentikan terowongan Kubectl SSH yang dibuat di Start-AzKubernetesDashboard.

## EXAMPLES

### Contoh 1
```powershell
Stop-AzKubernetesDashboard
```

Hentikan penyiapan terowongan SSH yang sudah ada dengan menjalankan Start-AzKubernetesDashboard.

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

### -PassThru
Mengembalikan true jika terowongan SSH ditutup.

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

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengesampingkan langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak mempengaruhi cmdlet berikutnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
