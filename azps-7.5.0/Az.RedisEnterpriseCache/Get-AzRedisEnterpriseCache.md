---
external help file: ''
Module Name: Az.RedisEnterpriseCache
online version: https://docs.microsoft.com/powershell/module/az.redisenterprisecache/get-azredisenterprisecache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/Get-AzRedisEnterpriseCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/Get-AzRedisEnterpriseCache.md
ms.openlocfilehash: 1d345a491a05f8372584fd67ee223959d678a1ca
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145646140"
---
# Get-AzRedisEnterpriseCache

## SYNOPSIS
Mendapatkan informasi tentang kluster Redis Enterprise dan database terkait.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.redisenterprisecache/get-azredisenterprisecache) untuk informasi terbaru.

## SYNTAX

### ListBySubscriptionId (Default)
```
Get-AzRedisEnterpriseCache [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzRedisEnterpriseCache -ClusterName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListByResourceGroup
```
Get-AzRedisEnterpriseCache -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang kluster Redis Enterprise dan database terkait.

## EXAMPLES

### Contoh 1: Mendapatkan cache Redis Enterprise berdasarkan nama
```powershell
Get-AzRedisEnterpriseCache -ResourceGroupName "MyGroup" -Name "MyCache"
```

```output
Location Name    Type                            Zone Database
-------- ----    ----                            ---- --------
West US  MyCache Microsoft.Cache/redisEnterprise      {default}

```

Perintah ini mendapatkan informasi tentang cache Redis Enterprise bernama MyCache.

### Contoh 2: Mencantumkan setiap cache Redis Enterprise dalam grup sumber daya
```powershell
Get-AzRedisEnterpriseCache -ResourceGroupName "MyGroup"
```

```output
Location Name     Type                            Zone      Database
-------- ----     ----                            ----      --------
East US  MyCache1 Microsoft.Cache/redisEnterprise           {default}
East US  MyCache2 Microsoft.Cache/redisEnterprise {1, 2, 3} {default}

```

Perintah ini mendapatkan informasi tentang setiap cache Redis Enterprise dalam grup sumber daya yang ditentukan.

### Contoh 3: Mencantumkan setiap cache Redis Enterprise dalam langganan
```powershell
Get-AzRedisEnterpriseCache
```

```output
Location    Name     Type                            Zone      Database
--------    ----     ----                            ----      --------
East US     MyCache1 Microsoft.Cache/redisEnterprise           {default}
East US     MyCache2 Microsoft.Cache/redisEnterprise {1, 2, 3} {default}
West US     MyCache3 Microsoft.Cache/redisEnterprise           {default}
Central US  MyCache4 Microsoft.Cache/redisEnterprise {1, 2, 3} {default}

```

Perintah ini mendapatkan informasi tentang setiap cache Redis Enterprise dalam langganan saat ini.

## PARAMETERS

### -ClusterName
Nama kluster Redis Enterprise.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, ListByResourceGroup
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Models.Api20210301.ICluster

## NOTES

ALIAS

## RELATED LINKS

