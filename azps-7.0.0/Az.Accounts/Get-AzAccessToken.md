---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azaccesstoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
ms.openlocfilehash: 94b54a42058d82def1e2eda295159d1de2841410
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136557561"
---
# Get-AzAccessToken

## SYNOPSIS
Dapatkan token akses mentah. Ketika menggunakan -ResourceUrl, pastikan nilai cocok dengan lingkungan Azure saat ini. Anda mungkin merujuk ke nilai `(Get-AzContext).Environment` .

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

Dapatkan token akses titik akhir Microsoft Graph untuk akun saat ini

### Contoh 3 Dapatkan token akses untuk titik akhir Microsoft Graph akhir
```powershell
PS C:\> Get-AzAccessToken -ResourceUrl "https://graph.microsoft.com/"
```

Dapatkan token akses titik akhir Microsoft Graph untuk akun saat ini

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
Url sumber daya untuk yang Anda minta tokennya, misalnya https://graph.microsoft.com/ ' '.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAccessToken

## CATATAN

## RELATED LINKS
