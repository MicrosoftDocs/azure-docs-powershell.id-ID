---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/set-aztemplatespec
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzTemplateSpec.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzTemplateSpec.md
ms.openlocfilehash: 1a6cc8fda9a2d8da3400a7a47df901bee254fae9
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145638854"
---
# Set-AzTemplateSpec

## SYNOPSIS
Memodifikasi Spesifikasi Templat.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/set-aztemplatespec) untuk informasi terbaru.

## SYNTAX

### FromJsonStringParameterSet (Default)
```
Set-AzTemplateSpec [-Location <String>] [-Tag <Hashtable>] [-UIFormDefinitionFile <String>]
 [-UIFormDefinitionString <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByIdParameterSet
```
Set-AzTemplateSpec [-ResourceId] <String> [[-Description] <String>] [[-DisplayName] <String>]
 [-Location <String>] [-Tag <Hashtable>] [-UIFormDefinitionFile <String>] [-UIFormDefinitionString <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByIdFromJsonFileParameterSet
```
Set-AzTemplateSpec [-ResourceId] <String> [-Version] <String> [[-Description] <String>]
 [[-DisplayName] <String>] [-Location <String>] [-Tag <Hashtable>] -TemplateFile <String>
 [-VersionDescription <String>] [-UIFormDefinitionFile <String>] [-UIFormDefinitionString <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByIdFromJsonParameterSet
```
Set-AzTemplateSpec [-ResourceId] <String> [-Version] <String> [[-Description] <String>]
 [[-DisplayName] <String>] [-Location <String>] [-Tag <Hashtable>] -TemplateJson <String>
 [-VersionDescription <String>] [-UIFormDefinitionFile <String>] [-UIFormDefinitionString <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByNameParameterSet
```
Set-AzTemplateSpec [-ResourceGroupName] <String> [-Name] <String> [[-Description] <String>]
 [[-DisplayName] <String>] [-Location <String>] [-Tag <Hashtable>] [-UIFormDefinitionFile <String>]
 [-UIFormDefinitionString <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateVersionByNameFromJsonFileParameterSet
```
Set-AzTemplateSpec [-ResourceGroupName] <String> [-Name] <String> [-Version] <String> [[-Description] <String>]
 [[-DisplayName] <String>] [-Location <String>] [-Tag <Hashtable>] -TemplateFile <String>
 [-VersionDescription <String>] [-UIFormDefinitionFile <String>] [-UIFormDefinitionString <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateVersionByNameFromJsonParameterSet
```
Set-AzTemplateSpec [-ResourceGroupName] <String> [-Name] <String> [-Version] <String> [[-Description] <String>]
 [[-DisplayName] <String>] [-Location <String>] [-Tag <Hashtable>] -TemplateJson <String>
 [-VersionDescription <String>] [-UIFormDefinitionFile <String>] [-UIFormDefinitionString <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memodifikasi Spesifikasi Templace. Jika Spesifikasi Templat dengan nama dan/atau versi tertentu yang ditentukan belum ada, spesifikasi tersebut akan dibuat.

Saat memodifikasi konten Templat ARM versi Spesifikasi Templat, konten dapat berasal dari string JSON mentah (menggunakan set parameter **UpdateVersionByNameFromJsonParameterSet** ) atau dari file JSON/Bicep tertentu (menggunakan set parameter **UpdateVersionByNameFromJsonFileParameterSet** ).

## EXAMPLES

### Contoh 1
```powershell
$templateJson = @"
{
    "$schema": "http://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {},
    "resources": []
}
"@
Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec' -Version 'v1.0' -Location 'West US' -TemplateJson $templateJson
```

Memodifikasi versi "v1.0" dari Spesifikasi Templat bernama "myTemplateSpec". Versi yang ditentukan akan memiliki $templateJson sebagai konten Templat ARM versi. Jika Spesifikasi Templat akar dan/atau versi belum ada, mereka akan dibuat.


**Catatan:** 

* Templat ARM dalam contoh adalah no-op karena tidak berisi sumber daya aktual.
* Lokasi hanya diperlukan ketika Spesifikasi Templat belum ada

### Contoh 2
```powershell
Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec' -Version 'v2.0' -Location 'West US' -TemplateFile 'myTemplateContent.json'
```

Memodifikasi versi "v2.0" dari Spesifikasi Templat bernama "myTemplateSpec". Versi yang ditentukan akan memiliki konten dari file lokal "myTemplateContent.json" sebagai konten Templat ARM versi. Jika Spesifikasi Templat akar dan/atau versi belum ada, mereka akan dibuat.

**Catatan:** Lokasi hanya diperlukan ketika Spesifikasi Templat belum ada

### Contoh: 3
```powershell
Set-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'myTemplateSpec'  -Location 'West US' -Description 'My updated Template Spec'
```

Memodifikasi deskripsi Spesifikasi Templat bernama "myTemplateSpec" dalam grup sumber daya "myRG". Jika Spesifikasi Templat belum ada, Spesifikasi templat akan dibuat.

**Catatan:** Lokasi hanya diperlukan ketika Spesifikasi Templat belum ada

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
Position: 1
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
Position: 2
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

### -Name
Nama spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: 1
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
Position: 0
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Hashtable tag untuk spesifikasi templat dan/atau versi

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

### -TemplateFile
Jalur file ke file JSON/Bicep templat Azure Resource Manager lokal.

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

### -UIFormDefinitionFile
UIForm untuk sumber daya templatespec

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

### -UIFormDefinitionString
UIForm untuk sumber daya templatespec

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

### -Versi
Versi spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: UpdateVersionByIdFromJsonFileParameterSet, UpdateVersionByIdFromJsonParameterSet, UpdateVersionByNameFromJsonFileParameterSet, UpdateVersionByNameFromJsonParameterSet
Aliases:

Required: True
Position: 3
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSTemplateSpec

## NOTES

## RELATED LINKS
