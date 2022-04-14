---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 5B17A241-BF36-48A6-BC29-4C32C08F5F94
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azresourcegroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzResourceGroup.md
ms.openlocfilehash: af224a39b1475ffb08f698f8c29d311ad955f315
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142224595"
---
# Get-AzResourceGroup

## SYNOPSIS
Mendapatkan grup sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azresourcegroup) untuk informasi terbaru.

## SYNTAX

### GetByResourceGroupName (Default)
```
Get-AzResourceGroup [[-Name] <String>] [[-Location] <String>] [-Tag <Hashtable>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroupId
```
Get-AzResourceGroup [[-Location] <String>] [-Id <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzResourceGroup** mendapatkan grup sumber daya Azure dalam langganan saat ini.
Anda bisa mendapatkan semua grup sumber daya, atau menentukan grup sumber daya menurut nama atau menurut properti lainnya.
Secara default, cmdlet ini mendapatkan semua grup sumber daya dalam langganan saat ini.
Untuk informasi selengkapnya tentang sumber daya Azure dan grup sumber daya Azure, lihat cmdlet New-AzResourceGroup.

## EXAMPLES

### Contoh 1: Dapatkan grup sumber daya menurut nama
```
PS C:\> Get-AzResourceGroup -Name "EngineerBlog"
```

Perintah ini mendapatkan grup sumber daya Azure di langganan Anda bernama EngineerBlog.

### Contoh 2: Dapatkan semua tag grup sumber daya
```
PS C:\> (Get-AzResourceGroup -Name "ContosoRG").Tags
```

Perintah ini mendapatkan grup sumber daya bernama ContosoRG, dan menampilkan tag yang terkait dengan grup tersebut.

### Contoh 3: Dapatkan grup sumber daya berdasarkan tag
```
PS C:\> Get-AzResourceGroup -Tag @{'environment'='prod'}
```

### Contoh 4: Memperlihatkan grup Sumber Daya berdasarkan lokasi
```
PS C:\> Get-AzResourceGroup |
  Sort Location,ResourceGroupName |
  Format-Table -GroupBy Location ResourceGroupName,ProvisioningState,Tags
```

### Contoh 5: Memperlihatkan nama semua grup Sumber Daya di lokasi tertentu
```
PS C:\> Get-AzResourceGroup -Location westus2 |
   Sort ResourceGroupName | 
   Format-Wide ResourceGroupName -Column 4
```

### Contoh 6: Memperlihatkan grup Sumber Daya yang namanya dimulai dengan WebServer
```
PS C:\> Get-AzResourceGroup -Name WebServer*
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
Position: 1
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceGroup

## CATATAN

## RELATED LINKS

[AzResourceGroup baru](./New-AzResourceGroup.md)

[Hapus-AzResourceGroup](./Remove-AzResourceGroup.md)

[Set-AzResourceGroup](./Set-AzResourceGroup.md)

