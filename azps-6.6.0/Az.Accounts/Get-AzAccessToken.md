---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azaccesstoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
ms.openlocfilehash: bc0b79be0a3187e4a6127d48b7e34fc7a6f63812
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140314729"
---
# Get-AzAccessToken

## SYNOPSIS
Dapatkan token akses mentah. Ketika menggunakan -ResourceUrl, pastikan nilai cocok dengan lingkungan Azure saat ini. Anda mungkin merujuk ke nilai `(Get-AzContext).Environment`.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.accounts/get-azaccesstoken) untuk informasi terkini.

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
PS C:\> Get-AzAccessToken
```

Dapatkan token akses akun saat ini untuk titik akhir ResourceManager

### Contoh 2 Dapatkan token akses untuk Microsoft Graph titik akhir
```powershell
PS C:\> Get-AzAccessToken -ResourceTypeName MSGraph
```

Dapatkan token akses titik akhir Microsoft Graph akhir untuk akun saat ini

### Contoh 3 Dapatkan token akses untuk titik akhir Microsoft Graph akhir
```powershell
PS C:\> Get-AzAccessToken -ResourceUrl "https://graph.microsoft.com/"
```

Dapatkan token akses titik akhir Microsoft Graph akhir untuk akun saat ini

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
Nama tipe sumber daya opsional, nilai yang didukung: AadGraph, AnalysisServices, Arm, Attestation, Batch, DataLake, KeyVault, MSGraph, OperationalInsights, ResourceManager, Storage, Synapse. Nilai default adalah Arm jika tidak ditentukan.

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
Url sumber daya untuk yang Anda minta tokennya, misalnya 'https://graph.microsoft.com/'.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAccessToken

## CATATAN

## RELATED LINKS
