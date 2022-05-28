---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/az.storagesync/invoke-azstoragesynccompatibilitycheck
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncCompatibilityCheck.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncCompatibilityCheck.md
ms.openlocfilehash: 2dc8bf92326aa7c28505a68442922a2a081cd3cc
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145548501"
---
# Invoke-AzStorageSyncCompatibilityCheck

## SYNOPSIS
Memeriksa potensi masalah kompatibilitas antara sistem Anda dan Azure File Sync.

## SYNTAX

### PathBased (Default)
```
Invoke-AzStorageSyncCompatibilityCheck [-Path] <String> [-Credential <PSCredential>] [-SkipSystemChecks]
 [-SkipNamespaceChecks] [<CommonParameters>]
```

### ComputerNameBased
```
Invoke-AzStorageSyncCompatibilityCheck [-Credential <PSCredential>] [-ComputerName] <String>
 [-SkipSystemChecks] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzStorageSyncCompatibilityCheck** memeriksa potensi masalah kompatibilitas antara sistem Anda dan Azure File Sync. Mengingat jalur lokal atau jarak jauh, ia melakukan serangkaian validasi pada sistem dan namespace file, lalu mengembalikan masalah kompatibilitas yang ditemukannya.
Pemeriksaan sistem:
- Pemeriksaan namespace file kompatibilitas OS:
- Karakter yang tidak didukung
- Ukuran file maksimal
- Panjang jalur maksimum
- Panjang file maksimum
- Ukuran himpunan data maksimum
- Kedalaman direktori maksimum

## EXAMPLES

### Contoh 1
```powershell
Invoke-AzStorageSyncCompatibilityCheck C:\DATA
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA.

### Contoh 2
```powershell
Invoke-AzStorageSyncCompatibilityCheck C:\DATA -SkipSystemChecks
```

Perintah ini memeriksa kompatibilitas file dan folder di C:\DATA, tetapi tidak melakukan pemeriksaan kompatibilitas sistem.

### Contoh: 3
```powershell
$validation = Invoke-AzStorageSyncCompatibilityCheck C:\DATA
$validation.Results | Select-Object -Property Type, Path, Level, Description, Result | Export-Csv -Path C:\results.csv -Encoding utf8
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA, lalu mengekspor hasilnya sebagai file CSV ke C:\results.

## PARAMETERS

### -ComputerName
Komputer tempat Anda melakukan pemeriksaan ini.

```yaml
Type: System.String
Parameter Sets: ComputerNameBased
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Kredensial Anda untuk berbagi yang Anda validasi.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jalur
Jalur UNC berbagi yang Anda validasi.

```yaml
Type: System.String
Parameter Sets: PathBased
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNamespaceChecks
Atur bendera ini untuk melewati validasi namespace file dan hanya melakukan validasi sistem.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathBased
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipSystemChecks
Atur bendera ini untuk melewati validasi sistem dan hanya melakukan validasi namespace file.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.StorageSync.Evaluation.Models.PSValidationResult

## NOTES
* Kata kunci: azure, Az, arm, sumber daya, manajemen, storagesync, filesync

## RELATED LINKS
