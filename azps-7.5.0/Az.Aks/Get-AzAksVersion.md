---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/get-azaksversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
ms.openlocfilehash: 45fa83b141d82c05b0b6e24f23bd95c027f2517e
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145686514"
---
# Get-AzAksVersion

## SYNOPSIS
Melihat daftar versi yang tersedia untuk membuat kluster Kubernetes terkelola.
Operasi mengembalikan properti dari setiap orkestrator termasuk versi, peningkatan yang tersedia, dan apakah versi atau peningkatan tersebut dalam pratinjau.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.aks/get-azaksversion) untuk informasi terbaru.

## SYNTAX

```
Get-AzAksVersion -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Melihat daftar versi yang tersedia untuk membuat kluster Kubernetes terkelola.
Operasi mengembalikan properti dari setiap orkestrator termasuk versi, peningkatan yang tersedia, dan apakah versi atau peningkatan tersebut dalam pratinjau.

## EXAMPLES

### Contoh 1: Mencantumkan versi yang tersedia untuk membuat kluster Kubernetes terkelola.
```powershell
Get-AzAksVersion -location eastus
```

```output
Default IsPreview OrchestratorType OrchestratorVersion
------- --------- ---------------- -------------------
                  Kubernetes       1.19.11
                  Kubernetes       1.19.13
                  Kubernetes       1.20.7
True              Kubernetes       1.20.9
                  Kubernetes       1.21.1
                  Kubernetes       1.21.2
        True      Kubernetes       1.22.1
        True      Kubernetes       1.22.2
```

Melihat daftar versi yang tersedia untuk membuat kluster Kubernetes terkelola.

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

### -Lokasi
Nama wilayah Azure yang didukung.

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
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.Api20190801.IOrchestratorVersionProfileListResult

## NOTES

ALIAS

## RELATED LINKS

