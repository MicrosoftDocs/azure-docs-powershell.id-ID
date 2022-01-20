---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/restore-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Restore-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Restore-AzStorageContainer.md
ms.openlocfilehash: 49038e651e54c49bcd4ec7fcef90a6dbcf0e1306
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136351038"
---
# Restore-AzStorageContainer

## SYNOPSIS
Memulihkan wadah blob penyimpanan Azure yang sebelumnya dihapus.

## SYNTAX

```
Restore-AzStorageContainer [-Name] <String> [-VersionId] <String> [-Context <IStorageContext>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzStorageContainer** memulihkan wadah blob penyimpanan Azure yang dihapus sebelumnya.
Cmdlet ini hanya bekerja setelah mengaktifkan Container softdelete dengan Enable-AzStorageBlobDeleteRetentionPolicy.

## EXAMPLES

### Contoh 1: Wadah daftar menyertakan wadah yang dihapus, dan memulihkan semua wadah yang dihapus dengan saluran
```
PS C:\> Get-AzStorageContainer -IncludeDeleted -Context $ctx | ? { $_.IsDeleted } | Restore-AzStorageContainer

   Storage Account Name: storageaccountname

Name                 PublicAccess         LastModified                   IsDeleted  VersionId                                                                                                                                                                                                                                                         
----                 ------------         ------------                   ---------  ---------                                                                                                                                                                    
container1           Off
container2           Off
```

Perintah ini mencantumkan semua wadah yang telah dihapus, memfilter semua wadah yang dihapus, lalu memulihkan semua wadah yang dihapus ke nama wadah yang sama dengan saluran.

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
Azure Storage Konteks

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
Versi wadah yang dihapus sebelumnya.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
