---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermdeployment
schema: 2.0.0
ms.openlocfilehash: 90c7167be3e1a53e8c20e696ca328de71a0a2b95eeb8c8f67766b4c93c986ee0
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140856242"
---
# Get-AzureRmDeployment

## SYNOPSIS
Mendapatkan penggunaan

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByDeploymentName (Default)
```
Get-AzureRmDeployment [[-Name] <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByDeploymentId
```
Get-AzureRmDeployment [-Id <String>] [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDeployment** mendapatkan penyebaran pada lingkup langganan saat ini.
Tentukan parameter *Nama* *atau Id* untuk memfilter hasilnya.
Secara default, **Get-AzureRmDeployment** mendapatkan semua penyebaran di lingkup langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan semua penyebaran di lingkup langganan
```
PS C:\>Get-AzureRmDeployment
```

Perintah ini mendapatkan semua penyebaran pada lingkup langganan saat ini.

### Contoh 2: Mendapatkan penyebaran menurut nama
```
PS C:\>Get-AzureRmDeployment -Name "DeployRoles01"
```

Perintah ini menerapkan DeployRoles01 pada lingkup langganan saat ini.
Anda dapat menetapkan nama untuk penyebaran ketika membuat penyebaran menggunakan cmdlet **New-AzureRmDeployment** .
Jika Anda tidak memberi nama, cmdlet memberikan nama default berdasarkan templat yang digunakan untuk membuat penyebaran.

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
Id sumber daya penyebaran yang sepenuhnya memenuhi syarat.
contoh: /subscriptions/{subId}/providers/Microsoft.Resources/deployments/{deploymentName}

```yaml
Type: String
Parameter Sets: GetByDeploymentId
Aliases: DeploymentId, ResourceId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama penyebaran.

```yaml
Type: String
Parameter Sets: GetByDeploymentName
Aliases: DeploymentName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## CATATAN

## RELATED LINKS
