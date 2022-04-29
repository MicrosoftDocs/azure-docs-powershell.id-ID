---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/get-azaksversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
ms.openlocfilehash: f862b26ab2d36cf49deb9048794642f69766e7fa
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144196887"
---
# Get-AzAksVersion

## SYNOPSIS
Melihat daftar versi yang tersedia untuk membuat kluster Kubernetes terkelola.
Operasi mengembalikan properti dari setiap orkestrator termasuk versi, peningkatan yang tersedia, dan apakah versi atau peningkatan tersebut dalam pratinjau.

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

