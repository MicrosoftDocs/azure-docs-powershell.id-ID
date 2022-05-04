---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://docs.microsoft.com/powershell/module/az.sql/get-azsqlservertrustgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerTrustGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlServerTrustGroup.md
ms.openlocfilehash: 41c29ae4afedb2c0b14234e61365e8c59fabdeae
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144573715"
---
# Get-AzSqlServerTrustGroup

## SYNOPSIS
Mendapatkan informasi tentang Grup Kepercayaan Server.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.sql/get-azsqlservertrustgroup) untuk informasi terbaru.

## SYNTAX

### ListByLocationSet (Default)
```
Get-AzSqlServerTrustGroup [-ResourceGroupName] <String> [-Location] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByName
```
Get-AzSqlServerTrustGroup [-ResourceGroupName] <String> [-Location] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListByInstanceSet
```
Get-AzSqlServerTrustGroup [-ResourceGroupName] <String> [-InstanceName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIdSet
```
Get-AzSqlServerTrustGroup [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSqlServerTrustGroup** mendapatkan informasi tentang Grup Kepercayaan Server dan anggotanya untuk langganan saat ini. Berdasarkan set parameter cmdlet ini dapat mengambil Grup Kepercayaan Server tertentu, semua Grup Kepercayaan Server di lokasi tertentu atau Grup Kepercayaan Server yang telah menentukan AzureSQL Managed Instance sebagai anggota.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSqlServerTrustGroup -ResourceGroupName "ResourceGroup01" -Location "West Europe" -Name "ServerTrustGroup01"
```

Mendapatkan informasi tentang Grup Kepercayaan Server bernama ServerTrustGroup01 dalam grup sumber daya ResourceGroup01 di lokasi Eropa Barat.

### Contoh 2
```powershell
Get-AzSqlServerTrustGroup -ResourceGroupName "ResourceGroup01" -Location "West Europe"
```

Mendapatkan informasi tentang semua Grup Kepercayaan Server di lokasi Eropa Barat dalam grup sumber daya ResourceGroup01.

### Contoh 3
```powershell
Get-AzSqlServerTrustGroup -ResourceGroupName "ResourceGroup01" -InstanceName "ManagedInstance01"
```

Mendapatkan informasi tentang semua Grup Kepercayaan Server yang memiliki instans terkelola ManagedInstance01 sebagai anggota.

### Contoh 4
```powershell
Get-AzSqlServerTrustGroup -ResourceId "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroup01/providers/Microsoft.Sql/locations/WestEurope/serverTrustGroups/ServerTrustGroup01"
```

Mendapatkan informasi tentang Grup Kepercayaan Server yang ditentukan oleh id-nya.

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

### -InstanceName
Nama instans terkelola yang merupakan anggota Grup Kepercayaan Server untuk diambil.

```yaml
Type: System.String
Parameter Sets: ListByInstanceSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Grup Kepercayaan Server yang akan diambil.

```yaml
Type: System.String
Parameter Sets: ListByLocationSet, GetByName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Grup Kepercayaan Server yang akan diambil.

```yaml
Type: System.String
Parameter Sets: GetByName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ListByLocationSet, GetByName, ListByInstanceSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya instans yang akan digunakan

```yaml
Type: System.String
Parameter Sets: ResourceIdSet
Aliases:

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

## OUTPUTS

### Microsoft.Azure.Commands.Sql.ServerTrustGroup.Model.AzureSqlServerTrustGroupModel

## NOTES

## RELATED LINKS
