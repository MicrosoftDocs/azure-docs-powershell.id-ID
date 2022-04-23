---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azdeploymentoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeploymentOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzDeploymentOperation.md
ms.openlocfilehash: c2fa3ff508d25bc6cc9c40a24cdbc0a8599fcd16
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143144117"
---
# Get-AzDeploymentOperation

## SYNOPSIS
Dapatkan operasi penyebaran

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azdeploymentoperation) untuk informasi terbaru.

## SYNTAX

### GetByDeploymentName (Default)
```
Get-AzDeploymentOperation -DeploymentName <String> [-OperationId <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByDeploymentObject
```
Get-AzDeploymentOperation -DeploymentObject <PSDeployment> [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDeploymentOperation** mencantumkan semua operasi yang merupakan bagian dari penyebaran untuk membantu Anda mengidentifikasi dan memberikan informasi selengkapnya tentang operasi yang persis gagal untuk penyebaran tertentu.
Ini juga dapat memperlihatkan respons dan konten permintaan untuk setiap operasi penyebaran.
Ini adalah informasi yang sama yang disediakan dalam detail penyebaran di portal.

Untuk mendapatkan permintaan dan konten respons, aktifkan pengaturan saat mengirimkan penyebaran melalui **New-AzDeployment**.
Ini dapat berpotensi membuat log dan mengekspos rahasia seperti kata sandi yang digunakan dalam properti sumber daya atau operasi **listKeys** yang kemudian dikembalikan saat Anda mengambil operasi penyebaran.
Untuk informasi selengkapnya tentang pengaturan ini dan cara mengaktifkannya, lihat penyebaran templat New-AzDeployment dan Debugging ARM

## EXAMPLES

### Contoh 1: Dapatkan operasi penyebaran yang diberi nama penyebaran
```powershell
PS C:\>Get-AzDeploymentOperation -DeploymentName test
```

Mendapatkan operasi penyebaran dengan nama "uji" pada lingkup langganan saat ini.

### Contoh 2: Dapatkan penyebaran dan dapatkan operasi penyebarannya
```powershell
PS C:\>Get-AzDeployment -Name "test" | Get-AzDeploymentOperation
```

Perintah ini mendapatkan "uji" penyebaran pada lingkup langganan saat ini dan mendapatkan operasi penyebarannya.

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
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment
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
Type: System.String
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeploymentOperation

## NOTES

## RELATED LINKS
