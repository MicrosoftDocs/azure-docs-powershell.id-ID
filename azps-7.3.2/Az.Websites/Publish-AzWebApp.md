---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/publish-azwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Publish-AzWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Publish-AzWebApp.md
ms.openlocfilehash: 05d5e4f329cb08e03e376141d9e919e707fa4b49
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141848642"
---
# Publish-AzWebApp

## SYNOPSIS
Menyebarkan Azure Web App dari file ZIP, JAR, atau WAR menggunakan zipdeploy. 

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/publish-azwebapp) untuk informasi terbaru.

## SYNTAX

### FromResourceName
```
Publish-AzWebApp -ArchivePath <String> [-AsJob] [-ResourceGroupName] <String> [-Name] <String>
 [[-Slot] <String>]  [-Force] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### FromWebApp
```
Publish-AzWebApp -ArchivePath <String> [-AsJob] [-WebApp] <PSSite> [-Force] [-DefaultProfile <IAzureContextContainer>] 
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Publish-AzWebApp** mengunggah konten ke Azure Web App yang sudah ada. Konten harus dimas dalam file ZIP jika menggunakan tumpukan seperti .NET, Python, atau Node, atau file WAR atau JAR jika menggunakan Java. Konten harus dibuat sebelumnya dan siap dijalankan tanpa langkah build tambahan selama penyebaran. Cmdlet ini menggunakan fitur zipdeploy dan wardeploy Kudu untuk menyebarkan konten. Lihat wiki Kudu untuk detail tentang cara kerja zipdeploy dan wardeploy, dan cara mengemas aplikasi web untuk penggunaan dengan benar. https://aka.ms/kuduzipdeploy dan https://aka.ms/kuduwardeploy berisi detail bermanfaat tentang zipdeploy dan wardeploy.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Publish-AzWebApp -ResourceGroupName Default-Web-WestUS -Name MyApp -ArchivePath C:\project\app.zip
```

Mengunggah konten app.zip ke aplikasi web bernama MyApp milik grup sumber daya Default-Web-WestUS.

### Contoh 2
```powershell
PS C:\> Publish-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp -Slot Staging -ArchivePath C:\project\javaproject.war
```

Mengunggah konten javaproject.war ke slot Staging aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG.

### Contoh 3
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> Publish-AzWebApp -WebApp $app -ArchivePath C:\project\app.zip -AsJob
```

Mengunggah konten app.zip ke aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG. Cmdlet akan dijalankan dalam pekerjaan latar belakang.

### Contoh 4
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> $app | Publish-AzWebApp -ArchivePath C:\project\java_app.jar
```
### Contoh 5
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> Publish-AzWebApp -WebApp $app -ArchivePath C:\project\app.zip -Force
```

Mengunggah konten java_app.jar ke aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG. Jika -Force tidak ditentukan, konfirmasi akan diminta sebelum konten disebarkan.

### Contoh 6
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> Publish-AzWebApp -WebApp $app -ArchivePath C:\project\app.zip -Timeout 300000 -Force
```

Mengunggah konten java_app.jar ke aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG. Pengguna dapat Mengatur rentang waktu dalam Milidetik untuk menunggu sebelum waktu permintaan habis. Jika -Force tidak ditentukan, konfirmasi akan diminta sebelum konten disebarkan.

## PARAMETERS

### -ArchivePath
Jalur file arsip. ZIP, WAR, dan JAR didukung.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -Paksa
Opsi Hapus Secara Paksa

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

### -Nama
Nama aplikasi web.

```yaml
Type: System.String
Parameter Sets: FromResourceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: FromResourceName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Nama slot aplikasi web.

```yaml
Type: System.String
Parameter Sets: FromResourceName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Waktu habis
Mengatur rentang waktu dalam Milidetik untuk menunggu sebelum waktu permintaan habis.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Objek aplikasi web

```yaml
Type: Microsoft.Azure.Commands.WebApps.Models.PSSite
Parameter Sets: FromWebApp
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Situs Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### Situs Microsoft.Azure.Commands.WebApps.Models.PSSite

## CATATAN

## RELATED LINKS
