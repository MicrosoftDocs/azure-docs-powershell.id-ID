---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 6E2F0D5E-E683-46F3-B48B-55C4864F3308
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmResourceGroupDeployment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/New-AzureRmResourceGroupDeployment.md
ms.openlocfilehash: 9512a8ae8e6bbd54704212539ad0650797cf4604
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426093"
---
# New-AzureRmResourceGroupDeployment

## SYNOPSIS
Menambahkan penyebaran Azure ke grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Penggunaan melalui file templat tanpa parameter (Default)
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateFile <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Penggunaan melalui file templat dan objek parameter templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterObject <Hashtable> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui objek parameter templat dan uri templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterObject <Hashtable> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui file templat dan file parameter templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterFile <String> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui file parameter templat dan uri templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterFile <String> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui uri parameter templat file templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterUri <String> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui uri templat dan uri parameter templat
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterUri <String> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Penggunaan melalui uri templat tanpa parameter
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateUri <String> [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmResourceGroupDeployment** menambahkan penyebaran ke grup sumber daya yang sudah ada.
Ini termasuk sumber daya yang diperlukan penyebaran.

Sumber daya Azure adalah entitas Azure yang dikelola pengguna, seperti server database, database, situs web, mesin virtual, atau Storage anda.
Grup sumber daya Azure adalah kumpulan sumber daya Azure yang digunakan sebagai unit, seperti situs web, server database, dan database yang diperlukan untuk situs web keuangan.
Penyebaran grup sumber daya menggunakan templat untuk menambahkan sumber daya ke grup sumber daya dan menerbitkannya sehingga tersedia di Azure.
Untuk menambahkan sumber daya ke grup sumber daya tanpa menggunakan templat, gunakan cmdlet New-AzureRmResource cmdlet.

Untuk menambahkan penyebaran grup sumber daya, tentukan nama grup sumber daya yang ada dan templat grup sumber daya.
Templat grup sumber daya adalah string JSON yang mewakili grup sumber daya untuk layanan berbasis awan yang kompleks, seperti portal web.
Templat ini menyertakan tempat penampung parameter untuk sumber daya yang diperlukan dan nilai properti yang dapat dikonfigurasi, seperti nama dan ukuran.
Anda dapat menemukan banyak templat dalam galeri templat Azure atau membuat sendiri templat Anda.
Anda bisa menggunakan cmdlet **Get-AzureRmResourceGroupGalleryTemplate** untuk menemukan templat di galeri.

Untuk menggunakan templat kustom guna membuat grup sumber daya, tentukan parameter *TemplateFile* atau parameter *TemplateUri.*
Setiap templat memiliki parameter untuk properti yang dapat dikonfigurasi.
Untuk menentukan nilai bagi parameter templat, tentukan parameter *TemplateParameterFile* atau *parameter TemplateParameterObject.*
Alternatifnya, Anda bisa menggunakan parameter templat yang ditambahkan secara dinamis ke perintah saat Anda menentukan templat.
Untuk menggunakan parameter dinamis, ketikkan parameter dinamis di prompt perintah, atau ketik tanda minus (-) untuk menunjukkan parameter dan gunakan tombol Tab untuk melihat parameter yang tersedia.
Nilai parameter templat yang Anda masukkan di prompt perintah lebih diprioritaskan ke prioritas dalam objek parameter templat atau file.

## EXAMPLES

### Contoh 1: Menggunakan templat kustom dan file parameter untuk membuat penyebaran
```
PS C:\>New-AzureRmResourceGroupDeployment -ResourceGroupName "ContosoEngineering" -TemplateFile "D:\Azure\Templates\EngineeringSite.json" -TemplateParameterFile "D:\Azure\Templates\EngSiteParms.json" -TemplateVersion "2.1"
```

Perintah ini membuat penyebaran baru dengan menggunakan templat kustom dan file templat di disk.
Perintah menggunakan parameter *TemplateFile* untuk menentukan templat dan parameter *TemplateParameterFile* untuk menentukan file yang berisi parameter dan nilai parameter.
Templat ini menggunakan parameter *TemplateVersion* untuk menentukan versi template.

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

### -DeploymentDelogiLogLevel
Menentukan tingkat log debug.
Nilai yang dapat diterima untuk parameter ini adalah:

- RequestContent 
- ResponseContent 
- Semua 
- Tidak ada

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

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -Mode
Menentukan mode penyebaran. Nilai yang dapat diterima untuk parameter ini adalah:

- Selesai 
- Penambahan

```yaml
Type: Microsoft.Azure.Management.ResourceManager.Models.DeploymentMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Incremental
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyebaran grup sumber daya untuk dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DeploymentName

Required: False
Position: Named
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
Menentukan nama grup sumber daya untuk digunakan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateFile
Menentukan jalur lengkap file templat JSON.
Ini bisa merupakan templat kustom atau templat galeri yang disimpan sebagai file JSON, seperti yang dibuat dengan menggunakan cmdlet **Save-AzureRmResourceGroupGalleryTemplate.**

```yaml
Type: System.String
Parameter Sets: Deployment via template file without parameters, Deployment via template file and template parameters object, Deployment via template file and template parameters file, Deployment via template file template parameters uri
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterFile
Menentukan jalur lengkap file JSON yang berisi nama dan nilai parameter templat.
Jika templat memiliki parameter, Anda harus menentukan nilai parameter dengan parameter *TemplateParameterFile* atau parameter *TemplateParameterObject.*
Parameter templat ditambahkan secara dinamis ke perintah ketika Anda menentukan templat.

Untuk menggunakan parameter dinamis, ketik tanda minus (-) untuk menunjukkan nama parameter, lalu gunakan tombol Tab untuk melihat parameter yang tersedia.

```yaml
Type: System.String
Parameter Sets: Deployment via template file and template parameters file, Deployment via template uri and template parameters file
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterObject
Menentukan tabel hash nama dan nilai parameter templat.
Untuk bantuan terkait tabel hash di Windows PowerShell, ketikkan `Get-Help about_Hash_Tables` .
Jika templat memiliki parameter, Anda harus menentukan nilai parameter.
Parameter templat ditambahkan secara dinamis ke perintah ketika Anda menentukan templat.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Deployment via template file and template parameters object, Deployment via template uri and template parameters object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterUri
Menentukan URI dari file parameter templat.

```yaml
Type: System.String
Parameter Sets: Deployment via template file template parameters uri, Deployment via template uri and template parameters uri
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateUri
Menentukan URI dari file templat JSON.
File ini bisa merupakan templat kustom atau templat galeri yang disimpan sebagai file JSON, seperti dengan menggunakan **Save-AzureRmResourceGroupGalleryTemplate**.

```yaml
Type: System.String
Parameter Sets: Deployment via template uri and template parameters object, Deployment via template uri and template parameters file, Deployment via template uri and template parameters uri, Deployment via template uri without parameters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Models.PSResourceGroupDeployment

## CATATAN

## RELATED LINKS

[Get-AzureRmResourceGroupDeployment](./Get-AzureRmResourceGroupDeployment.md)

[New-AzureRmResource](./New-AzureRmResource.md)

[New-AzureRmResourceGroup](./New-AzureRmResourceGroup.md)

[Remove-AzureRmResourceGroupDeployment](./Remove-AzureRmResourceGroupDeployment.md)

[Stop-AzureRmResourceGroupDeployment](./Stop-AzureRmResourceGroupDeployment.md)

[Test-AzureRmResourceGroupDeployment](./Test-AzureRmResourceGroupDeployment.md)


