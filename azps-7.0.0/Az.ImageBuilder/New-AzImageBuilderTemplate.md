---
external help file: ''
Module Name: Az.ImageBuilder
online version: https://docs.microsoft.com/powershell/module/az.imagebuilder/New-AzImageBuilderTemplate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImageBuilder/help/New-AzImageBuilderTemplate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImageBuilder/help/New-AzImageBuilderTemplate.md
ms.openlocfilehash: 5c5c0ee83cfe36d8abeed183da79f41299cf4a0e
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136575358"
---
# New-AzImageBuilderTemplate

## SYNOPSIS
Membuat templat gambar mesin virtual

## SYNTAX

### FlattenParameterSet (Default)
```
New-AzImageBuilderTemplate -ImageTemplateName <String> -ResourceGroupName <String>
 -Distribute <IImageTemplateDistributor[]> -Source <IImageTemplateSource> -UserAssignedIdentityId <String>
 [-SubscriptionId <String>] [-BuildTimeoutInMinute <Int32>] [-Customize <IImageTemplateCustomizer[]>]
 [-Location <String>] [-Tag <Hashtable>] [-VMProfileOsdiskSizeInGb <Int32>] [-VMProfileVmSize <String>]
 [-VnetConfigSubnetId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### JsonTemplate
```
New-AzImageBuilderTemplate -ImageTemplateName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-JsonTemplatePath <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat templat gambar mesin virtual

## EXAMPLES

### Contoh 1: Membuat templat gambar mesin virtual
```powershell
PS C:\> $srcPlatform = New-AzImageBuilderSourceObject -SourceTypePlatformImage -Publisher 'Canonical'  -Offer 'UbuntuServer' -Sku '18.04-LTS' -Version 'latest'
PS C:\> $disSharedImg = New-AzImageBuilderDistributorObject -SharedImageDistributor -ArtifactTag @{tag='dis-share'} -GalleryImageId '/subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/wyunchi-imagebuilder/providers/Microsoft.Compute/galleries/testsharedgallery/images/imagedefinition-linux/versions/1.0.0' -ReplicationRegion 'eastus2' -RunOutputName 'runoutput-01'  -ExcludeFromLatest $false
PS C:\> $customizer = New-AzImageBuilderCustomizerObject -ShellCustomizer -CustomizerName 'CheckSumCompareShellScript' -ScriptUri 'https://raw.githubusercontent.com/danielsollondon/azvmimagebuilder/master/quickquickstarts/customizeScript2.sh' -Sha256Checksum 'ade4c5214c3c675e92c66e2d067a870c5b81b9844b3de3cc72c49ff36425fc93'
PS C:\> $userAssignedIdentity = '/subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourcegroups/wyunchi-imagebuilder/providers/Microsoft.ManagedIdentity/userAssignedIdentities/image-builder-user-assign-identity'
PS C:\> New-AzImageBuilderTemplate -ImageTemplateName platform-shared-img -ResourceGroupName wyunchi-imagebuilder -Source $srcPlatform -Distribute $disSharedImg -Customize $customizer -Location eastus  -UserAssignedIdentityId $userAssignedIdentity

Location Name                Type
-------- ----                ----
PlanInfoPlanName      :
PlanInfoPlanPublisher :
Sku                   : 18.04-LTS
Version               : latest
PlanInfo              : Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.PlatformImagePurchasePlan
```

Perintah ini akan membuat templat gambar mesin virtual.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -BuildTimeoutInMinute
Durasi maksimum untuk menunggu selagi membuat templat gambar.
Menghilangkan atau menentukan 0 untuk menggunakan default (4 jam).

```yaml
Type: System.Int32
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Customize
Menentukan properti yang digunakan untuk menjelaskan langkah-langkah kustomisasi gambar, seperti Sumber gambar dll. Untuk membuat, lihat bagian CATATAN untuk mengKUSTOMISASI properti dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.IImageTemplateCustomizer[]
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
kawasan HideParameter Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Distribute
Distribusi menargetkan tempat output gambar harus masuk.
Untuk membuat, lihat bagian CATATAN untuk MENDISTRIBUSIKAN properti dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.IImageTemplateDistributor[]
Parameter Sets: FlattenParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageTemplateName
Nama Templat gambar.

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

### -JsonTemplatePath
Jalur file templat gambar yang diformat json.

```yaml
Type: System.String
Parameter Sets: JsonTemplate
Aliases:

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
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -Source
Menjelaskan sumber gambar mesin virtual untuk membuat, mengkustomisasi, dan mendistribusikan.
Untuk membuat, lihat bagian CATATAN untuk properti SUMBER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.IImageTemplateSource
Parameter Sets: FlattenParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.

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
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentityId
Id identitas yang ditetapkan pengguna.

```yaml
Type: System.String
Parameter Sets: FlattenParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMProfileOsdiskSizeInGb
Ukuran disk OS di GB.
Menghilangkan atau menentukan 0 untuk menggunakan ukuran disk OS default Azure.

```yaml
Type: System.Int32
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMProfileVmSize
Ukuran mesin virtual yang digunakan untuk menyusun, mengustomisasi, dan mengambil gambar.
Menghilangkan atau menentukan string kosong untuk menggunakan nilai default (Standard_D1_v2).

```yaml
Type: System.String
Parameter Sets: FlattenParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VnetConfigSubnetId
Id sumber daya subnet yang sudah ada sebelumnya.

```yaml
Type: System.String
Parameter Sets: FlattenParameterSet
Aliases:

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.IImageTemplate

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


MENGUSTOMISASI <IImageTemplateCustomizer[]>: Menentukan properti yang digunakan untuk menjelaskan langkah-langkah kustomisasi gambar, seperti Sumber gambar, dll.
  - `Type <String>`: Tipe alat kustomisasi yang ingin Anda gunakan di Gambar. Misalnya, "Shell" dapat menjadi mengustomisasi shell
  - `[Name <String>]`: Nama yang Mudah Digunakan untuk memberikan konteks tentang fungsi langkah kustomisasi ini

DISTRIBUTE <IImageTemplateDistributor[]>: Distribusi target tempat output gambar harus masuk.
  - `RunOutputName <String>`: Nama yang akan digunakan untuk RunOutput terkait.
  - `Type <String>`: Tipe distribusi.
  - `[ArtifactTag <IImageTemplateDistributorArtifactTags>]`: Tag yang akan diterapkan pada artifak setelah sudah dibuat/diperbarui oleh distributor.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

SUMBER <IImageTemplateSource> : Menjelaskan sumber gambar mesin virtual untuk membangun, mengkustomisasi dan mendistribusikan.
  - `Type <String>`: Menentukan tipe gambar sumber yang Anda inginkan untuk dimulai.

## RELATED LINKS

