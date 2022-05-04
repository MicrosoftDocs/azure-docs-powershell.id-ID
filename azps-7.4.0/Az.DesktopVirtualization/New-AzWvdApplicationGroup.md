---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/new-azwvdapplicationgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdApplicationGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdApplicationGroup.md
ms.openlocfilehash: d3a98a52ae402dd17cfce35014779460b1673f6c
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144693860"
---
# New-AzWvdApplicationGroup

## SYNOPSIS
Membuat atau memperbarui applicationGroup.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.desktopvirtualization/new-azwvdapplicationgroup) untuk informasi terbaru.

## SYNTAX

```
New-AzWvdApplicationGroup -Name <String> -ResourceGroupName <String>
 -ApplicationGroupType <ApplicationGroupType> -HostPoolArmPath <String> [-SubscriptionId <String>]
 [-Description <String>] [-FriendlyName <String>] [-IdentityType <ResourceIdentityType>] [-Kind <String>]
 [-Location <String>] [-ManagedBy <String>] [-MigrationRequestMigrationPath <String>]
 [-MigrationRequestOperation <Operation>] [-PlanName <String>] [-PlanProduct <String>]
 [-PlanPromotionCode <String>] [-PlanPublisher <String>] [-PlanVersion <String>] [-SkuCapacity <Int32>]
 [-SkuFamily <String>] [-SkuName <String>] [-SkuSize <String>] [-SkuTier <SkuTier>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui applicationGroup.

## EXAMPLES

### Contoh 1: Membuat Windows Virtual Desktop ApplicationGroup berdasarkan nama
```powershell
New-AzWvdApplicationGroup -ResourceGroupName ResourceGroupName `
                            -Name ApplicationGroupName `
                            -Location 'eastus' `
                            -FriendlyName 'Friendly Name' `
                            -Description 'Description' `
                            -HostPoolArmPath '/subscriptions/SubscriptionId/resourcegroups/ResourceGroupName/providers/Microsoft.DesktopVirtualization/hostPools/HostPoolName' `
                            -ApplicationGroupType 'RemoteApp'
```

```output
Location   Name                 Type
--------   ----                 ----
eastus     ApplicationGroupName Microsoft.DesktopVirtualization/applicationgroups
```

Perintah ini membuat Windows Virtual Desktop ApplicationGroup dalam Grup Sumber Daya.

### Contoh 2: Membuat Windows Virtual Desktop ApplicationGroup berdasarkan nama
```powershell
New-AzWvdApplicationGroup -ResourceGroupName ResourceGroupName `
                            -Name ApplicationGroupName `
                            -Location 'eastus' `
                            -FriendlyName 'Friendly Name' `
                            -Description 'Description' `
                            -HostPoolArmPath '/subscriptions/SubscriptionId/resourcegroups/ResourceGroupName/providers/Microsoft.DesktopVirtualization/hostPools/HostPoolName' `
                            -ApplicationGroupType 'Desktop'
```

```output
Location   Name                 Type
--------   ----                 ----
eastus     ApplicationGroupName Microsoft.DesktopVirtualization/applicationgroups
```

Perintah ini membuat Windows Virtual Desktop ApplicationGroup dalam Grup Sumber Daya.

## PARAMETERS

### -ApplicationGroupType
Jenis Sumber Daya ApplicationGroup.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.ApplicationGroupType
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

### -Deskripsi
Deskripsi ApplicationGroup.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Nama yang mudah diingat dari ApplicationGroup.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPoolArmPath
Jalur arm HostPool applicationGroup.

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

### -IdentityType
Jenis identitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.ResourceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jenis
Metadata yang digunakan oleh portal/peralatan/dll untuk merender pengalaman UX yang berbeda untuk sumber daya dengan jenis yang sama; misalnya ApiApps adalah jenis Microsoft.Web/sites.
Jika didukung, penyedia sumber daya harus memvalidasi dan mempertahankan nilai ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi geografis tempat sumber daya berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedBy
ID sumber daya yang sepenuhnya memenuhi syarat dari sumber daya yang mengelola sumber daya ini.
Menunjukkan apakah sumber daya ini dikelola oleh sumber daya Azure lain.
Jika ada, penyebaran mode lengkap tidak akan menghapus sumber daya jika dihapus dari templat karena dikelola oleh sumber daya lain.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationRequestMigrationPath
Jalur ke objek warisan untuk dimigrasikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationRequestOperation
Jenis operasi untuk migrasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.Operation
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama grup aplikasi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ApplicationGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanName
Nama yang ditentukan pengguna dari Artefak Pihak ke-3 yang sedang diakui.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanProduct
Artefak Pihak ke-3 yang sedang diakui.
Mis.
NewRelic.
Peta produk ke OfferID yang ditentukan untuk artefak pada saat onboarding Data Market.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanPromotionCode
Penerbit menyediakan kode promosi seperti yang disediakan di Pasar Data untuk produk/artefak tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanPublisher
Penerbit Artefak Pihak ke-3 yang sedang dibeli.
Mis.
NewRelic

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlanVersion
Versi produk/artefak yang diinginkan.

```yaml
Type: System.String
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

### -SkuCapacity
Jika SKU mendukung peluasan skala/masuk, bilangan bulat kapasitas harus disertakan.
Jika peluasan/penyempurnaan skala tidak dimungkinkan untuk sumber daya, ini dapat dihilangkan.

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

### -SkuFamily
Jika layanan memiliki generasi perangkat keras yang berbeda, untuk SKU yang sama, maka itu dapat ditangkap di sini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Nama SKUnya.
Mantan - P3.
Biasanya kode huruf+angka

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuSize
Ukuran SKU.
Ketika bidang nama adalah kombinasi tingkat dan beberapa nilai lainnya, ini akan menjadi kode mandiri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuTier
Bidang ini diperlukan untuk diimplementasikan oleh Penyedia Sumber Jika layanan memiliki lebih dari satu tingkat, tetapi tidak diperlukan pada PUT.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.SkuTier
Parameter Sets: (All)
Aliases:

Required: False
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

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IApplicationGroup

## NOTES

ALIAS

## RELATED LINKS

