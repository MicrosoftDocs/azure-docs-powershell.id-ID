---
external help file: Microsoft.Azure.Commands.EventHub.dll-Help.xml
Module Name: AzureRM.EventHub
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.eventhub/remove-azurermeventhubnamespace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Remove-AzureRmEventHubNamespace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/EventHub/Commands.EventHub/help/Remove-AzureRmEventHubNamespace.md
ms.openlocfilehash: 6df8d5539bf340df5e00ad69ac557bc2cbb8ccaa
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142098369"
---
# Remove-AzureRmEventHubNamespace

## SYNOPSIS
Menghapus ruang nama Hub Kejadian tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### NamespaceParameterSet (Default)
```
Remove-AzureRmEventHubNamespace [-ResourceGroupName] <String> [-Name] <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NamespaceInputObjectSet
```
Remove-AzureRmEventHubNamespace [-InputObject] <PSNamespaceAttributes> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NamespaceResourceIdParameterSet
```
Remove-AzureRmEventHubNamespace [-ResourceId] <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzureRmEventHubNamespace menghapus dan menghapus ruang nama Hub Kejadian yang ditentukan.

## EXAMPLES

### Contoh 1
```
PS C:\> Remove-AzureRmEventHubNamespace -ResourceGroupName MyResourceGroupName -Name MyNamespaceName
```

Menghapus ruang \`nama Hub Kejadian MyNamespaceName\` dalam grup \`sumber daya MyResourceGroupName\`.

### Contoh 2.1 - InputObject - Menggunakan Variabel:
```
PS C:\> $inputObject = Get-AzureRmEventHubNamespace <params> 
PS C:\> Remove-AzureRmEventHubNamespace -InputObject $inputObject
```

### Contoh 2.1 - InputObject - Menggunakan Piping:
```
PS C:\> Get-AzureRmEventHubNamespace <params> | Remove-AzureRmEventHubNamespace
```

### Contoh 3.1 - ResourceId - Using Variable
```
PS C:\> $resourceid = Get-AzureRmEventHubNamespace <params>
PS C:\> Remove-AzureRmEventHubNamespace -ResourceId $resourceid.Id
```

### Contoh 3.2 - ResourceId - Using Piping:
```
PS C:\> Get-AzureRmResource -ResourceType Microsoft.EventHub/Namespaces | Remove-AzureRmEventHubNamespace
```

### Contoh 3.3 - ResourceId - Menggunakan String:
```
PS C:\> Remove-AzureRmEventHubNamespace -ResourceId "/subscriptions/xxx-xxxxx-xxxxxx-xxxxxx/resourceGroups/ResourceGroupName/providers/Microsoft.EventHub/namespaces/NamespaceName"
```

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Ruang Nama EventHubs

```yaml
Type: Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes
Parameter Sets: NamespaceInputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Ruang Nama EventHub

```yaml
Type: System.String
Parameter Sets: NamespaceParameterSet
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Menentukan ini akan mengembalikan true jika perintah berhasil.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: NamespaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya Ruang Nama EventHubs

```yaml
Type: System.String
Parameter Sets: NamespaceResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes
Parameter: InputObject (ByValue)

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS
