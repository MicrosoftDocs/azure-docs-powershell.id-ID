---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/get-aznetappfilessubvolume
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesSubvolume.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/Get-AzNetAppFilesSubvolume.md
ms.openlocfilehash: 06074aa1b67786ed70682e0b5fcbd80d6b5f836d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145553597"
---
# Get-AzNetAppFilesSubvolume

## SYNOPSIS
Mendapatkan detail subvolume Azure NetApp Files (ANF).

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzNetAppFilesSubvolume -ResourceGroupName <String> -AccountName <String> -PoolName <String>
 [-VolumeName <String>] [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzNetAppFilesSubvolume [-Name <String>] -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzNetAppFilesSubvolume [-Name <String>] -VolumeObject <PSNetAppFilesVolume>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzNetAppFilesSubvolume** mendapatkan detail Subvolume ANF.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzNetAppFilesVolume -ResourceGroupName "MyRG" -AccountName "MyAnfAccount" -PoolName "MyAnfPool" -VolumeName "MyAnfVolume" -Name "MyAnfSubvolume"

ResourceGroupName : myrg
Id                : /subscriptions/69a75bda-882e-44d5-8431-63421204132a/resourceGroups/myrg/providers/Microsoft.NetApp/netAppAccounts/myanfaccount/capacityPools/myanfpool/volumes/myanfvolume/subvolumes/myanfsubvolume
Name              : myanfaccount/myanfpool/myanfvolume/myanfsubvolume
Type              : Microsoft.NetApp/netAppAccounts/capacityPools/volumes/subvolumes
Etag              :
Path              : /subvolumePath
Size              :
ParentPath        :
ProvisioningState : Succeeded
```

Cmdlet **Get-AzNetAppFilesSubvolume** mendapatkan detail Subvolume ANF.

## PARAMETERS

### -AccountName
Nama akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
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

### -Name
Nama Subvolume ANF

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SubvolumeName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolName
Nama kumpulan ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya Subvolume ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya Subvolume ANF

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VolumeName
Nama volume ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeObject
Objek volume yang berisi Subvolume yang akan dikembalikan

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolume
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolume

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesVolume

## NOTES

## RELATED LINKS

[New-AzNetAppFilesSubvolume](./New-AzNetAppFilesSubvolume.md)
 [Update-AzNetAppFilesSubvolume](./Update-AzNetAppFilesSubvolume.md)
 [Remove-AzNetAppFilesSubvolume](./Remove-AzNetAppFilesSubvolume.md)
 [Get-AzNetAppFilesSubvolumeMetadata](./Get-AzNetAppFilesSubvolumeMetadata.md)
