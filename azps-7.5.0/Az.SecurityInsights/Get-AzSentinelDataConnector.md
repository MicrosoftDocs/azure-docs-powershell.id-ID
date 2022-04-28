---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/get-azsentineldataconnector
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelDataConnector.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/Get-AzSentinelDataConnector.md
ms.openlocfilehash: cb6b2161ed91621c6175a3f9a71195f42eb29916
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144245402"
---
# Get-AzSentinelDataConnector

## SYNOPSIS
Mendapatkan Konektor Data. <br/><br/>
Harap dicatat bahwa dukungan otomatisasi hanya tersedia untuk konektor data berikut:
* AADDataConnector
* AATPDataConnector
* ASCDataConnector
* AwsCloudTrailDataConnector
* MCASDataConnector
* MDATPDataConnector
* OfficeDataConnector
* TIDataConnector

## SYNTAX

### WorkspaceScope (Default)
```
Get-AzSentinelDataConnector -ResourceGroupName <String> -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DataConnectorId
```
Get-AzSentinelDataConnector -ResourceGroupName <String> -WorkspaceName <String> -DataConnectorId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzSentinelDataConnector -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSentinelDataConnector** mendapatkan Konektor Data dari ruang kerja yang ditentukan.
Jika Anda menentukan parameter *DataConnectorId* , satu objek **DataConnector** dikembalikan.
Jika Anda tidak menentukan parameter *DataConnectorId* , array yang berisi semua Konektor Data di ruang kerja yang ditentukan akan dikembalikan.
Anda dapat menggunakan objek **DataConnector** untuk memperbarui Konektor Data, misalnya Anda dapat menonaktifkan **DataConnector**.

## EXAMPLES

### Contoh 1
```powershell
$DataConnectors = Get-AzSentinelDataConnector -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName"
```

Contoh ini mendapatkan semua DataConnectors di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $DataConnectors.

### Contoh 2
```powershell
$DataConnector = Get-AzSentinelDataConnector -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -DataConnectorId "MyDataConnectorId"
```

Contoh ini mendapatkan DataConnector di ruang kerja yang ditentukan, lalu menyimpannya dalam variabel $DataConnector.

### Contoh 3
```powershell
Get-AzSentinelDataConnector @SentinelConnection | Where-Object {$_.Kind -eq "Office365"}
```

Contoh ini (menggunakan objek koneksi) mendapatkan konektor data Office365.

## PARAMETERS

### -DataConnectorId
Id Konektor Data.

```yaml
Type: System.String
Parameter Sets: DataConnectorId
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, DataConnectorId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Nama Ruang Kerja.

```yaml
Type: System.String
Parameter Sets: WorkspaceScope, DataConnectorId
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

### System.String
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector
## NOTES

## RELATED LINKS
