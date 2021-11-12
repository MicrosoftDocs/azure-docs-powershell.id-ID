---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-azdeploymentoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Get-AzDeploymentOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Resources/Resources/help/Get-AzDeploymentOperation.md
ms.openlocfilehash: e1da6e54eac3e72217e83e498966bdfa80740762
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406462"
---
# Get-AzDeploymentOperation

## SYNOPSIS
Operasi Dapatkan penggunaan

## SINTAKS

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

## DESKRIPSI
Cmdlet **Get-AzDeploymentOperation** mencantumkan semua operasi yang menjadi bagian dari penyebaran untuk membantu Anda mengidentifikasi dan memberi informasi selengkapnya tentang operasi persis yang gagal untuk penggunaan tertentu.
Konten juga dapat memperlihatkan respons dan permintaan konten untuk setiap operasi penyebaran.
Ini adalah informasi yang sama yang disediakan dalam detail penggunaan di portal.

Untuk mendapatkan permintaan dan konten respons, aktifkan pengaturan saat mengirimkan penyebaran melalui **New-AzDeployment**.
Ini bisa berpotensi membuat log dan mengekspos rahasia seperti kata sandi yang digunakan dalam properti sumber daya atau operasi **ListKeys** yang kemudian dikembalikan saat Anda mengambil operasi penyebaran.
Untuk informasi selengkapnya tentang pengaturan ini dan cara mengaktifkannya, lihat cara New-AzDeployment Dan Debug penyebaran templat ARM

## CONTOH

### Contoh 1: Mendapatkan operasi penyebaran dengan nama penyebaran
```powershell
PS C:\>Get-AzDeploymentOperation -DeploymentName test
```

Mendapatkan operasi penyebaran dengan nama "uji" pada lingkup langganan saat ini.

### Contoh 2: Mendapatkan penyebaran dan mendapatkan operasi penyebaran
```powershell
PS C:\>Get-AzDeployment -Name "test" | Get-AzDeploymentOperation
```

Perintah ini mendapatkan "uji" penyebaran di lingkup langganan saat ini dan mendapatkan operasi penyebarannya.

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
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeployment

## OUTPUT

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSDeploymentOperation

## CATATAN

## LINK TERKAIT
