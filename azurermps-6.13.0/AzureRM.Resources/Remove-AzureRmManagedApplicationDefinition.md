---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/remove-azurermmanagedapplicationdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Remove-AzureRmManagedApplicationDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Remove-AzureRmManagedApplicationDefinition.md
ms.openlocfilehash: 62b3af8cd9e60d7a4360e5bbab0c9a33a7675961efe6dd9c5586977c26584f52
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140863604"
---
# Remove-AzureRmManagedApplicationDefinition

## SYNOPSIS
Menghapus definisi aplikasi terkelola

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### RemoveByNameAndResourceGroup (Default)
```
Remove-AzureRmManagedApplicationDefinition -Name <String> -ResourceGroupName <String> [-Force]
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RemoveById
```
Remove-AzureRmManagedApplicationDefinition -Id <String> [-Force] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmManagedApplicationDefinition** menghapus definisi aplikasi yang dikelola

## EXAMPLES

### Contoh 1: Hapus definisi aplikasi terkelola menurut ID sumber daya
```
PS C:\>$ApplicationDefinition = Get-AzureRmManagedApplicationDefinition -Name "myAppDef" -ResourceGroupName "myRG"
PS C:\>Remove-AzureRmManagedApplicationDefinition -Id $ApplicationDefinition.ResourceId -Force
```

Perintah pertama mendapatkan definisi aplikasi terkelola bernama myAppDef menggunakan cmdlet Get-AzureRmManagedApplicationDefinition.
Perintah menyimpannya di $ApplicationDefinition variabel.
Perintah kedua menghapus definisi aplikasi terkelola yang diidentifikasi oleh properti **ResourceId** $ApplicationDefinition.

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai versi terbaru yang tersedia.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Jangan minta konfirmasi.

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

### -Id
ID definisi aplikasi terkelola yang sepenuhnya memenuhi syarat, termasuk langganan.
misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}

```yaml
Type: System.String
Parameter Sets: RemoveById
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama definisi aplikasi yang dikelola.

```yaml
Type: System.String
Parameter Sets: RemoveByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

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
Parameter Sets: RemoveByNameAndResourceGroup
Aliases:

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
