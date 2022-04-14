---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 9F29DFCB-A02B-45A5-99B9-C054BF4FCA6C
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azresourcegroupdeploymentoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeploymentOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeploymentOperation.md
ms.openlocfilehash: 11369935670a04df286a227aaee7898676a009d2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142042715"
---
# Get-AzResourceGroupDeploymentOperation

## SYNOPSIS
Mendapatkan operasi penyebaran grup sumber daya

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azresourcegroupdeploymentoperation) untuk informasi terbaru.

## SYNTAX

```
Get-AzResourceGroupDeploymentOperation -DeploymentName <String> [-SubscriptionId <Guid>]
 -ResourceGroupName <String> [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzResourceGroupDeploymentOperation** mencantumkan semua operasi yang merupakan bagian dari penyebaran untuk membantu Anda mengidentifikasi dan memberikan informasi selengkapnya tentang operasi persis yang gagal untuk penyebaran tertentu.
Ini juga dapat memperlihatkan respons dan konten permintaan untuk setiap operasi penyebaran.
Ini adalah informasi yang sama yang disediakan dalam detail penyebaran di portal.
Untuk mendapatkan permintaan dan konten respons, aktifkan pengaturan saat mengirimkan penyebaran melalui **New-AzResourceGroupDeployment**.
Ini dapat berpotensi membuat log dan mengekspos rahasia seperti kata sandi yang digunakan dalam properti sumber daya atau operasi **listKeys** yang kemudian dikembalikan saat Anda mengambil operasi penyebaran.
Untuk informasi selengkapnya tentang pengaturan ini dan cara mengaktifkannya, lihat penyebaran templat New-AzResourceGroupDeployment dan Debugging ARM

## EXAMPLES

### Contoh 1: Get1
```powershell
PS C:\>Get-AzResourceGroupDeploymentOperation -DeploymentName test -ResourceGroupName test
```

Mendapatkan operasi penyebaran dengan nama "uji" di bawah "uji" grup sumber daya

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

### -DeploymentName
Nama penyebaran.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API prarilis saat menentukan versi mana yang akan digunakan secara otomatis.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Langganan yang akan digunakan.

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Nullable'1[[System.Guid, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeploymentOperation

## CATATAN

## RELATED LINKS
