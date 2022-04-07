---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/Az.storagesync/new-Azstoragesyncservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/New-AzStorageSyncService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/New-AzStorageSyncService.md
ms.openlocfilehash: 664829d065e91219371046bbe3ec0e85a94ec837
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140499351"
---
# New-AzStorageSyncService

## SYNOPSIS
Perintah ini akan membuat layanan sinkronisasi penyimpanan baru dalam grup sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storagesync/new-azstoragesyncservice) untuk informasi terkini.

## SYNTAX

```
New-AzStorageSyncService [-ResourceGroupName] <String> [-Name] <String> [-Location] <String>
 [[-IncomingTrafficPolicy] <String>] [-Tag <Hashtable>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Layanan sinkronisasi penyimpanan adalah sumber daya tingkat teratas untuk Sinkronisasi File Azure. Perintah ini akan membuat layanan sinkronisasi penyimpanan baru dalam grup sumber daya. Kami menyarankan untuk membuat layanan sinkronisasi penyimpanan sesingkas mungkin yang benar-benar diperlukan untuk membedakan grup server berbeda di organisasi Anda. Layanan sinkronisasi penyimpanan berisi grup sinkronisasi dan juga berfungsi sebagai target untuk mendaftarkan server Anda. Server hanya dapat didaftarkan ke satu layanan sinkronisasi penyimpanan. Jika server perlu berpartisipasi dalam menyinkronkan kumpulan file yang sama, daftarkan file ke layanan sinkronisasi penyimpanan yang sama.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzStorageSyncService -ResourceGroupName "myResourceGroup" -Location "myLocation" -StorageSyncServiceName "myStorageSyncServiceName" -IncomingTrafficPolicy "AllowAllTraffic"
```

Perintah ini akan membuat layanan sinkronisasi penyimpanan.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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

### -IncomingTrafficPolicy
Storage Sync Service IncomingTrafficPolicy

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AllowVirtualNetworksOnly, AllowAllTraffic

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Storage Layanan Sinkronisasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama layanan sinkronisasi penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageSyncServiceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Storage Tag Layanan Sinkronisasi.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.StorageSync.Models.PSStorageSyncService

## CATATAN

## RELATED LINKS
