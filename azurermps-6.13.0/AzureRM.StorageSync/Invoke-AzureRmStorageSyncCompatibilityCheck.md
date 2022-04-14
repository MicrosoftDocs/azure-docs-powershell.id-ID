---
external help file: Microsoft.Azure.Commands.StorageSync.dll-Help.xml
Module Name: AzureRM.StorageSync
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.storagesync/invoke-azurermstoragesynccompatibilitycheck
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StorageSync/Commands.StorageSync/help/Invoke-AzureRmStorageSyncCompatibilityCheck.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/StorageSync/Commands.StorageSync/help/Invoke-AzureRmStorageSyncCompatibilityCheck.md
ms.openlocfilehash: 73e0f00fe184a5462141b060717ca64567d4a67e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141773593"
---
# Invoke-AzureRmStorageSyncCompatibilityCheck

## SYNOPSIS
Memeriksa potensi masalah kompatibilitas antara sistem Anda dan Sinkronisasi File Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### PathBased (Default)
```
Invoke-AzureRmStorageSyncCompatibilityCheck [-Path] <String> [-Credential <PSCredential>] [-SkipSystemChecks]
 [-SkipNamespaceChecks] [-Quiet] [<CommonParameters>]
```

### ComputerNameBased
```
Invoke-AzureRmStorageSyncCompatibilityCheck [-Credential <PSCredential>] [-ComputerName] <String>
 [-SkipSystemChecks] [-Quiet] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzureRmStorageSyncCompatibilityCheck** memeriksa potensi masalah kompatibilitas antara sistem anda dan Azure File Sync. Dengan jalur lokal atau jarak jauh, jalur ini menjalankan sekumpulan validasi pada sistem dan ruang nama file, lalu mengembalikan masalah kompatibilitas yang ditemukan.
Pemeriksaan sistem:
- Kompatibilitas OS Ruang nama file memeriksa:
- Karakter yang tidak didukung
- Ukuran file maksimum
- Panjang jalur maksimum
- Panjang file maksimum
- Ukuran kumpulan data maksimum
- Kedalaman direktori maksimum

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Invoke-AzureRmStorageSyncCompatibilityCheck C:\DATA
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA.

### Contoh 2
```powershell
PS C:\> Invoke-AzureRmStorageSyncCompatibilityCheck C:\DATA -SkipSystemChecks
```

Perintah ini memeriksa kompatibilitas file dan folder di C:\DATA, tetapi tidak melakukan pemeriksaan kompatibilitas sistem.

### Contoh 3
```powershell
PS C:\> $errors = Invoke-AzureRmStorageSyncCompatibilityCheck C:\DATA
PS C:\> $errors | Select-Object -Property Type, Path, Level, Description, Result | Export-Csv -Path C:\results
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA, lalu mengekspor hasil sebagai file CSV ke C:\hasil.

## PARAMETERS

### -ComputerName
Komputer tempat Anda menjalankan pemeriksaan ini.

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

### -Kredensial
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

### -Diam
Menyembunyikan laporan output penulisan ke konsol.

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

### -SkipNamespaceChecks
Atur bendera ini untuk melewati validasi ruang nama file dan hanya melakukan validasi sistem.

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
Atur bendera ini untuk melewati validasi sistem dan hanya melakukan validasi ruang nama file.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.StorageSync.Evaluation.Models.PSValidationResult

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, storagesync, filesync

## RELATED LINKS
