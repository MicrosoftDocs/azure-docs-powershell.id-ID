---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: https://docs.microsoft.com/powershell/module/az.eventhub/get-azeventhubauthorizationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHubAuthorizationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHubAuthorizationRule.md
ms.openlocfilehash: 394a7004dfce9fd3c7513347e90c8f98befac072
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143286767"
---
# Get-AzEventHubAuthorizationRule

## SYNOPSIS
Mendapatkan detail aturan otorisasi, atau mendapatkan daftar aturan otorisasi.

## SYNTAX

### NamespaceAuthorizationRuleSet (Default)
```
Get-AzEventHubAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### EventhubAuthorizationRuleSet
```
Get-AzEventHubAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [-Eventhub] <String>
 [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AliasAuthoRuleSet
```
Get-AzEventHubAuthorizationRule [-ResourceGroupName] <String> [-Namespace] <String> [-AliasName] <String>
 [[-Name] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventHubAuthorizationRule mendapatkan detail aturan otorisasi, atau daftar semua aturan otorisasi untuk Hub Kejadian tertentu.
Jika nama aturan otorisasi disediakan, detail aturan otorisasi tunggal tersebut akan dikembalikan.
Jika nama aturan otorisasi tidak disediakan, daftar semua aturan otorisasi untuk Hub Kejadian tertentu akan dikembalikan.
Jika nama Alias (Pemulihan Bencana) disediakan, detail aturan otorisasi Ruang Nama untuk Alias yang dikonfigurasi akan dikembalikan.

## EXAMPLES

### Contoh 1: AuthorizationRule untuk namespace
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -Name MyAuthRuleName
```

Mendapatkan aturan \`otorisasi MyAuthRuleName\` di ruang \`nama MyNamespaceName\`.

### Contoh 2: AuthorizationRules untuk namespace
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -EventHubName MyEventHubName
```

Mendapatkan daftar semua aturan otorisasi di ruang \`nama MyNamespaceName\`.

### Contoh 3: AuthorizationRule untuk EventHub
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -EventHubName MyEventHubName -Name MyAuthRuleName
```

Mendapatkan aturan otorisasi MyAuthRuleName\` di Hub \`Kejadian MyEventHubName\`, yang dilingkup oleh ruang \`nama MyNamespaceName\`.\`

### Contoh 4: AuthorizationRules untuk EventHub
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -EventHubName MyEventHubName
```

Mendapatkan aturan otorisasi daftar di Hub \`Kejadian MyEventHubName\`, yang dilingkup oleh namespace \`MyNamespaceName\`.

### Contoh 5: AuthorizationRule for Alias (GeoRecovery Configuration)
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -AliasName MyAliasNameName -Name MyAuthRuleName
```

Mendapatkan aturan \`otorisasi MyAuthRuleName\` di ruang \`nama MyNamespaceName\`.

### Contoh 6: AuthorizationRules for Alias (GeoRecovery Configuration)
```powershell
Get-AzEventHubAuthorizationRule -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -AliasName MyAliasNameName
```

Mendapatkan daftar semua aturan \`otorisasi MyAuthRuleName\` di ruang \`nama MyNamespaceName\`.

## PARAMETERS

### -AliasName
Nama Alias

```yaml
Type: System.String
Parameter Sets: AliasAuthoRuleSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Eventhub
Nama Eventhub

```yaml
Type: System.String
Parameter Sets: EventhubAuthorizationRuleSet
Aliases: EventHubName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama AuthorizationRule

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AuthorizationRuleName

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama Ruang Nama

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes

## NOTES

## RELATED LINKS
