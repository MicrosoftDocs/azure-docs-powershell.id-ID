---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 20CB842B-F7A9-4052-85D9-0DF9586D5FEA
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-Azresourcegroupdeployment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzResourceGroupDeployment.md
ms.openlocfilehash: 2703a5f32142ddd8d5754c89924360564b45d0f9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142781002"
---
# Get-AzResourceGroupDeployment

## SYNOPSIS
Mendapatkan penyebaran dalam grup sumber daya.

## SYNTAX

### GetByResourceGroupDeploymentName (Default)
```
Get-AzResourceGroupDeployment [-ResourceGroupName] <String> [[-Name] <String>] [-ApiVersion <String>]
 [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroupDeploymentId
```
Get-AzResourceGroupDeployment -Id <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzResourceGroupDeployment** mendapatkan penyebaran dalam grup sumber daya Azure.
Tentukan parameter *Nama* atau *Id* untuk memfilter hasil.
Secara default, **Get-AzResourceGroupDeployment** mendapatkan semua penyebaran untuk grup sumber daya tertentu.
Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, atau situs web.
Grup sumber daya Azure adalah kumpulan sumber daya Azure yang disebarkan sebagai unit.
Penyebaran adalah operasi yang membuat sumber daya dalam grup sumber daya tersedia untuk digunakan.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat cmdlet New-AzResourceGroup.
Anda dapat menggunakan cmdlet ini untuk pelacakan.
Untuk proses debug, gunakan cmdlet ini dengan cmdlet Get-AzLog.

## EXAMPLES

### Contoh 1: Dapatkan semua penyebaran untuk grup sumber daya
```
PS C:\>Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG"
```

Perintah ini mendapatkan semua penyebaran untuk grup sumber daya ContosoLabsRG.
Output memperlihatkan penyebaran untuk blog WordPress yang menggunakan templat galeri.

### Contoh 2: Mendapatkan penyebaran berdasarkan nama
```
PS C:\>Get-AzResourceGroupDeployment -ResourceGroupName "ContosoLabsRG" -Name "DeployWebsite01"
```

Perintah ini mendapatkan penyebaran DeployWebsite01 dari grup sumber daya ContosoLabsRG.
Anda dapat menetapkan nama untuk penyebaran saat membuatnya menggunakan cmdlet **New-AzResourceGroup** atau **New-AzResourceGroupDeployment** .
Jika Anda tidak menetapkan nama, cmdlet menyediakan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

### Contoh 3: Dapatkan penyebaran semua grup sumber daya
```
PS C:\>Get-AzResourceGroup | Get-AzResourceGroupDeployment | Format-Table ResourceGroupName, DeploymentName, ProvisioningState
```

Perintah ini mendapatkan semua grup sumber daya dalam langganan Anda menggunakan cmdlet Get-AzResourceGroup.
Perintah melewati grup sumber daya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini mendapatkan semua penyebaran semua grup sumber daya dalam langganan, dan mengirimkan hasil ke cmdlet Format-Table untuk menampilkan nilai properti **ResourceGroupName**, **DeploymentName**, dan **ProvisioningState** mereka.

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda dapat menentukan versi yang berbeda dari versi default.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID penyebaran grup sumber daya untuk didapatkan.

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
Menentukan nama penyebaran yang akan didapatkan.
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
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API prarilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models. PSResourceGroupDeployment

## NOTES

## RELATED LINKS

[Get-AzResourceGroup](./Get-AzResourceGroup.md)

[AzResourceGroup baru](./New-AzResourceGroup.md)

[New-AzResourceGroupDeployment](./New-AzResourceGroupDeployment.md)

[Remove-AzResourceGroupDeployment](./Remove-AzResourceGroupDeployment.md)

[Stop-AzResourceGroupDeployment](./Stop-AzResourceGroupDeployment.md)

[Test-AzResourceGroupDeployment](./Test-AzResourceGroupDeployment.md)


