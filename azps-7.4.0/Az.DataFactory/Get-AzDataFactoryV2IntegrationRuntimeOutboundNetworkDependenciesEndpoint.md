---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactoryV2.dll-Help.xml
Module Name: Az.DataFactory
online version: https://docs.microsoft.com/powershell/module/az.datafactory/get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint.md
ms.openlocfilehash: 718005d75302030458805a07c2db13ddc57afbd1
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144620510"
---
# Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint

## SYNOPSIS
Mendapatkan daftar dependensi jaringan keluar untuk runtime integrasi Azure-SSIS tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datafactory/get-azdatafactoryv2integrationruntimeoutboundnetworkdependenciesendpoint) untuk informasi terbaru.

## SYNTAX

### ByIntegrationRuntimeName (Default)
```
Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint [-Name] <String>
 [-ResourceGroupName] <String> [-DataFactoryName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByResourceId
```
Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint [-ResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByIntegrationRuntimeObject
```
Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint [-InputObject] <PSIntegrationRuntime>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint menyediakan daftar dependensi jaringan keluar untuk runtime integrasi SSIS di Azure Data Factory yang bergabung dengan jaringan virtual.

## EXAMPLES

### Contoh 1: Mencantumkan dependensi jaringan keluar
```powershell
Get-AzDataFactoryV2IntegrationRuntimeOutboundNetworkDependenciesEndpoint -Name 'integrationRuntime1' -ResourceGroupName 'testrg' -DataFactoryName 'newtestDataFactory1'
```

```output
Category                                 EndPoint
--------                                 --------
Azure Data Factory (Management)          [{"DomainName":"wu.frontend.clouddatahub.net","EndpointDetails":[{"Port":443}]}]
Azure Storage (Management)               [{"DomainName":"*.blob.core.windows.net","EndpointDetails":[{"Port":443}]},{"DomainName":"*.table.core.windows.net","EndpointDetails":[{"Port":443}]}]
Event Hub (Logging)                      [{"DomainName":"*.servicebus.windows.net","EndpointDetails":[{"Port":443}]}]
```

## PARAMETERS

### -DataFactoryName
Nama pabrik data.

```yaml
Type: System.String
Parameter Sets: ByIntegrationRuntimeName
Aliases:

Required: True
Position: 1
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

### -InputObject
Objek runtime integrasi.

```yaml
Type: Microsoft.Azure.Commands.DataFactoryV2.Models.PSIntegrationRuntime
Parameter Sets: ByIntegrationRuntimeObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama runtime integrasi.

```yaml
Type: System.String
Parameter Sets: ByIntegrationRuntimeName
Aliases: IntegrationRuntimeName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByIntegrationRuntimeName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya Azure.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.DataFactoryV2.Models.PSIntegrationRuntime

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.DataFactoryV2.Models.PSIntegrationRuntimeOutboundNetworkDependenciesCategoryEndpoint, Microsoft.Azure.PowerShell.Cmdlets.DataFactoryV2, Version=1.13.1.0, Culture=neutral, PublicKeyToken=null]]

## NOTES
Kata kunci: azure, azurerm, arm, sumber daya, manajemen, manajer, data, pabrik, salinan, aktivitas, runtime integrasi

## RELATED LINKS

[Get-AzDataFactoryV2IntegrationRuntime]()
