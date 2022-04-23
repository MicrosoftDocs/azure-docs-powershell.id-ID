---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesqlpoolgeobackup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSqlPoolGeoBackup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSqlPoolGeoBackup.md
ms.openlocfilehash: 105e9f5a89e16d71e4f830fecabf4199a8e8fca5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143322767"
---
# Get-AzSynapseSqlPoolGeoBackup

## SYNOPSIS
Mendapatkan cadangan geo-redundan dari Sql Pool.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsesqlpoolgeobackup) untuk informasi terbaru.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName <String> -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzSynapseSqlPoolGeoBackup [-ResourceId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseSqlPoolGeoBackup** mendapatkan cadangan geo-redundan tertentu dari SQL Pool atau semua cadangan geo-redundan yang tersedia di ruang kerja tertentu.
Cadangan geo-redundan adalah sumber daya yang dapat dipusingkan menggunakan file data dari lokasi geografis terpisah.
Anda dapat menggunakan Geo-Restore untuk memulihkan cadangan geo-redundan jika terjadi pemadaman kawasan untuk memulihkan Sql Pool ke kawasan baru.

## EXAMPLES

### Contoh 1: Dapatkan cadangan geo-redundan tertentu
```powershell
PS C:\> Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName ContosoResourceGroup -WorkspaceName "ContosoWorkspace" -Name "ContosoSqlPool"
```

Cmdlet mengambil Geo Backup untuk kolam renang sql.

### Contoh 2: Mendapatkan semua cadangan geo-redundan di ruang kerja
```
PS C:\>Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace"
```

Perintah ini mendapatkan semua cadangan geo-redundan yang tersedia di ruang kerja tertentu.

### Contoh 3: Mendapatkan semua cadangan geo-redundan di ruang kerja menggunakan pemfilteran
```
PS C:\>Get-AzSynapseSqlPoolGeoBackup -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace" -Name "Contoso*"
```

Perintah ini mendapatkan semua cadangan geo-redundan yang tersedia di ruang kerja tertentu yang dimulai dengan "Contoso".

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
Masukkan Sql Pool Geo Backup Resource Id.

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

### Microsoft.Azure.Commands.Synapse.Models.PSBackupModel

## NOTES

## RELATED LINKS
