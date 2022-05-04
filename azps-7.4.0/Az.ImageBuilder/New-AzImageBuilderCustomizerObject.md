---
external help file: ''
Module Name: Az.ImageBuilder
online version: https://docs.microsoft.com/powershell/module/az.imagebuilder/new-AzImageBuilderCustomizerObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImageBuilder/help/New-AzImageBuilderCustomizerObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImageBuilder/help/New-AzImageBuilderCustomizerObject.md
ms.openlocfilehash: 2de50f9f08da05736e8df2ebadbd6b969ba4cec5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144585506"
---
# New-AzImageBuilderCustomizerObject

## SYNOPSIS
Menjelaskan satuan kustomisasi gambar

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.imagebuilder/new-azimagebuildercustomizerobject) untuk informasi terbaru.

## SYNTAX

### ShellCustomizer (Default)
```
New-AzImageBuilderCustomizerObject -CustomizerName <String> -ShellCustomizer [-Inline <String[]>]
 [-ScriptUri <String>] [-Sha256Checksum <String>] [<CommonParameters>]
```

### FileCustomizer
```
New-AzImageBuilderCustomizerObject -CustomizerName <String> -FileCustomizer [-Destination <String>]
 [-Sha256Checksum <String>] [-SourceUri <String>] [<CommonParameters>]
```

### PowerShellCustomizer
```
New-AzImageBuilderCustomizerObject -CustomizerName <String> -PowerShellCustomizer [-Inline <String[]>]
 [-RunAsSystem <Boolean>] [-RunElevated <Boolean>] [-ScriptUri <String>] [-Sha256Checksum <String>]
 [-ValidExitCode <Int32[]>] [<CommonParameters>]
```

### RestartCustomizer
```
New-AzImageBuilderCustomizerObject -CustomizerName <String> -RestartCustomizer [-RestartCheckCommand <String>]
 [-RestartCommand <String>] [-RestartTimeout <String>] [<CommonParameters>]
```

### WindowsUpdateCustomizer
```
New-AzImageBuilderCustomizerObject -CustomizerName <String> -WindowsUpdateCustomizer [-Filter <String[]>]
 [-SearchCriterion <String>] [-UpdateLimit <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Menjelaskan satuan kustomisasi gambar

## EXAMPLES

### Contoh 1: Membuat penyesuai pembaruan windows
```powershell
New-AzImageBuilderCustomizerObject -WindowsUpdateCustomizer -Filter ("BrowseOnly", "IsInstalled") -SearchCriterion "BrowseOnly=0 and IsInstalled=0"  -UpdateLimit 100 -CustomizerName 'WindUpdate'
```

```output
Name       Type          Filter                    SearchCriterion                UpdateLimit
----       ----          ------                    ---------------                -----------
WindUpdate WindowsUpdate {BrowseOnly, IsInstalled} BrowseOnly=0 and IsInstalled=0 100
```

Perintah ini membuat penyesuai pembaruan windows.

### Contoh 2: Membuat penyesuai file
```powershell
New-AzImageBuilderCustomizerObject -FileCustomizer -CustomizerName 'filecus' -Destination 'c:\\buildArtifacts\\index.html' -SourceUri 'https://github.com/danielsollondon/azvmimagebuilder/blob/master/quickquickstarts/exampleArtifacts/buildArtifacts/index.html'
```

```output
Name    Type Destination                    Sha256Checksum SourceUri
----    ---- -----------                    -------------- ---------
filecus File c:\\buildArtifacts\\index.html                https://github.com/danielsollondon/azvmimagebuilder/blob/master/quickquickstarts/exampleArtifacts/buildArtifacts/…
```

Perintah ini membuat penyesuai file.

### Contoh 3: Membuat penyesuai powershell
```powershell
$inline = @("mkdir c:\\buildActions", "echo Azure-Image-Builder-Was-Here  > c:\\buildActions\\buildActionsOutput.txt")
New-AzImageBuilderCustomizerObject -PowerShellCustomizer -CustomizerName settingUpMgmtAgtPath -RunElevated $false -Inline $inline
```

```output
Name                 Type       Inline                                                                                                  RunElevated ScriptUri Sha256Checksum
----                 ----       ------                                                                                                  ----------- --------- --------------
settingUpMgmtAgtPath PowerShell {mkdir c:\\buildActions, echo Azure-Image-Builder-Was-Here  > c:\\buildActions\\buildActionsOutput.txt} False
```

Perintah ini membuat penyesuai powershell.

### Contoh 4: Membuat penyesuai hidupkan ulang
```powershell
New-AzImageBuilderCustomizerObject -RestartCustomizer -CustomizerName 'restcus' -RestartCommand 'shutdown /f /r /t 0 /c \"packer restart\"' -RestartCheckCommand 'powershell -command "& {Write-Output "restarted."}"' -RestartTimeout '10m'
```

```output
Name    Type           RestartCheckCommand                                 RestartCommand                            RestartTimeout
----    ----           -------------------                                 --------------                            --------------
restcus WindowsRestart powershell -command "& {Write-Output "restarted."}" shutdown /f /r /t 0 /c \"packer restart\" 10m
```

Perintah ini membuat penyesuai hidupkan ulang.

### Contoh 5: Membuat penyesuai shell
```powershell
New-AzImageBuilderCustomizerObject -ShellCustomizer -CustomizerName downloadBuildArtifacts -ScriptUri "https://raw.githubusercontent.com/danielsollondon/azvmimagebuilder/master/quickquickstarts/customizeScript2.sh" 
```

```output
Name                   Type  Inline ScriptUri                                                                                                      Sha256Checksum
----                   ----  ------ ---------                                                                                                      --------------
downloadBuildArtifacts Shell        https://raw.githubusercontent.com/danielsollondon/azvmimagebuilder/master/quickquickstarts/customizeScript2.sh
```

Perintah ini membuat penyesuai shell.

## PARAMETERS

### -CustomizerName
Nama yang Mudah Diingat untuk memberikan konteks tentang apa yang dilakukan langkah penyesuaian ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Destination
Jalur absolut ke file (dengan struktur direktori berlapis yang sudah dibuat) tempat file (dari sourceUri) akan diunggah ke di VM.

```yaml
Type: System.String
Parameter Sets: FileCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileCustomizer
Mengunggah file ke VM (Linux, Windows).
Sesuai dengan provisioner file Packer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FileCustomizer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Array filter untuk memilih pembaruan yang akan diterapkan.
Hilangkan atau tentukan array kosong untuk menggunakan default (tanpa filter).
Lihat tautan di atas untuk contoh dan deskripsi terperinci dari bidang ini.

```yaml
Type: System.String[]
Parameter Sets: WindowsUpdateCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sebaris
Array perintah shell untuk dijalankan.

```yaml
Type: System.String[]
Parameter Sets: PowerShellCustomizer, ShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellCustomizer
Menjalankan PowerShell yang ditentukan pada VM (Windows).
Sesuai dengan provisioner powershell Packer.
Tepat salah satu dari 'scriptUri' atau 'inline' dapat ditentukan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellCustomizer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartCheckCommand
Perintah untuk memeriksa apakah hidupkan ulang berhasil [Default: ''].

```yaml
Type: System.String
Parameter Sets: RestartCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartCommand
Perintah untuk menjalankan restart [Default: 'shutdown /r /f /t 0 /c packer restart']

```yaml
Type: System.String
Parameter Sets: RestartCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartCustomizer
Reboot VM dan menunggunya kembali online (Windows).
Sesuai dengan provisioner windows-restart Packer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RestartCustomizer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartTimeout
Waktu habis hidupkan ulang yang ditentukan sebagai string besaran dan unit, misalnya '5m' (5 menit) atau '2 jam' (2 jam) [Default: '5m'].

```yaml
Type: System.String
Parameter Sets: RestartCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsSystem
Jika ditentukan, skrip PowerShell akan dijalankan dengan hak istimewa yang ditingkatkan menggunakan pengguna Sistem Lokal.
Hanya dapat benar ketika bidang runElevated di atas diatur ke true.

```yaml
Type: System.Boolean
Parameter Sets: PowerShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunElevated
Jika ditentukan, skrip PowerShell akan dijalankan dengan hak istimewa yang ditingkatkan.

```yaml
Type: System.Boolean
Parameter Sets: PowerShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptUri
URI skrip shell yang akan dijalankan untuk penyesuaian.
Ini bisa menjadi tautan github, SAS URI untuk Azure Storage, dll.

```yaml
Type: System.String
Parameter Sets: PowerShellCustomizer, ShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchCriterion
Kriteria untuk mencari pembaruan.
Hilangkan atau tentukan string kosong untuk menggunakan default (cari semua).
Lihat tautan di atas untuk contoh dan deskripsi terperinci dari bidang ini.

```yaml
Type: System.String
Parameter Sets: WindowsUpdateCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sha256Checksum
Checksum SHA256 dari skrip shell yang disediakan di bidang scriptUri.

```yaml
Type: System.String
Parameter Sets: FileCustomizer, PowerShellCustomizer, ShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShellCustomizer
Menjalankan skrip shell selama fase kustomisasi (Linux).
Sesuai dengan provisioner shell Packer.
Tepat salah satu dari 'scriptUri' atau 'inline' dapat ditentukan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShellCustomizer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceUri
URI file yang akan diunggah untuk menyesuaikan VM.
Ini bisa menjadi tautan github, SAS URI untuk Azure Storage, dll.

```yaml
Type: System.String
Parameter Sets: FileCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateLimit
Jumlah maksimum pembaruan yang akan diterapkan pada satu waktu.
Hilangkan atau tentukan 0 untuk menggunakan default (1000).

```yaml
Type: System.Int32
Parameter Sets: WindowsUpdateCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValidExitCode
Kode keluar yang valid untuk skrip PowerShell.
[Default: 0].

```yaml
Type: System.Int32[]
Parameter Sets: PowerShellCustomizer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsUpdateCustomizer
Menginstal Pembaruan Windows.
Sesuai dengan Packer Windows Update Provisioner (https://github.com/rgl/packer-provisioner-windows-update).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsUpdateCustomizer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImageBuilder.Models.Api20200214.IImageTemplateCustomizer

## NOTES

ALIAS

## RELATED LINKS

