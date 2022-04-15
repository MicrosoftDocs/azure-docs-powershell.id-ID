---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsedroppedsqlpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseDroppedSqlPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseDroppedSqlPool.md
ms.openlocfilehash: 95ad959ac367ada9bd130593b2e325df701c53bb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142337363"
---
# Get-AzSynapseDroppedSqlPool

## SYNOPSIS
Mendapatkan cadangan kolam renang Sql yang jatuh dari Kolam Synapse Sql.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsedroppedsqlpool) untuk informasi terbaru.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzSynapseDroppedSqlPool -ResourceGroupName <String> -WorkspaceName <String> [-Name <String>]
 [-DeletionDate <DateTime>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzSynapseDroppedSqlPool [-DeletionDate <DateTime>] [-ResourceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseDroppedSqlPool** mendapatkan cadangan kumpulan SQL yang dihapus yang ditentukan yang bisa Anda pulihkan, atau semua cadangan yang dihapus yang dapat Anda pulihkan di ruang kerja. 

## EXAMPLES

### Contoh 1: Dapatkan sqlpool yang dijatuhkan tertentu dari kumpulan sql
```powershell
PS C:\> Get-AzSynapseDroppedSqlPool -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace -Name "ContosoSqlPool"
```

Cmdlet mengambil sqlpools jatuh untuk kolam renang sql.

### Contoh 2: Get all dropped sqlpool on a workspace
```
PS C:\>Get-AzSynapseDroppedSqlPool -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace"
```

Perintah ini mendapatkan semua sqlpool yang tersedia di ruang kerja tertentu.

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

### -PenghapusanDate
Tanggal penghapusan Azure Synaspe SQL Database untuk mengambil cadangan, dengan presisi milidetik (misalnya 2016-02-23T00:21:22.847Z)

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Kolam renang Sql Synapse.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

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
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Masukkan Id Sumber Daya Kumpulan Sql yang Dihapus.

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseResourceGroup

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSDroppedSqlPoolBackupModel

## CATATAN

## RELATED LINKS
