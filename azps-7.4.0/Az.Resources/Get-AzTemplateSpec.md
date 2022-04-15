---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-aztemplatespec
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTemplateSpec.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzTemplateSpec.md
ms.openlocfilehash: 11733e128be5802d73b3da03359f55e7d9e05925
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142420869"
---
# Get-AzTemplateSpec

## SYNOPSIS
Mendapatkan atau mencantumkan Spesifikasi Templat

## SYNTAX

### ListTemplateSpecsParameterSet (Default)
```
Get-AzTemplateSpec [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetTemplateSpecByNameParameterSet
```
Get-AzTemplateSpec [-ResourceGroupName] <String> [-Name] <String> [[-Version] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetTemplateSpecByIdParameterSet
```
Get-AzTemplateSpec [[-Version] <String>] [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini dapat digunakan untuk mencantumkan Spesifikasi Templat dalam grup langganan/sumber daya atau mendapatkan Spesifikasi Templat tertentu berdasarkan nama atau id. Ketika mendapatkan Spesifikasi Templat tertentu menurut nama/id, versi tertentu dapat diambil secara opsional dengan menentukan nama versi melalui parameter **-Version** . Ketika **-Version** digunakan, hanya detail versi tertentu yang akan ada dalam **. Versi* pada objek Spesifikasi Templat yang dikembalikan. Jika tidak ada versi tertentu yang ditentukan saat mengambil Spesifikasi Templat menurut nama/id, semua versi akan ada dalam **. Properti versi* objek yang dikembalikan.

**Catatan**: Ketika mencantumkan semua Spesifikasi Templat dalam langganan atau grup sumber daya, setiap Spesifikasi Templat yang dikembalikan *". Properti Versions"* akan *null*. Informasi versi hanya disertakan ketika parameter -Name atau -ResourceId disediakan (misalnya: Anda meminta spesifikasi/versi templat tertentu).

## EXAMPLES

### Contoh 1: Spesifikasi Templat Daftar dalam langganan saat ini
```powershell
Get-AzTemplateSpec
```

Mencantumkan semua Spesifikasi Templat dalam langganan saat ini.

### Contoh 2: Spesifikasi Templat Daftar dalam grup sumber daya
```powershell
Get-AzTemplateSpec -ResourceGroupName 'myRG'
```

Mencantumkan semua Spesifikasi Templat dalam grup sumber daya 'myRG' langganan saat ini.

### Contoh 3: Dapatkan Spesifikasi Templat (dengan semua versi) menurut nama
```powershell
Get-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'MyTemplateSpec'
```

Mendapatkan informasi tentang Spesifikasi Templat bernama 'MyTemplateSpec' dalam grup sumber daya 'myRG'.

**Catatan**: Semua versi Spesifikasi Templat akan hadir dalam "*. Properti versi*" dari objek yang dikembalikan.

### Contoh 4: Dapatkan Spesifikasi Templat (versi tertentu) menurut nama
```powershell
Get-AzTemplateSpec -ResourceGroupName 'myRG' -Name 'MyTemplateSpec' -Version 'v1.0'
```

Mendapatkan informasi tentang versi 'v1.0' dari Spesifikasi Templat bernama 'MyTemplateSpec' dalam grup sumber daya 'myRG'.

**Catatan**: *". Properti versi"* dari objek yang dikembalikan hanya akan berisi versi tertentu yang diminta.

### Contoh 5: Dapatkan Spesifikasi Templat (dengan semua versi) menurut id sumber daya
```powershell
Get-AzTemplateSpec -ResourceId '/subscriptions/{subId}/resourceGroups/myRG/providers/Microsoft.Resources/templateSpecs/MyTemplateSpec'
```

Mendapatkan informasi tentang Spesifikasi Templat bernama 'MyTemplateSpec' dalam grup sumber daya 'myRG' subId\} langganan\{.

**Catatan**: Semua versi Spesifikasi Templat akan hadir dalam "*. Properti versi*" dari objek yang dikembalikan.

### Contoh 6: Dapatkan Spesifikasi Templat (versi tertentu) menurut id sumber daya
```powershell
Get-AzTemplateSpec -ResourceId '/subscriptions/{subId}/resourceGroups/myRG/providers/Microsoft.Resources/templateSpecs/MyTemplateSpec' -Version 'v1.0'
```

Mendapatkan informasi tentang versi 'v1.0' dari Spesifikasi Templat bernama 'MyTemplateSpec' dalam grup sumber daya 'myRG' subId\} langganan\{.

**Catatan**: *". Properti versi"* dari objek yang dikembalikan hanya akan berisi versi tertentu yang diminta.

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

### -Nama
Nama spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: GetTemplateSpecByNameParameterSet
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
Parameter Sets: ListTemplateSpecsParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: GetTemplateSpecByNameParameterSet
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
Parameter Sets: GetTemplateSpecByIdParameterSet
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Versi spesifikasi templat.

```yaml
Type: System.String
Parameter Sets: GetTemplateSpecByNameParameterSet, GetTemplateSpecByIdParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSTemplateSpec

## CATATAN

## RELATED LINKS
