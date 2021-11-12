---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
Module Name: AzureRM.SiteRecovery
ms.assetid: 99196F44-F1DB-4219-91C0-3056624ADE5B
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryReplicationProtectedItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryReplicationProtectedItem.md
ms.openlocfilehash: 0e94a46b8d6433ddd96530dc011234050398bf37
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419723"
---
# Get-AzureRmSiteRecoveryReplicationProtectedItem

## SYNOPSIS
Mendapatkan properti Item Terproteksi Pemulihan Situs Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByObject (Default)
```
Get-AzureRmSiteRecoveryReplicationProtectedItem -ProtectionContainer <ASRProtectionContainer>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectWithName
```
Get-AzureRmSiteRecoveryReplicationProtectedItem -Name <String> -ProtectionContainer <ASRProtectionContainer>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectWithFriendlyName
```
Get-AzureRmSiteRecoveryReplicationProtectedItem -FriendlyName <String>
 -ProtectionContainer <ASRProtectionContainer> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByProtectableItemObject
```
Get-AzureRmSiteRecoveryReplicationProtectedItem -ProtectableItem <ASRProtectableItem>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmSiteRecoveryReplicationProtectedItem** mendapatkan properti Item Terproteksi Pemulihan Situs Azure.

## EXAMPLES

## PARAMETERS

### -FriendlyName
Menentukan nama replikasi Item Terproteksi yang akan dapatkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ByObjectWithFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama Item Terproteksi Replikasi yang akan dapatkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ByObjectWithName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectableItem
Menentukan Item yang Dapat Diproteksi terkait dengan Replikasi Item yang Diproteksi.

```yaml
Type: Microsoft.Azure.Commands.SiteRecovery.ASRProtectableItem
Parameter Sets: ByProtectableItemObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionContainer
Menentukan objek Azure Site Recovery Protection Container.

```yaml
Type: Microsoft.Azure.Commands.SiteRecovery.ASRProtectionContainer
Parameter Sets: ByObject, ByObjectWithName, ByObjectWithFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### ASRProtectableItem
Parameter 'ProtectableItem' menerima nilai tipe 'ASRProtectableItem' dari saluran

### ASRProtectionContainer
Parameter 'ProtectionContainer' menerima nilai tipe 'ASRProtectionContainer' dari saluran

## OUTPUTS

### System.Collections.Generic.IEnumerable'1[[Microsoft.Azure.Commands.SiteRecovery.ASRReplicationProtectedItem, Microsoft.Azure.Commands.SiteRecovery, Version=2.0.1.0, Culture=neutral, PublicKeyToken=null]]

## CATATAN

## RELATED LINKS

[New-AzureRmSiteRecoveryReplicationProtectedItem](./New-AzureRmSiteRecoveryReplicationProtectedItem.md)

[Remove-AzureRmSiteRecoveryReplicationProtectedItem](./Remove-AzureRmSiteRecoveryReplicationProtectedItem.md)

[Set-AzureRmSiteRecoveryReplicationProtectedItem](./Set-AzureRmSiteRecoveryReplicationProtectedItem.md)
