---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/Az.storagesync/get-Azstoragesyncservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Get-AzStorageSyncService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Get-AzStorageSyncService.md
ms.openlocfilehash: 9b97ae923001265b4f55cba5579d80fe60e78a30
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144211619"
---
# Get-AzStorageSyncService

## SYNOPSIS
Perintah ini mencantumkan semua layanan sinkronisasi penyimpanan dalam lingkup grup langganan/sumber daya tertentu.

## SYNTAX

### ParentStringParameterSet (Default)
```
Get-AzStorageSyncService [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### StringParameterSet
```
Get-AzStorageSyncService [-ResourceGroupName] <String> [[-Name] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini mencantumkan semua layanan sinkronisasi penyimpanan dalam lingkup grup langganan/sumber daya tertentu. Ini dapat digunakan untuk juga mencantumkan atribut setiap layanan sinkronisasi penyimpanan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzStorageSyncService -ResourceGroupName "myResourceGroup"
```

Perintah ini mencantumkan semua sumber daya layanan sinkronisasi penyimpanan dalam grup sumber daya tertentu. Ini dapat digunakan untuk juga mencantumkan atribut setiap layanan sinkronisasi penyimpanan. Tentukan -StorageSyncServiceName untuk mengembalikan yang spesifik.

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

### -Name
Nama layanan sinkronisasi penyimpanan.

```yaml
Type: System.String
Parameter Sets: StringParameterSet
Aliases: StorageSyncServiceName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: ParentStringParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: StringParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.StorageSync.Models.PSStorageSyncService

## NOTES

## RELATED LINKS
