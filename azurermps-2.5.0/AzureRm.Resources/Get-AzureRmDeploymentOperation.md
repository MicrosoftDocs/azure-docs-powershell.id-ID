---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermdeploymentoperation
schema: 2.0.0
ms.openlocfilehash: 2bb5c3823d974dad53045d9283099befd4d60855
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142145393"
---
# Get-AzureRmDeploymentOperation

## SYNOPSIS
Dapatkan operasi penyebaran

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### GetByDeploymentName (Default)
```
Get-AzureRmDeploymentOperation -DeploymentName <String> [-OperationId <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByDeploymentObject
```
Get-AzureRmDeploymentOperation -DeploymentObject <PSDeployment> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDeploymentOperation** mencantumkan semua operasi yang merupakan bagian dari penyebaran untuk membantu Anda mengidentifikasi dan memberikan informasi selengkapnya tentang operasi yang persis gagal untuk penyebaran tertentu.
Ini juga dapat memperlihatkan respons dan konten permintaan untuk setiap operasi penyebaran.
Ini adalah informasi yang sama yang disediakan dalam detail penyebaran di portal.

Untuk mendapatkan permintaan dan konten respons, aktifkan pengaturan saat mengirimkan penyebaran melalui **New-AzureRmDeployment**.
Ini dapat berpotensi membuat log dan mengekspos rahasia seperti kata sandi yang digunakan dalam properti sumber daya atau operasi **listKeys** yang kemudian dikembalikan saat Anda mengambil operasi penyebaran.
Untuk informasi selengkapnya tentang pengaturan ini dan cara mengaktifkannya, lihat penyebaran templat New-AzureRmDeployment dan Debugging ARM

## EXAMPLES

### Dapatkan operasi penyebaran dengan nama penyebaran
```
PS C:\>Get-AzureRmDeploymentOperation -DeploymentName test
```

Mendapatkan operasi penyebaran dengan nama "uji" pada lingkup langganan saat ini.

### Dapatkan penyebaran dan dapatkan operasi penyebarannya
```
PS C:\>Get-AzureRmDeployment -Name "test" | Get-AzureRmDeploymentOperation
```

Perintah ini mendapatkan "uji" penyebaran pada lingkup langganan saat ini dan mendapatkan operasi penyebarannya.

## PARAMETERS

### -ApiVersion
Ketika diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
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

### -DeploymentName
Nama penyebaran.

```yaml
Type: String
Parameter Sets: GetByDeploymentName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeploymentObject
Objek penyebaran.

```yaml
Type: PSDeployment
Parameter Sets: GetByDeploymentObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OperationId
Id operasi penyebaran.

```yaml
Type: String
Parameter Sets: GetByDeploymentName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pra
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API prarilis saat menentukan versi mana yang akan digunakan secara otomatis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Nullable'1[[System.Guid, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeploymentOperation

## CATATAN

## RELATED LINKS
