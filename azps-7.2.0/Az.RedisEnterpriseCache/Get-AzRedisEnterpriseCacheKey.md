---
external help file: ''
Module Name: Az.RedisEnterpriseCache
online version: https://docs.microsoft.com/powershell/module/az.redisenterprisecache/get-azredisenterprisecachekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/Get-AzRedisEnterpriseCacheKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RedisEnterpriseCache/help/Get-AzRedisEnterpriseCacheKey.md
ms.openlocfilehash: 198bb45d9ae23628359c766bf3c62fb2557dd648
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140228635"
---
# Get-AzRedisEnterpriseCacheKey

## SYNOPSIS
Mengambil semua kunci akses untuk database Redis Enterprise.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.redisenterprisecache/get-azredisenterprisecachekey) untuk informasi terkini.

## SYNTAX

```
Get-AzRedisEnterpriseCacheKey -ClusterName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengambil semua kunci akses untuk database Redis Enterprise.

## EXAMPLES

### Contoh 1: Dapatkan kunci akses database
```powershell
PS C:\> Get-AzRedisEnterpriseCacheKey -Name "MyCache" -ResourceGroupName "MyGroup"

PrimaryKey                                   SecondaryKey
----------                                   ------------
primary-key                                  secondary-key

```

Perintah ini mendapatkan kunci akses rahasia yang digunakan untuk mengotentikan koneksi ke database cache Redis Enterprise bernama MyCache.

## PARAMETERS

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.RedisEnterpriseCache.Models.Api20210301.IAccessKeys

## CATATAN

ALIAS

## RELATED LINKS

