---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
online version: https://docs.microsoft.com/powershell/module/az.websites/publish-azwebapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Publish-AzWebApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Publish-AzWebApp.md
ms.openlocfilehash: b647bd10fe4beeb6c86b249c1429b3792ac3cf35
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136180734"
---
# Publish-AzWebApp

## SYNOPSIS
Menyebarkan Azure Web App dari file ZIP, JAR, atau WAR menggunakan zipdeploy. 

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
Cmdlet **Publish-AzWebApp** mengunggah konten ke Azure Web App yang sudah ada. Konten harus dimasukkan dalam file ZIP jika menggunakan tumpukan seperti .NET, Python, atau Node, atau file WAR atau JAR jika menggunakan Java. Konten harus sudah dibuat sebelumnya dan siap untuk dijalankan tanpa langkah build tambahan selama penyebaran. Cmdlet ini menggunakan fitur zipdeploy daneploy Kudu untuk menyebarkan konten. Lihat wiki Kudu untuk detail tentang bagaimana zipdeploy dan wikieploy berfungsi, dan cara mengemas aplikasi web dengan benar untuk penyebaran. https://aka.ms/kuduzipdeploy dan https://aka.ms/kuduwardeploy berisi detail yang bermanfaat tentang zipdeploy dan zipeploy.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Publish-AzWebApp -ResourceGroupName Default-Web-WestUS -Name MyApp -ArchivePath C:\project\app.zip
```

Mengunggah konten pesan app.zip aplikasi web bernama MyApp milik grup sumber daya Default-Web-WestUS.

### Contoh 2
```powershell
PS C:\> Publish-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp -Slot Staging -ArchivePath C:\project\javaproject.war
```

Mengunggah konten javaproject.war ke slot Pengembangan dari aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG.

### Contoh 3
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> Publish-AzWebApp -WebApp $app -ArchivePath C:\project\app.zip -AsJob
```

Mengunggah konten akun app.zip aplikasi web yang bernama ContosoApp milik grup sumber daya ContosoRG. Cmdlet akan dijalankan di pekerjaan latar belakang.

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

Mengunggah konten akun java_app.jar ke aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG.

### Contoh 6
```powershell
PS C:\> $app = Get-AzWebApp -ResourceGroupName ContosoRG -Name ContosoApp
PS C:\> Publish-AzWebApp -WebApp $app -ArchivePath C:\project\app.zip -Timeout 300000 -Force
```

Mengunggah konten akun java_app.jar ke aplikasi web bernama ContosoApp milik grup sumber daya ContosoRG. Pengguna bisa Mengatur rentang waktu dalam Milidetik untuk menunggu sebelum waktu permintaan habis.

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
Jalankan cmdlet di latar belakang

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

### -Force
Opsi Hapus Paksa

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

### -Timeout
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## CATATAN

## RELATED LINKS
