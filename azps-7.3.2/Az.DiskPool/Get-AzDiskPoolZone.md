---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/get-azdiskpoolzone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Get-AzDiskPoolZone.md
ms.openlocfilehash: 956f1a0a05449c9d54339b51987d4cc4868a2eae
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141893096"
---
# Get-AzDiskPoolZone

## SYNOPSIS
Mencantumkan Sku Kumpulan Disk yang tersedia di lokasi Azure.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.diskpool/get-azdiskpoolzone) untuk informasi terbaru.

## SYNTAX

```
Get-AzDiskPoolZone -Location <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan Sku Kumpulan Disk yang tersedia di lokasi Azure.

## EXAMPLES

### Contoh 1: Mencantumkan zona ketersediaan untuk lokasi
```powershell
PS C:\> Get-AzDiskPoolZone -Location eastus

SkuName  SkuTier  AvailabilityZone AdditionalCapability
-------  -------  ---------------- --------------------
Basic    Basic    {3, 1, 2}
Standard Standard {3, 1, 2}
Premium  Premium  {3, 1, 2}
```

Perintah mencantumkan semua zona ketersediaan untuk suatu lokasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Api20210801.IDiskPoolZoneInfo

## CATATAN

ALIAS

## RELATED LINKS

