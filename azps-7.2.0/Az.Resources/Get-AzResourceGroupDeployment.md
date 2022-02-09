---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 20CB842B-F7A9-4052-85D9-0DF9586D5FEA
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azresourcegroupdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
ms.openlocfilehash: f39194e8297209359322edaa7558aa613b473742
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138303308"
---
# Get-AzResourceGroupDeployment

## SYNOPSIS
Mendapatkan penyebaran di grup sumber daya.

## SYNTAX

### GetByResourceGroupDeploymentName (Default)
```
Get-AzResourceGroupDeployment [-ResourceGroupName] <String> [[-Name] <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroupDeploymentId
```
Get-AzResourceGroupDeployment -Id <String> [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzResourceGroupDeployment** mendapatkan penyebaran di grup sumber daya Azure.
Tentukan parameter *Nama* *atau Id* untuk memfilter hasilnya.
Secara default, **Get-AzResourceGroupDeployment** mendapatkan semua penyebaran untuk grup sumber daya yang ditentukan.
Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web.
Grup sumber daya Azure adalah kumpulan sumber daya Azure yang digunakan sebagai unit.
Penyebaran adalah operasi yang membuat sumber daya di grup sumber daya tersedia untuk digunakan.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat New-AzResourceGroup cmdlet.
Anda dapat menggunakan cmdlet ini untuk pelacakan.
Untuk penelusuran kesalahan, gunakan cmdlet ini dengan cmdlet Get-AzLog cmdlet.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran untuk grup sumber daya
```
PS C:\>Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG"
```

Perintah ini mendapatkan semua penyebaran untuk grup sumber daya ContosoLabsRG.
Output memperlihatkan penggunaan untuk blog WordPress yang menggunakan templat galeri.

### Contoh 2: Mendapatkan penyebaran menurut nama
```
PS C:\>Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG" -Name "DeployWebsite01"
```

Perintah ini menerapkan penyebaran DeployWebsite01 dari grup sumber daya ContosoLabsRG.
Anda bisa menetapkan nama untuk penggunaan saat Anda membuatnya dengan menggunakan cmdlet **New-AzResourceGroup** atau **New-AzResourceGroupDeployment** .
Jika Anda tidak memberi nama, cmdlet memberikan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

### Contoh 3: Mendapatkan penyebaran semua grup sumber daya
```
PS C:\>Get-AzResourceGroup | Get-AzResourceGroupDeployment | Format-Table ResourceGroupName, DeploymentName, ProvisioningState
```

Perintah ini mendapatkan semua grup sumber daya dalam langganan Anda menggunakan cmdlet Get-AzResourceGroup cmdlet.
Perintah itu meneruskan grup sumber daya ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini mendapatkan semua penyebaran dari semua grup sumber daya dalam langganan, dan memberikan hasil ke cmdlet Format-Table untuk menampilkan nilai properti **ResourceGroupName**, **DeploymentName**, **dan ProvisioningState** .

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Id
Menentukan ID penggunaan grup sumber daya untuk mendapatkan.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroupDeploymentId
Aliases: DeploymentId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyebaran untuk mendapatkan.
Karakter wildcard tidak diizinkan.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroupDeploymentName
Aliases: DeploymentName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pra
Cmdlet ini mempertimbangkan versi API prari release ketika cmdlet menentukan versi mana yang akan digunakan secara otomatis.

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
Menentukan nama grup sumber daya.
Cmdlet mendapatkan penyebaran untuk grup sumber daya yang ditentukan parameter ini.
Karakter wildcard tidak diizinkan.
Parameter ini diperlukan dan Anda hanya dapat menentukan satu grup sumber daya dalam setiap perintah.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroupDeploymentName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceGroupDeployment

## CATATAN

## RELATED LINKS

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[New-AzResourceGroup](./New-AzResourceGroup.md)

[New-AzResourceGroupDeployment](./New-AzResourceGroupDeployment.md)

[Remove-AzResourceGroupDeployment](./Remove-AzResourceGroupDeployment.md)

[Stop-AzResourceGroupDeployment](./Stop-AzResourceGroupDeployment.md)

[Test-AzResourceGroupDeployment](./Test-AzResourceGroupDeployment.md)


