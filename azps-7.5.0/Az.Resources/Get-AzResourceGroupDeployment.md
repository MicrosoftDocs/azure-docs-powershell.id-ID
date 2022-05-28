---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 20CB842B-F7A9-4052-85D9-0DF9586D5FEA
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azresourcegroupdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
ms.openlocfilehash: a19f5f54fd933d8d4dc798af9b7387679180a07b
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145642670"
---
# Get-AzResourceGroupDeployment

## SYNOPSIS
Mendapatkan penyebaran dalam grup sumber daya.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azresourcegroupdeployment) untuk informasi terbaru.

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
Cmdlet **Get-AzResourceGroupDeployment** mendapatkan penyebaran dalam grup sumber daya Azure.
Tentukan parameter *Nama* atau *Id* untuk memfilter hasilnya.
Secara default, **Get-AzResourceGroupDeployment** mendapatkan semua penyebaran untuk grup sumber daya tertentu.
Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web.
Grup sumber daya Azure adalah kumpulan sumber daya Azure yang disebarkan sebagai unit.
Penyebaran adalah operasi yang membuat sumber daya dalam grup sumber daya tersedia untuk digunakan.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat cmdlet New-AzResourceGroup.
Anda dapat menggunakan cmdlet ini untuk pelacakan.
Untuk penelusuran kesalahan, gunakan cmdlet ini dengan cmdlet Get-AzLog.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran untuk grup sumber daya
```powershell
Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG"
```

Perintah ini mendapatkan semua penyebaran untuk grup sumber daya ContosoLabsRG.
Output menunjukkan penyebaran untuk blog WordPress yang menggunakan templat galeri.

### Contoh 2: Mendapatkan penyebaran berdasarkan nama
```powershell
Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG" -Name "DeployWebsite01"
```

Perintah ini mendapatkan penyebaran DeployWebsite01 dari grup sumber daya ContosoLabsRG.
Anda dapat menetapkan nama ke penyebaran saat membuatnya dengan menggunakan cmdlet **New-AzResourceGroup** atau **New-AzResourceGroupDeployment** .
Jika Anda tidak menetapkan nama, cmdlet menyediakan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

### Contoh 3: Mendapatkan penyebaran semua grup sumber daya
```powershell
Get-AzResourceGroup | Get-AzResourceGroupDeployment | Format-Table ResourceGroupName, DeploymentName, ProvisioningState
```

Perintah ini mendapatkan semua grup sumber daya dalam langganan Anda dengan menggunakan cmdlet Get-AzResourceGroup.
Perintah meneruskan grup sumber daya ke cmdlet saat ini dengan menggunakan operator alur.
Cmdlet saat ini mendapatkan semua penyebaran semua grup sumber daya dalam langganan, dan meneruskan hasilnya ke cmdlet Format-Table untuk menampilkan nilai properti **ResourceGroupName**, **DeploymentName**, dan **ProvisioningState** mereka.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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
Menentukan ID penyebaran grup sumber daya yang akan didapatkan.

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

### -Name
Menentukan nama penyebaran yang akan didapatkan.
Karakter kartubebas tidak diizinkan.

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
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Karakter kartubebas tidak diizinkan.
Parameter ini diperlukan dan Anda hanya dapat menentukan satu grup sumber daya di setiap perintah.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceGroupDeployment

## NOTES

## RELATED LINKS

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[Baru-AzResourceGroup](./New-AzResourceGroup.md)

[New-AzResourceGroupDeployment](./New-AzResourceGroupDeployment.md)

[Remove-AzResourceGroupDeployment](./Remove-AzResourceGroupDeployment.md)

[Stop-AzResourceGroupDeployment](./Stop-AzResourceGroupDeployment.md)

[Test-AzResourceGroupDeployment](./Test-AzResourceGroupDeployment.md)


