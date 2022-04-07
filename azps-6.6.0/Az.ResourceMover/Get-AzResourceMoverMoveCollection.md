---
external help file: ''
Module Name: Az.ResourceMover
online version: https://docs.microsoft.com/powershell/module/az.resourcemover/get-azresourcemovermovecollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Get-AzResourceMoverMoveCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ResourceMover/help/Get-AzResourceMoverMoveCollection.md
ms.openlocfilehash: 096328f3c6832341042be07d643a5996dac8061a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140460638"
---
# Get-AzResourceMoverMoveCollection

## SYNOPSIS
Dapatkan koleksi untuk dipindahkan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resourcemover/get-azresourcemovermovecollection) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzResourceMoverMoveCollection [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzResourceMoverMoveCollection -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzResourceMoverMoveCollection -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan koleksi untuk dipindahkan.

## EXAMPLES

### Contoh 1: Dapatkan detail tentang semua koleksi Pindahkan dalam langganan
```powershell
PS C:\>Get-AzResourceMoverMoveCollection  -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

Etag                                   Location      Name                                Type                             
----                                   --------      ----                                ----                             
"270119e0-0000-0c00-0000-5f5c94940000" centraluseuap PS-centralus-westcentralus-demoRMS  Microsoft.Migrate/moveCollections
"39015ed4-0000-0c00-0000-5f5ce2760000" centraluseuap PS-centralus-westcentralus-demo2RMS Microsoft.Migrate/moveCollections
"1000b505-0000-0c00-0000-5f69db6e0000" centraluseuap MoveCollection-cus-eus-ccy         Microsoft.Migrate/moveCollections


```

Dapatkan detail tentang semua koleksi Pindahkan dalam langganan.

### Contoh 2: Dapatkan detail koleksi Pindahkan dengan nama koleksi pemindahan tertentu dalam langganan
```powershell
PS C:\>Get-AzResourceMoverMoveCollection -ResourceGroupName "RG-MoveCollection-demoRMS" -Name "PS-centralus-westcentralus-demoRMS"

Etag                                   Location      Name                               Type                             
----                                   --------      ----                               ----                             
"22006609-0000-3300-0000-602169590000" centraluseuap PS-centralus-westcentralus-demoRMS Microsoft.Migrate/moveCollections

```

Dapatkan detail koleksi Pindahkan dengan nama koleksi pemindahan tertentu dalam langganan.

### Contoh 3: Dapatkan detail kumpulan Pindahkan dengan nama grup sumber daya tertentu dalam langganan
```powershell
PS C:\> Get-AzResourceMoverMoveCollection -ResourceGroupName "RG-MoveCollection-demoRMS" 

Location    Name                               Type
--------    ----                               ----
eastus2     PS-centralus-westcentralus-demoRM  Microsoft.Migrate/moveCollections
Etag                                   Location      Name                                Type                             
----                                   --------      ----                                ----                             
"22006609-0000-3300-0000-602169590000" centraluseuap PS-centralus-westcentralus-demoRMS  Microsoft.Migrate/moveCollections
"4e02b0a9-0000-0c00-0000-5fd101cc0000" centraluseuap PS-centralus-westcentralus-demo2RMS Microsoft.Migrate/moveCollections

```

Dapatkan detail Kumpulan Pemindahan dengan nama grup sumber daya yang ditentukan dalam langganan.

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

### -Nama
Pindahkan nama koleksi.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: MoveCollectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ResourceMover.Models.Api202101.IMoveCollection

## CATATAN

ALIAS

## RELATED LINKS

