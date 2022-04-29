---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationActionObject.md
ms.openlocfilehash: 53b0ae6f26e7951c7e694ac80554bee8aaa327e5
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144228557"
---
# New-AzSecurityAutomationActionObject

## SYNOPSIS
Membuat objek tindakan otomatisasi keamanan baru

## SYNTAX

### SecurityAutomationActionLogicApp (Default)
```
New-AzSecurityAutomationActionObject -LogicAppResourceId <String> -Uri <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SecurityAutomationActionEventHub
```
New-AzSecurityAutomationActionObject -EventHubResourceId <String> -ConnectionString <String>
 [-SasPolicyName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SecurityAutomationActionWorkspace
```
New-AzSecurityAutomationActionObject -WorkspaceResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek tindakan otomatisasi keamanan baru

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSecurityAutomationActionObject -WorkspaceResourceId '/subscriptions/64ac75e7-15ff-4963-8c07-a16016505e0f/resourceGroups/sampleResourceGroup/providers/Microsoft.OperationalInsights/workspaces/surashed-test'
```

Membuat tindakan otomatisasi keamanan baru dengan jenis ruang kerja

### Contoh 2
```powershell
PS C:\> New-AzSecurityAutomationActionObject -LogicAppResourceId '/subscriptions/03b601f1-7eca-4496-8f8d-355219eee254/resourceGroups/sampleResourceGroup/providers/Microsoft.Logic/workflows/LA' -Uri 'https://dummy.com/'
```

Membuat tindakan otomatisasi keamanan baru dengan jenis logicApp

### Contoh 3
```powershell
PS C:\> New-AzSecurityAutomationActionObject -EventHubResourceId 'subscriptions/03b601f1-7eca-4496-8f8d-355219eee254/resourceGroups/sampleResourceGroup/providers/Microsoft.EventHub/namespaces/cus-wsp-fake-assessment/eventhubs/cus-wsp-fake-assessment' -ConnectionString 'Endpoint=sb://dummy/;SharedAccessKeyName=dummy;SharedAccessKey=dummy;EntityPath=dummy'
```

Membuat tindakan otomatisasi keamanan baru dengan jenis hub genap

## PARAMETERS

### -ConnectionString
String koneksi Pusat Aktivitas target

```yaml
Type: String
Parameter Sets: SecurityAutomationActionEventHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventHubResourceId
ID Sumber Daya Azure Pusat Aktivitas target

```yaml
Type: String
Parameter Sets: SecurityAutomationActionEventHub
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicAppResourceId
ID Sumber Daya Azure Logic App yang dipicu.
Ini juga dapat berada di langganan lain, mengingat Anda memiliki izin untuk memicu Aplikasi Logika

```yaml
Type: String
Parameter Sets: SecurityAutomationActionLogicApp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasPolicyName
Nama kebijakan SAS Pusat Aktivitas target

```yaml
Type: String
Parameter Sets: SecurityAutomationActionEventHub
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri
Titik akhir URI pemicu Aplikasi Logika (tidak akan disertakan dalam respons apa pun)

```yaml
Type: String
Parameter Sets: SecurityAutomationActionLogicApp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceResourceId
ID Sumber Daya Azure Ruang Kerja Analitik Log yang sepenuhnya memenuhi syarat

```yaml
Type: String
Parameter Sets: SecurityAutomationActionWorkspace
Aliases:

Required: True
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

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationAction

## NOTES

## RELATED LINKS
