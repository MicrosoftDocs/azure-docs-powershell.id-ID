---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azserviceendpointpolicydefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzServiceEndpointPolicyDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzServiceEndpointPolicyDefinition.md
ms.openlocfilehash: 3519eeb9f5710c3cc94dd367365ff776b436e542
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139999717"
---
# New-AzServiceEndpointPolicyDefinition

## SYNOPSIS
Membuat definisi kebijakan titik akhir layanan.

## SYNTAX

```
New-AzServiceEndpointPolicyDefinition -Name <String> [-Description <String>] [-ServiceResource <String[]>]
 [-Service <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzServiceEndpointPolicyDefinition** membuat definisi kebijakan titik akhir layanan.

## EXAMPLES

### Contoh 1: Membuat kebijakan titik akhir layanan
```powershell
$policydef= New-AzServiceEndpointPolicyDefinition -Name "ServiceEndpointPolicyDefinition1" -ResourceGroupName "ResourceGroup01" -Service "Microsoft.Storage" -ServiceResources "subscriptions/sub1" -Description "New Definition"
```

Perintah ini membuat definisi kebijakan titik akhir layanan dengan nama ServiceEndpointPolicyDefinition1, layanan Microsoft. Storage, langganan/sub1 sumber daya layanan dan deskripsi "Definisi Baru" yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01 dan menyimpannya di $policydef sumber daya.

### Contoh 2

Membuat definisi kebijakan titik akhir layanan. (otomatisgenerated)

<!-- Aladdin Generated Example -->
```powershell
New-AzServiceEndpointPolicyDefinition -Description 'New Definition' -Name 'ServiceEndpointPolicyDefinition1' -Service 'Microsoft.Storage' -ServiceResource <String[]>
```

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

### -Deskripsi
Deskripsi definisi

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

### -Nama
Nama kebijakan titik akhir layanan

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

### -Layanan
Nama layanan

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

### -ServiceResource
Daftar sumber daya layanan

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSServiceEndpointPolicyDefinition

## CATATAN

## RELATED LINKS

[Add-AzServiceEndpointPolicyDefinition](./Add-AzServiceEndpointPolicyDefinition.md)

[Get-AzServiceEndpointPolicyDefinition](./Get-AzServiceEndpointPolicyDefinition.md)

[Remove-AzServiceEndpointPolicyDefinition](./Remove-AzServiceEndpointPolicyDefinition.md)

[Set-AzServiceEndpointPolicyDefinition](./Set-AzServiceEndpointPolicyDefinition.md)
