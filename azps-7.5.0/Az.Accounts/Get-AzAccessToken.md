---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azaccesstoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
ms.openlocfilehash: 346d37a05f2942b29ad64033a5d4abc61b9f97d7
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145787334"
---
# Get-AzAccessToken

## SYNOPSIS
Mendapatkan token akses mentah. Saat menggunakan -ResourceUrl, pastikan nilainya cocok dengan lingkungan Azure saat ini. Anda dapat merujuk ke nilai `(Get-AzContext).Environment`.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/get-azaccesstoken) untuk informasi terbaru.

## SYNTAX

### KnownResourceTypeName (Default)
```
Get-AzAccessToken [-ResourceTypeName <String>] [-TenantId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ResourceUrl
```
Get-AzAccessToken -ResourceUrl <String> [-TenantId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan token akses

## EXAMPLES

### Contoh 1 Dapatkan token akses untuk titik akhir ARM
```powershell
Get-AzAccessToken
```

Mendapatkan token akses akun saat ini untuk titik akhir ResourceManager

### Contoh 2 Dapatkan token akses untuk titik akhir Microsoft Graph
```powershell
Get-AzAccessToken -ResourceTypeName MSGraph
```

Mendapatkan token akses titik akhir Microsoft Graph untuk akun saat ini

### Contoh 3 Dapatkan token akses untuk titik akhir Microsoft Graph
```powershell
Get-AzAccessToken -ResourceUrl "https://graph.microsoft.com/"
```

Mendapatkan token akses titik akhir Microsoft Graph untuk akun saat ini

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

### -ResourceTypeName
Nama jenis sumber daya opsional, nilai yang didukung: AadGraph, AnalysisServices, Arm, Attestation, Batch, DataLake, KeyVault, MSGraph, OperationalInsights, ResourceManager, Storage, Synapse. Nilai defaultnya adalah Arm jika tidak ditentukan.

```yaml
Type: System.String
Parameter Sets: KnownResourceTypeName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceUrl
Url sumber daya untuk itu Anda meminta token, misalnya 'https://graph.microsoft.com/'.

```yaml
Type: System.String
Parameter Sets: ResourceUrl
Aliases: Resource, ResourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantId
Id Penyewa Opsional. Gunakan id penyewa dari konteks default jika tidak ditentukan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAccessToken

## NOTES

## RELATED LINKS
