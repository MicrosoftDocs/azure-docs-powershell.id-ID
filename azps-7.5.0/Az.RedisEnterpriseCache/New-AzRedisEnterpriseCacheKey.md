---
external help file: ''
Module Name: Az.RedisEnterpriseCache
online version: https://docs.microsoft.com/powershell/module/az.redisenterprisecache/new-azredisenterprisecachekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/New-AzRedisEnterpriseCacheKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/New-AzRedisEnterpriseCacheKey.md
ms.openlocfilehash: a66051f56cd7633d2af7a765a9bce22788607a41
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144194328"
---
# New-AzRedisEnterpriseCacheKey

## SYNOPSIS
Meregenerasi kunci akses untuk database Redis Enterprise.

## SYNTAX

```
New-AzRedisEnterpriseCacheKey -ClusterName <String> -ResourceGroupName <String> -KeyType <AccessKeyType>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Meregenerasi kunci akses untuk database Redis Enterprise.

## EXAMPLES

### Contoh 1: Meregenerasi kunci akses utama
```powershell
New-AzRedisEnterpriseCacheKey -Name "MyCache" -ResourceGroupName "MyGroup" -KeyType "Primary"
```

```output
PrimaryKey                                   SecondaryKey
----------                                   ------------
new-primary-key                              secondary-key

```

Perintah ini meregenerasi kunci akses rahasia utama yang digunakan untuk mengautentikasi koneksi ke database cache Redis Enterprise bernama MyCache.

### Contoh 2: Meregenerasi kunci akses sekunder
```powershell
New-AzRedisEnterpriseCacheKey -Name "MyCache" -ResourceGroupName "MyGroup" -KeyType "Secondary"
```

```output
PrimaryKey                                   SecondaryKey
----------                                   ------------
primary-key                                  new-secondary-key

```

Perintah ini meregenerasi kunci akses rahasia sekunder yang digunakan untuk mengautentikasi koneksi ke database cache Redis Enterprise bernama MyCache.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -ClusterName
Nama kluster Redis Enterprise.

```yaml
Type: System.String
Parameter Sets: (All)
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

### -KeyType
Kunci akses mana yang akan diregenerasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Support.AccessKeyType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Models.Api20210301.IAccessKeys

## NOTES

ALIAS

## RELATED LINKS

