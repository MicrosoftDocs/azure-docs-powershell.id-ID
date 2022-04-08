---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/az.storagesync/invoke-azstoragesynccompatibilitycheck
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncCompatibilityCheck.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncCompatibilityCheck.md
ms.openlocfilehash: 491e8a91319053a260cd4c4367401b01cfdd5e32
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140499441"
---
# Invoke-AzStorageSyncCompatibilityCheck

## SYNOPSIS
Memeriksa potensi masalah kompatibilitas antara sistem dan Sinkronisasi File Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.storagesync/invoke-azstoragesynccompatibilitycheck) untuk informasi terkini.

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
Cmdlet **Invoke-AzStorageSyncCompatibilityCheck** memeriksa potensi masalah kompatibilitas antara sistem Anda dan Sinkronisasi File Azure. Jika diberi jalur lokal atau jarak jauh, program ini menjalankan serangkaian validasi pada sistem dan ruang nama file, lalu mengembalikan setiap masalah kompatibilitas yang ditemukannya.
Pemeriksaan sistem:
- Pemeriksaan ruang nama File kompatibilitas OS:
- Karakter yang tidak didukung
- Ukuran file maksimum
- Panjang jalur maksimum
- Panjang file maksimum
- Ukuran maksimum set data
- Kedalaman direktori maksimum

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Invoke-AzStorageSyncCompatibilityCheck C:\DATA
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA.

### Contoh 2
```powershell
PS C:\> Invoke-AzStorageSyncCompatibilityCheck C:\DATA -SkipSystemChecks
```

Perintah ini memeriksa kompatibilitas file dan folder di C:\DATA, tetapi tidak menjalankan pemeriksaan kompatibilitas sistem.

### Contoh 3
```powershell
PS C:\> $validation = Invoke-AzStorageSyncCompatibilityCheck C:\DATA
PS C:\> $validation.Results | Select-Object -Property Type, Path, Level, Description, Result | Export-Csv -Path C:\results.csv -Encoding utf8
```

Perintah ini memeriksa kompatibilitas sistem dan juga file dan folder di C:\DATA, lalu mengekspor hasil sebagai file CSV ke C:\hasil.

## PARAMETERS

### -ComputerName
Komputer yang Anda menjalankan pemeriksaan ini.

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
Kredensial Anda untuk berbagi yang sedang Anda validasi.

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

### -Path
Jalur UNC dari berbagi yang Anda validasi.

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
Set this flag to skip file namespace validations and only perform system validations.

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
Set this flag to skip system validations and only perform file namespace validations.

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

## CATATAN
* Kata kunci: azure, Az, arm, resource, management, storagesync, filesync

## RELATED LINKS
