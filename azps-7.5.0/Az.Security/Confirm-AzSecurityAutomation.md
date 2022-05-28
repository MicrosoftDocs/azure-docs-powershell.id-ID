---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Confirm-AzSecurityAutomation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Confirm-AzSecurityAutomation.md
ms.openlocfilehash: c4a17ced1078628734d2f1b9eed4fff8a6365b56
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145637396"
---
# Confirm-AzSecurityAutomation

## SYNOPSIS
Memvalidasi model otomatisasi keamanan sebelum membuat atau memperbarui. Setiap kesalahan validasi dikembalikan ke klien

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.security/confirm-azsecurityautomation) untuk informasi terbaru.

## SYNTAX

### ResourceGroupLevelResource (Default)
```
Confirm-AzSecurityAutomation -ResourceGroupName <String> -Name <String> -Location <String> [-Etag <String>]
 [-Tag <Hashtable>] [-Description <String>] [-IsEnabled <Boolean>] -Scope <PSSecurityAutomationScope[]>
 -Source <PSSecurityAutomationSource[]> -Action <PSSecurityAutomationAction[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Confirm-AzSecurityAutomation -ResourceId <String> -Location <String> [-Etag <String>] [-Tag <Hashtable>]
 [-Description <String>] [-IsEnabled <Boolean>] -Scope <PSSecurityAutomationScope[]>
 -Source <PSSecurityAutomationSource[]> -Action <PSSecurityAutomationAction[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Confirm-AzSecurityAutomation [-Location <String>] [-Etag <String>] [-Tag <Hashtable>] [-Description <String>]
 [-IsEnabled <Boolean>] [-Scope <PSSecurityAutomationScope[]>] [-Source <PSSecurityAutomationSource[]>]
 -Action <PSSecurityAutomationAction[]> -InputObject <PSSecurityAutomation>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Memvalidasi model otomatisasi keamanan sebelum membuat atau memperbarui. Setiap kesalahan validasi dikembalikan ke klien

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Confirm-AzSecurityAutomation -Name 'SampleAutomation' -ResourceGroupName 'SampleResourceGroup' -Description 'Sample security automation' -Scope $scopes -Source $sources -Action $actions
```

Memvalidasi bahwa pembuatan otomatisasi keamanan bernama "SampleAutomation" di bawah grup sumber daya bernama "SampleResourceGroup"

## PARAMETERS

### -Tindakan
Kumpulan tindakan yang dipicu jika semua evaluasi aturan yang dikonfigurasi, dalam setidaknya satu kumpulan aturan, adalah benar

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationAction[]
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
Deskripsi otomatisasi keamanan

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

### -Etag
Tag entitas digunakan untuk membandingkan dua entitas atau lebih dari sumber daya yang diminta yang sama

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

### -InputObject
Objek Input.

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomation
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsEnabled
Apakah aturan diaktifkan.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi.

```yaml
Type: System.String
Parameter Sets: ResourceGroupLevelResource, ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceGroupLevelResource
Aliases:

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
Parameter Sets: ResourceGroupLevelResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya keamanan yang ingin Anda panggil perintahnya.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cakupan
Kumpulan cakupan tempat logika otomatisasi keamanan diterapkan.
Cakupan yang didukung adalah langganan itu sendiri atau grup sumber daya di bawah langganan tersebut.
Otomatisasi hanya akan berlaku pada cakupan yang ditentukan

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationScope[]
Parameter Sets: ResourceGroupLevelResource, ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationScope[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sumber
Kumpulan jenis peristiwa sumber yang mengevaluasi kumpulan aturan otomatisasi keamanan

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationSource[]
Parameter Sets: ResourceGroupLevelResource, ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationSource[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomation

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
