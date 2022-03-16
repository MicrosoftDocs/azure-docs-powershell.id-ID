---
external help file: ''
Module Name: Az.Aks
online version: https://docs.microsoft.com/powershell/module/az.aks/get-azaksversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Aks/Aks/help/Get-AzAksVersion.md
ms.openlocfilehash: 56b3d5376137ed555e42ea91c8a52e7f679762a5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140063597"
---
# Get-AzAksVersion

## SYNOPSIS
Daftar versi yang tersedia untuk membuat kluster Ruang Kerja terkelola.
Operasi akan mengembalikan properti setiap pengelola, termasuk versi, pemutakhiran yang tersedia, dan apakah versi atau pemutakhiran tersebut sedang dalam pratinjau.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.aks/get-azaksversion) untuk informasi terkini.

## SYNTAX

```
Get-AzAksVersion -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Daftar versi yang tersedia untuk membuat kluster Ruang Kerja terkelola.
Operasi akan mengembalikan properti setiap pengelola, termasuk versi, pemutakhiran yang tersedia, dan apakah versi atau pemutakhiran tersebut sedang dalam pratinjau.

## EXAMPLES

### Contoh 1: Versi daftar yang tersedia untuk membuat kluster Kjadwal terkelola.
```powershell
PS C:\> Get-AzAksVersion -location eastus

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

Daftar versi yang tersedia untuk membuat kluster Ruang Kerja terkelola.

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
Nama kawasan Azure yang didukung.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Aks.Models.Api20190801.IOrchestratorVersionProfileListResult

## CATATAN

ALIAS

## RELATED LINKS

