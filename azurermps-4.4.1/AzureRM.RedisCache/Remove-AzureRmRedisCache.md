---
external help file: Microsoft.Azure.Commands.RedisCache.dll-Help.xml
Module Name: AzureRM.RedisCache
ms.assetid: A22D930B-5026-4915-B498-EE31153E1E9A
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/Remove-AzureRmRedisCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RedisCache/Commands.RedisCache/help/Remove-AzureRmRedisCache.md
ms.openlocfilehash: a9a879386bdbc22eef3094e2f1d0cf19cd42cc45
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422711"
---
# Remove-AzureRmRedisCache

## SYNOPSIS
Menghapus Cache Redis.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmRedisCache -ResourceGroupName <String> -Name <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmRedisCache** menghapus Singgahan Azure Redis.

## EXAMPLES

### Contoh 1: Hapus Cache Redis dan kembalikan hasil
```
PS C:\>Remove-AzureRmRedisCache -ResourceGroupName "ResourceGroup03" -Name "myCache" -Force -PassThru
True
```

Perintah ini akan menghapus Cache Redis dan menampilkan apakah operasi berhasil.

### Contoh 2: Hapus Cache Redis dan tidak menampilkan hasil
```
PS C:\>Remove-AzureRmRedisCache -ResourceGroupName "ResourceGroup03" -Name "myCache" -Force
```

Perintah ini akan menghapus Cache Redis.
Karena *parameter PassThru* tidak ditentukan, hasil operasi tidak ditampilkan.

## PARAMETERS

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -Nama
Menentukan nama Cache Redis yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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
Menentukan nama grup sumber daya yang berisi Singgahan Redis yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
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

### Tidak ada
Anda dapat pipa input ke cmdlet ini menurut nama, tetapi tidak menurut nilai.

## OUTPUTS

### Boolean
Mengembalikan $True jika tidak ada pengecualian terjadi.

## CATATAN

## RELATED LINKS

[Get-AzureRmRedisCache](./Get-AzureRmRedisCache.md)

[New-AzureRmRedisCache](./New-AzureRmRedisCache.md)

[Set-AzureRmRedisCache](./Set-AzureRmRedisCache.md)


