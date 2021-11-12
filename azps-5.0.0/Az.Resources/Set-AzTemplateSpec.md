---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/set-aztemplatespec
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Set-AzTemplateSpec.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Set-AzTemplateSpec.md
ms.openlocfilehash: ff2911c1fd8e49e5057c13c086f68a2b3489ad2f
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132407593"
---
# Set-AzTemplateSpec

## SYNOPSIS
Mengubah Spesifikasi Templat.

## SINTAKS

### FromJsonStringParameterSet (Default)
```
Set-AzTemplateSpec [-Location <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByIdParameterSet
```
Set-AzTemplateSpec -ResourceId <String> [-Description <String>] [-DisplayName <String>] [-Location <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByIdFromJsonFileParameterSet
```
Set-AzTemplateSpec -ResourceId <String> -Version <String> [-Description <String>] [-DisplayName <String>]
 [-Location <String>] -TemplateFile <String> [-VersionDescription <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByIdFromJsonParameterSet
```
Set-AzTemplateSpec -ResourceId <String> -Version <String> [-Description <String>] [-DisplayName <String>]
 [-Location <String>] -TemplateJson <String> [-VersionDescription <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByNameParameterSet
```
Set-AzTemplateSpec -ResourceGroupName <String> -Name <String> [-Description <String>] [-DisplayName <String>]
 [-Location <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByNameFromJsonFileParameterSet
```
Set-AzTemplateSpec -ResourceGroupName <String> -Name <String> -Version <String> [-Description <String>]
 [-DisplayName <String>] [-Location <String>] -TemplateFile <String> [-VersionDescription <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByNameFromJsonParameterSet
```
Set-AzTemplateSpec -ResourceGroupName <String> -Name <String> -Version <String> [-Description <String>]
 [-DisplayName <String>] [-Location <String>] -TemplateJson <String> [-VersionDescription <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Mengubah Templace Spec. Jika Spesifikasi Templat dengan nama dan/atau versi tertentu belum ada, spesifikasi akan dibuat.

Saat memodifikasi konten Templat Template Spec versi ARM, konten bisa berasal dari string JSON mentah (menggunakan kumpulan parameter **UpdateVersionByNameFromJsonParameterSet)** atau dari file JSON yang ditentukan (menggunakan **UpdateVersionByNameFromJsonFileParameterSet** parameter set).

## CONTOH

### Contoh 1:
```powershell
PS C:\> $templateJson = @"
{
    "$schema": "http://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {},
    "resources": []
}
"@
PS C:\> Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec' -Version 'v1.0' -Location 'West US' -TemplateJson $templateJson
```

Mengubah versi "v1.0" dari Spesifikasi Templat bernama "myTemplateSpec". Versi yang ditentukan akan $templateJson sebagai konten Templat ARM versi. Jika Spesifikasi Templat akar dan/atau versinya belum ada, spesifikasi akan dibuat.


**Catatan:** 

* Templat ARM dalam contoh ini tidak tersedia karena tidak berisi sumber daya aktual.
* Lokasi hanya diperlukan saat Spesifikasi Templat belum ada

### Contoh 2:
```powershell
PS C:\> Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec' -Version 'v2.0' -Location 'West US' -TemplateFile 'myTemplateContent.json'
```

Mengubah versi "v2.0" dari Spesifikasi Templat bernama "myTemplateSpec". Versi tertentu akan memiliki konten dari file lokal "myTemplateContent.json" sebagai konten Templat ARM versi. Jika Spesifikasi Templat akar dan/atau versinya belum ada, spesifikasi akan dibuat.

**Catatan:** Lokasi hanya diperlukan saat Spesifikasi Templat belum ada

### Contoh 3:
```powershell
PS C:\> Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec'  -Location 'West US' -Description 'My updated Template Spec'
```

Mengubah deskripsi Spesifikasi Templat bernama "myTemplateSpec" dalam grup sumber daya "myRG". Jika Spesifikasi Templat belum ada, spesifikasi akan dibuat.

**Catatan:** Lokasi hanya diperlukan saat Spesifikasi Templat belum ada

## PARAMETERS

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

### -Deskripsi
Deskripsi spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateByIdParameterSet, UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet, UpdateByNameParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Nama tampilan spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateByIdParameterSet, UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet, UpdateByNameParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Lokasi spesifikasi templat. Hanya diperlukan jika spesifikasi templat belum ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya yang sepenuhnya memenuhi syarat dari spesifikasi templat. Contoh: /subscriptions/{subId}/resourceGroups/{rgName}/providers/Microsoft.Resources/templateSpecs/{templateSpecName}

```yaml
Type: System.String
Parameter Sets: UpdateByIdParameterSet, UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateFile
Jalur file ke file JSON templat Azure Resource Manager lokal.

```yaml
Type: System.String
Parameter Sets: UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByNameFromJsonFileParameterSet
Aliases: InputFile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateJson
JSON templat Azure Resource Manager.

```yaml
Type: System.String
Parameter Sets: UpdateVersionByIdFromJsonParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Versi spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VersionDescription
Deskripsi versi.

```yaml
Type: System.String
Parameter Sets: UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSTemplateSpec

## CATATAN

## LINK TERKAIT
