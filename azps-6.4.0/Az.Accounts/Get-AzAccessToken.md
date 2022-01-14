---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azaccesstoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzAccessToken.md
ms.openlocfilehash: 5b40b147690cf45f5f6ceba6821c3ad104410a43
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136179690"
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

### Contoh 1 Dapatkan token akses mentah untuk titik akhir ARM
```powershell
PS C:\> Get-AzAccessToken
```

Dapatkan token akses dari titik akhir ResourceManager untuk akun saat ini

### Contoh 2 Dapatkan token akses mentah AAD titik akhir grafik
```powershell
PS C:\> Get-AzAccessToken -ResourceTypeName AadGraph
```

Dapatkan token akses AAD grafik akhir untuk akun saat ini

### Contoh 3 Dapatkan token akses mentah untuk AAD titik akhir grafik mentah
```powershell
PS C:\> Get-AzAccessToken -ResourceUrl "https://graph.windows.net/"
```

Dapatkan token akses AAD grafik akhir untuk akun saat ini

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
Nama tipe sumber daya opsional, nilai yang didukung: AadGraph, AnalysisServices, Arm, Attestation, Batch, DataLake, KeyVault, OperationalInsights, ResourceManager, Storage, Synapse. Nilai default adalah Arm jika tidak ditentukan.

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
Url sumber daya untuk yang Anda minta tokennya, misalnya http://graph.windows.net/ ' '.

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

### System.String

## CATATAN

## RELATED LINKS
