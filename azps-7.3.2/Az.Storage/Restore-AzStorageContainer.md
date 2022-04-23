---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/restore-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Restore-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Restore-AzStorageContainer.md
ms.openlocfilehash: 8fb08b53cb4a1bd8b1baadee8574925f22104adb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143323793"
---
# Restore-AzStorageContainer

## SYNOPSIS
Memulihkan wadah blob penyimpanan Azure yang dihapus sebelumnya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/restore-azstoragecontainer) untuk informasi terbaru.

## SYNTAX

```
Restore-AzStorageContainer [-Name] <String> [-VersionId] <String> [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzStorageContainer** memulihkan wadah blob penyimpanan Azure yang dihapus sebelumnya.
Cmdlet ini hanya berfungsi setelah softdelete Container yang diaktifkan dengan Enable-AzStorageBlobDeleteRetentionPolicy.

## EXAMPLES

### Contoh 1: Wadah daftar menyertakan wadah yang dihapus, dan memulihkan semua wadah yang dihapus dengan pipeline
```
PS C:\> Get-AzStorageContainer -IncludeDeleted -Context $ctx | ? { $_.IsDeleted } | Restore-AzStorageContainer

   Storage Account Name: storageaccountname

Name                 PublicAccess         LastModified                   IsDeleted  VersionId                                                                                                                                                                                                                                                         
----                 ------------         ------------                   ---------  ---------                                                                                                                                                                    
container1           Off
container2           Off
```

Perintah ini mencantumkan semua kontainer termasuk wadah yang dihapus, memfilter semua wadah yang dihapus, lalu memulihkan semua wadah yang dihapus ke nama wadah yang sama dengan pipeline.

### Contoh 2: Memulihkan wadah tunggal yang dihapus
```
PS C:\> Get-AzStorageContainer -IncludeDeleted -Context $ctx | ? { $_.IsDeleted } 

   Storage Account Name: storageaccountname

Name                 PublicAccess         LastModified                   IsDeleted  VersionId                                                                                                                                                                                                                                                      
----                 ------------         ------------                   ---------  ---------                                                                                                                                                                   
container1                                8/28/2020 10:18:13 AM +00:00   True       01D685BC91A88F22                                                                                                                                                                                                                                                                
container2                                9/4/2020 12:52:37 PM +00:00    True       01D67D248986B6DA  

PS C:\> Restore-AzStorageContainer -Name container1 -VersionId 01D685BC91A88F22 -Context $ctx

   Storage Account Name: storageaccountname

Name                 PublicAccess         LastModified                   IsDeleted  VersionId                                                                                                                                                                                                                                                     
----                 ------------         ------------                   ---------  ---------                                                                                                                                                                                                                                                        
container1           Off
```

Perintah pertama ini mencantumkan semua wadah dan memfilter wadah yang dihapus.
Perintah sekunder memulihkan wadah yang dihapus dengan memasukkan parameter secara manual.

## PARAMETERS

### -Konteks
Objek Konteks Azure Storage

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama wadah yang dihapus sebelumnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Container, DeletedContainerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VersionId
Versi kontainer yang dihapus sebelumnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DeletedContainerVersion, 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
