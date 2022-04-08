---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermmanagedapplicationdefinition
schema: 2.0.0
ms.openlocfilehash: f6644d4db3d1601351931fb1c57561df2b1a32fcad21caca10ecadbf1b2475a3
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140852742"
---
# Get-AzureRmManagedApplicationDefinition

## SYNOPSIS
Definisi aplikasi yang dikelola

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByNameAndResourceGroup (Default)
```
Get-AzureRmManagedApplicationDefinition [-Name <String>] -ResourceGroupName <String> [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetById
```
Get-AzureRmManagedApplicationDefinition -Id <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmManagedApplicationDefinition** mendapatkan definisi aplikasi yang dikelola

## EXAMPLES

### Contoh 1: Dapatkan semua definisi aplikasi yang dikelola di bawah grup sumber daya
```
PS C:\>Get-AzureRmManagedApplicationDefinition -ResourceGroupName "MyRG"
```

Perintah ini mendapatkan definisi aplikasi terkelola di bawah grup sumber daya "MyRG"

### Contoh 2: Mendapatkan definisi aplikasi terkelola
```
PS C:\>Get-AzureRmManagedApplicationDefinition -ResourceGroupName "MyRG" -Name "myManagedAppDef"
```

Perintah ini mendapatkan definisi aplikasi terkelola "myManagedAppDef" di bawah grup sumber daya "MyRG"

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai versi terbaru yang tersedia.

```yaml
Type: String
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
ID definisi aplikasi terkelola yang sepenuhnya memenuhi syarat, termasuk langganan.
misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}

```yaml
Type: String
Parameter Sets: GetById
Aliases: ResourceId, ManagedApplicationDefinitionId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama definisi aplikasi yang dikelola.

```yaml
Type: String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

```yaml
Type: SwitchParameter
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
Type: String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

## RELATED LINKS
