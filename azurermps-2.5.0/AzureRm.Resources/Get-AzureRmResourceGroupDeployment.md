---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 20CB842B-F7A9-4052-85D9-0DF9586D5FEA
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermresourcegroupdeployment
schema: 2.0.0
ms.openlocfilehash: 9da5ee691b440ee24933d658dec3c85b1a7c8ced
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421514"
---
# Get-AzureRmResourceGroupDeployment

## SYNOPSIS
Mendapatkan penyebaran di grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByResourceGroupDeploymentName (Default)
```
Get-AzureRmResourceGroupDeployment [-ResourceGroupName] <String> [[-Name] <String>] [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroupDeploymentId
```
Get-AzureRmResourceGroupDeployment -Id <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmResourceGroupDeployment** mendapatkan penyebaran di grup sumber daya Azure.
Tentukan parameter *Nama* *atau Id* untuk memfilter hasilnya.
Secara default, **Get-AzureRmResourceGroupDeployment** mendapatkan semua penyebaran untuk grup sumber daya yang ditentukan.
Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web.
Grup sumber daya Azure adalah kumpulan sumber daya Azure yang digunakan sebagai unit.
Penyebaran adalah operasi yang membuat sumber daya di grup sumber daya tersedia untuk digunakan.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat New-AzureRmResourceGroup cmdlet.
Anda dapat menggunakan cmdlet ini untuk pelacakan.
Untuk penelusuran kesalahan, gunakan cmdlet ini dengan Get-AzureRmLog cmdlet.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran untuk grup sumber daya
```
PS C:\>Get-AzureRmResourceGroupDeployment -ResourceGroupName "ContosoLabsRG"
```

Perintah ini mendapatkan semua penyebaran untuk grup sumber daya ContosoLabsRG.
Output memperlihatkan penggunaan untuk blog WordPress yang menggunakan templat galeri.

### Contoh 2: Mendapatkan penyebaran menurut nama
```
PS C:\>Get-AzureRmResourceGroupDeployment -ResourceGroupName "ContosoLabsRG" -Name "DeployWebsite01"
```

Perintah ini menerapkan penyebaran DeployWebsite01 dari grup sumber daya ContosoLabsRG.
Anda dapat menetapkan nama untuk penyebaran ketika membuat penyebaran menggunakan cmdlet **New-AzureRmResourceGroup** atau **New-AzureRmResourceGroupDeployment.**
Jika Anda tidak memberi nama, cmdlet memberikan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

### Contoh 3: Mendapatkan penyebaran semua grup sumber daya
```
PS C:\>Get-AzureRmResourceGroup | Get-AzureRmResourceGroupDeployment | Format-Table ResourceGroupName, DeploymentName, ProvisioningState
```

Perintah ini mendapatkan semua grup sumber daya dalam langganan Anda menggunakan cmdlet Get-AzureRmResourceGroup cmdlet.
Perintah itu meneruskan grup sumber daya ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini mendapatkan semua penyebaran dari semua grup sumber daya dalam langganan, dan memberikan hasil ke cmdlet Format-Table untuk menampilkan nilai properti **ResourceGroupName,** **DeploymentName,** **dan ProvisioningState.**

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda bisa menentukan versi yang berbeda dari versi default.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Mengindikasikan bahwa cmdlet ini mempertimbangkan versi API prari perilisan bila secara otomatis menentukan versi mana yang akan digunakan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models. PSResourceGroupDeployment

## CATATAN

## RELATED LINKS

[Get-AzureRmResourceGroup](./Get-AzureRmResourceGroup.md)

[New-AzureRmResourceGroup](./New-AzureRmResourceGroup.md)

[New-AzureRmResourceGroupDeployment](./New-AzureRmResourceGroupDeployment.md)

[Remove-AzureRmResourceGroupDeployment](./Remove-AzureRmResourceGroupDeployment.md)

[Stop-AzureRmResourceGroupDeployment](./Stop-AzureRmResourceGroupDeployment.md)

[Test-AzureRmResourceGroupDeployment](./Test-AzureRmResourceGroupDeployment.md)


