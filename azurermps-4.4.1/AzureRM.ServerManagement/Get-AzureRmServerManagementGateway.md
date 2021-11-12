---
external help file: Microsoft.Azure.Commands.ServerManagement.dll-Help.xml
Module Name: AzureRM.ServerManagement
ms.assetid: C579BF90-FD8B-4384-96EB-46154E308492
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServerManagement/Commands.ServerManagement/help/Get-AzureRmServerManagementGateway.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServerManagement/Commands.ServerManagement/help/Get-AzureRmServerManagementGateway.md
ms.openlocfilehash: 6b98f4266e730e1cfb60ef51046e6846f24999d7
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426425"
---
# Get-AzureRmServerManagementGateway

## SYNOPSIS
Mendapatkan satu atau lebih Gateway Manajemen Server.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### NoParams (Default)
```
Get-AzureRmServerManagementGateway [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Many-ByResourceGroup
```
Get-AzureRmServerManagementGateway [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Single-ByName
```
Get-AzureRmServerManagementGateway [-ResourceGroupName] <String> [-GatewayName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Single-ByObject
```
Get-AzureRmServerManagementGateway [-Gateway] <Gateway> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmServerManagementGateway** mendapatkan satu atau beberapa Gateway Manajemen Azure Server.

## EXAMPLES

### Contoh 1: Mendapatkan semua gateway dalam langganan
```
PS C:\>Get-AzureRmServerManagementGateway
Resource Group Location       Auto Upgrade Gateway Name
-------------- --------       ------------ ------------
groupOne       centralus      Off          mygateway
groupOne       centralus      Off          othergateway
groupTwo       centralus      On           privategateway
```

Perintah ini mendapatkan semua Gateway Manajemen Server dalam langganan.

### Contoh 2: Dapatkan gateway dalam grup sumber daya
```
PS C:\>Get-AzureRmServerManagementGateway -ResourceGroupName "Group001"
Resource Group Location       Auto Upgrade Gateway Name
-------------- --------       ------------ ------------
myGroup        centralus      Off          mygateway
```

Perintah ini mendapatkan semua Gateway Manajemen Server yang dimiliki oleh grup sumber daya bernama Group001.

### Contoh 3: Mendapatkan semua contoh gateway yang terinstal
```
PS C:\>(Get-AzureRmServerManagementGateway -ResourceGroupName "Group002" -GatewayName "Gateway01").Instances
Name             Installed              Version         Operating System
----             ---------              -------         ----------------
GATEWAYPC        4/13/2016 6:35:04 PM   1.0.1104.0      Microsoft Windows 10 Enterprise
```

Perintah ini mendapatkan semua contoh Gateway Manajemen Server bernama Gateway01 yang termasuk dalam grup sumber daya bernama Group002.

## PARAMETERS

### -Gateway
Menentukan gateway yang akan didaangkan cmdlet ini.

Cmdlet menggunakan parameter *ResourceGroupName* *dan GatewayName* melalui Gateway yang ditentukan untuk menjalankan tindakan.

Saat parameter ini ditentukan, cmdlet ini akan menyertakan status detail untuk gateway.

```yaml
Type: Microsoft.Azure.Commands.ServerManagement.Model.Gateway
Parameter Sets: Single-ByObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GatewayName
Menentukan nama Gateway Manajemen Server tempat cmdlet ini mendapatkan pintu masuk.

Saat Anda menentukan *parameter GatewayName,* cmdlet ini akan menyertakan status mendetail pada gateway.

```yaml
Type: System.String
Parameter Sets: Single-ByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang mendapatkan gateway oleh cmdlet ini.

```yaml
Type: System.String
Parameter Sets: Many-ByResourceGroup, Single-ByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Gateway
Parameter 'Gateway' menerima nilai tipe 'Gateway' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.ServerManagement.Model.Gateway

## CATATAN
* Jika cmdlet ini digunakan tanpa parameter, cmdlet ini akan mengembalikan semua gateway yang terkait dengan langganan.

## RELATED LINKS

[New-AzureRmServerManagementGateway](./New-AzureRmServerManagementGateway.md)

[Remove-AzureRmServerManagementGateway](./Remove-AzureRmServerManagementGateway.md)


