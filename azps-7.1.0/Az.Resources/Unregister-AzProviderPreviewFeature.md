---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/unregister-azproviderpreviewfeature
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Unregister-AzProviderPreviewFeature.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Unregister-AzProviderPreviewFeature.md
ms.openlocfilehash: d07cfd0425e7c6388c1884f49bb2ef68bee9dcca
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136709104"
---
# Unregister-AzProviderPreviewFeature

## SYNOPSIS
Menghapus pendaftaran fitur dari akun Anda.

## SYNTAX

```
Unregister-AzProviderPreviewFeature -Name <String> -ProviderNamespace <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Unregister-AzProviderPreviewFeature** menghapus pendaftaran fitur dari akun Anda.

## EXAMPLES

### Contoh 1: Menghapus pendaftaran fitur
```
PS C:\>Unregister-AzProviderPreviewFeature -FeatureName AllowApplicationSecurityGroups -ProviderNamespace Microsoft.Network
```

Langkah ini akan menghapus fitur AllowApplicationSecurityGroups untuk Microsoft.Network dari akun Anda.

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
Nama fitur.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FeatureName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Jika ditentukan, cmdlet akan mengembalikan true saat registrasi fitur dihapus.

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

### -ProviderNamespace
Ruang nama penyedia sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

## RELATED LINKS

[Get-AzProviderPreviewFeature](./Get-AzProviderPreviewFeature.md)

[Register-AzProviderPreviewFeature](./Register-AzProviderPreviewFeature.md)