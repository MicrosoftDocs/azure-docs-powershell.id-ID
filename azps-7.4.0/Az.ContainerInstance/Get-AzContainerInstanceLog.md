---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.containerinstance/get-azcontainerinstancelog
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceLog.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/Get-AzContainerInstanceLog.md
ms.openlocfilehash: 91ed992c698d29bf2807824b26f87ff3ecf295e5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144626016"
---
# Get-AzContainerInstanceLog

## SYNOPSIS
Dapatkan log untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/get-azcontainerinstancelog) untuk informasi terbaru.

## SYNTAX

```
Get-AzContainerInstanceLog -ContainerGroupName <String> -ContainerName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-Tail <Int32>] [-Timestamp] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan log untuk instans kontainer tertentu dalam grup sumber daya dan grup kontainer tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan log ekor instans kontainer
```powershell
Get-AzContainerInstanceLog -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName test-rg
```

```output
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
```

Dapatkan log dari test-container dalam grup kontainer test-cg.
Secara default, ini akan mengembalikan konten log hingga 4MB.

### Contoh 2: Dapatkan 2 baris log ekor instans kontainer
```powershell
Get-AzContainerInstanceLog -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName test-rg -Tail 2
```

```output
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
```

Dapatkan ekor 2 baris log dari test-container dalam grup kontainer test-cg.

## PARAMETERS

### -ContainerGroupName
Nama grup kontainer.

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

### -ContainerName
Nama instans kontainer.

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
Kredensial langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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

### -Tail
Jumlah baris yang akan ditampilkan dari ekor log instans kontainer.
Jika tidak disediakan, semua log yang tersedia ditampilkan hingga 4mb.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tanda waktu
Jika true, menambahkan tanda waktu di awal setiap baris output log.
Jika tidak disediakan, default ke false.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### System.String

## NOTES

ALIAS

## RELATED LINKS

