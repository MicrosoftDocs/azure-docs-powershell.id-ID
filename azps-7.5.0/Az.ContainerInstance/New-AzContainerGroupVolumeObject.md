---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupVolumeObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupVolumeObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupVolumeObject.md
ms.openlocfilehash: dadf33c64b2eea8b84a7ed721acfa8c862ec0216
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145808214"
---
# New-AzContainerGroupVolumeObject

## SYNOPSIS
Buat objek dalam memori untuk Volume.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainergroupvolumeobject) untuk informasi terbaru.

## SYNTAX

```
New-AzContainerGroupVolumeObject -Name <String> [-AzureFileReadOnly] [-AzureFileShareName <String>]
 [-AzureFileStorageAccountKey <SecureString>] [-AzureFileStorageAccountName <String>]
 [-EmptyDir <IVolumeEmptyDir>] [-GitRepoDirectoryName <String>] [-GitRepoRepositoryUrl <String>]
 [-GitRepoRevision <String>] [-Secret <ISecretVolume>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk Volume.

## EXAMPLES

### Contoh 1: Membuat volume File Azure
```powershell
New-AzContainerGroupVolumeObject -Name "myvolume" -AzureFileShareName "myshare" -AzureFileStorageAccountName "username" -AzureFileStorageAccountKey (ConvertTo-SecureString "******" -AsPlainText -Force)
```

```output
Name
----
myvolume
```

Perintah ini membuat volume File Azure.

### Contoh 2: Membuat volume direktori kosong
```powershell
New-AzContainerGroupVolumeObject -Name "emptyvolume" -EmptyDir @{} | fl
```

```output
AzureFileReadOnly           : 
AzureFileShareName          : 
AzureFileStorageAccountKey  : 
AzureFileStorageAccountName : 
EmptyDir                    : {
                              }
GitRepoDirectory            : 
GitRepoRepository           : 
GitRepoRevision             : 
Name                        : emptyvolume
Secret                      : {
                              }
```

Perintah ini membuat volume direktori kosong.

## PARAMETERS

### -AzureFileReadOnly
Bendera yang menunjukkan apakah File Azure yang dibagikan dipasang sebagai volume bersifat baca-saja.

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

### -AzureFileShareName
Nama pembagian File Azure yang akan dipasang sebagai volume.

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

### -AzureFileStorageAccountKey
Kunci akses akun penyimpanan yang digunakan untuk mengakses pembagian File Azure.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureFileStorageAccountName
Nama akun penyimpanan yang berisi pembagian File Azure.

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

### -EmptyDir
Volume direktori kosong.
Untuk membuat, lihat bagian CATATAN untuk properti EMPTYDIR dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IVolumeEmptyDir
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GitRepoDirectoryName
Nama direktori target.
Tidak boleh berisi atau dimulai dengan '..'.
Jika '.' disediakan, direktori volume akan menjadi repositori git.
Jika tidak, jika ditentukan, volume akan berisi repositori git di subdirektori dengan nama yang diberikan.

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

### -GitRepoRepositoryUrl
URL repositori.

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

### -GitRepoRevision
Terapkan hash untuk revisi yang ditentukan.

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

### -Name
Nama volume.

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

### -Rahasia
Volume rahasia.
Untuk membuat, lihat bagian CATATAN untuk properti SECRET dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ISecretVolume
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.Volume

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EMPTYDIR <IVolumeEmptyDir>: Volume direktori kosong.
  - `[(Any) <Object>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

RAHASIA <ISecretVolume>: Volume rahasia.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

