---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 5B17A241-BF36-48A6-BC29-4C32C08F5F94
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermresourcegroup
schema: 2.0.0
ms.openlocfilehash: ede228aef26cf7e4729acf3a6acc0faae3902f2c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141970777"
---
# Get-AzureRmResourceGroup

## SYNOPSIS
Mendapatkan grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByResourceGroupName (Default)
```
Get-AzureRmResourceGroup [-Name <String>] [-Location <String>] [-Tag <Hashtable>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroupId
```
Get-AzureRmResourceGroup [-Location <String>] [-Id <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmResourceGroup** mendapatkan grup sumber daya Azure dalam langganan saat ini.
Anda bisa mendapatkan semua grup sumber daya, atau menentukan grup sumber daya menurut nama atau menurut properti lainnya.
Secara default, cmdlet ini mendapatkan semua grup sumber daya dalam langganan saat ini.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat cmdlet New-AzureRmResourceGroup.

## EXAMPLES

### Contoh 1: Dapatkan grup sumber daya menurut nama
```
PS C:\>Get-AzureRmResourceGroup -Name "EngineerBlog"
```

Perintah ini mendapatkan grup sumber daya Azure di langganan Anda bernama EngineerBlog.

### Contoh 2: Dapatkan semua tag grup sumber daya
```
PS C:\>(Get-AzureRmResourceGroup -Name "ContosoRG").Tags
```

Perintah ini mendapatkan grup sumber daya bernama ContosoRG, dan menampilkan tag yang terkait dengan grup tersebut.

### Contoh 3: Memperlihatkan grup Sumber Daya berdasarkan lokasi
```
PS C:\> Get-AzureRmResourceGroup |
  Sort Location,ResourceGroupName |
  Format-Table -GroupBy Location ResourceGroupName,ProvisioningState,Tags
```

### Contoh 4: Memperlihatkan nama semua grup Sumber Daya di lokasi tertentu
```
PS C:\> Get-AzureRmResourceGroup -Location westus2 |
   Sort ResourceGroupName | 
   Format-Wide ResourceGroupName -Column 4
```

### Contoh 5: Memperlihatkan grup Sumber Daya yang namanya dimulai dengan WebServer
```
PS C:\> Get-AzureRmResourceGroup | Where ResourceGroupName -like WebServer*
```

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
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID grup sumber daya yang akan didapatkan.
Karakter wildcard tidak diizinkan.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroupId
Aliases: ResourceGroupId, ResourceId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi grup sumber daya untuk didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama grup sumber daya untuk didapatkan. Parameter ini mendukung wildcard di awal dan/atau akhir string.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroupName
Aliases: ResourceGroupName

Required: False
Position: Named
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

### -Tag
Tag hashtable untuk memfilter grup sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: GetByResourceGroupName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.PSResourceGroup

## CATATAN

## RELATED LINKS

[AzureRmResourceGroup baru](./New-AzureRmResourceGroup.md)

[Hapus-AzureRmResourceGroup](./Remove-AzureRmResourceGroup.md)

[Set-AzureRmResourceGroup](./Set-AzureRmResourceGroup.md)


