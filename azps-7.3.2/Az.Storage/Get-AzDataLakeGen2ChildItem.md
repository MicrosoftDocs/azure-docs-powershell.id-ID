---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azdatalakegen2childitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzDataLakeGen2ChildItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzDataLakeGen2ChildItem.md
ms.openlocfilehash: 513dbf1bf11ea119cb107511b79c198b611a4c77
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143070335"
---
# Get-AzDataLakeGen2ChildItem

## SYNOPSIS
Mencantumkan sub direktori dan file dari akar direktori atau filesystem.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/get-azdatalakegen2childitem) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataLakeGen2ChildItem [-FileSystem] <String> [[-Path] <String>] [-FetchProperty] [-Recurse]
 [-MaxCount <Int32>] [-ContinuationToken <String>] [-AsJob] [-OutputUserPrincipalName]
 [-Context <IStorageContext>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataLakeGen2ChildItem** mencantumkan sub direktori dan file dalam direktori atau Filesystem di akun penyimpanan Azure.
Cmdlet ini hanya berfungsi jika Ruang Nama Hierarki diaktifkan untuk akun Storage. Akun semacam ini dapat dibuat dengan menjalankan cmdlet "New-AzStorageAccount" dengan "-EnableHierarchicalNamespace $true".

## EXAMPLES

### Contoh 1: Mencantumkan sub item langsung dari Filesystem
```
PS C:\>Get-AzDataLakeGen2ChildItem -FileSystem "filesystem1" 

   FileSystem Name: filesystem1

Path                 IsDirectory  Length          LastModified         Permissions  Owner                Group               
----                 -----------  ------          ------------         -----------  -----                -----               
dir1                 True                         2020-03-13 13:07:34Z rwxr-x---    $superuser           $superuser          
dir2                 True                         2020-03-23 09:28:36Z rwxr-x---    $superuser           $superuser
```

Perintah ini mencantumkan sub item langsung dari Filesystem

### Contoh 2: Daftar secara rekurtif dari direktori, dan ambil Properti/ACL
```
PS C:\>Get-AzDataLakeGen2ChildItem -FileSystem "filesystem1" -Path "dir1/" -Recurse -FetchProperty

   FileSystem Name: filesystem1

Path                 IsDirectory  Length          LastModified         Permissions  Owner                Group               
----                 -----------  ------          ------------         -----------  -----                -----               
dir1/dir3            True                         2020-03-23 09:34:31Z rwx---rwx    $superuser           $superuser          
dir1/file1           False        1024            2020-03-23 09:29:18Z rwx---rwx    $superuser           $superuser           
dir1/testfile_1K_0   False        1024            2020-03-23 09:29:21Z rw-r-----    $superuser           $superuser
```

Perintah ini mencantumkan sub item langsung dari Filesystem

### Contoh 3: Mencantumkan item secara rekurtif dari Filesystem dalam beberapa kumpulan
```
PS C:\> $MaxReturn = 1000
PS C:\> $FileSystemName = "filesystem1"
PS C:\> $Total = 0
PS C:\> $Token = $Null
PS C:\> do
 {
     $items = Get-AzDataLakeGen2ChildItem -FileSystem $FileSystemName -Recurse -MaxCount $MaxReturn  -ContinuationToken $Token
     $Total += $items.Count
     if($items.Length -le 0) { Break;}
     $Token = $items[$items.Count -1].ContinuationToken;
 }
 While ($null -ne $Token)
PS C:\> Echo "Total $Total items in Filesystem $FileSystemName"
```

Contoh ini menggunakan parameter *MaxCount* dan *ContinuationToken* untuk mencantumkan item secara berulang dari Filesystem dalam beberapa kumpulan.
*MaxCount* kecil dapat membatasi item yang dikembalikan dari satu requst, dapat membantu operasi mengurangi waktu, dan membatasi penggunaan memori Powershell.
Empat perintah pertama menetapkan nilai ke variabel untuk digunakan dalam contoh.
Perintah kelima menentukan pernyataan **Do-While** yang menggunakan cmdlet **Get-AzDataLakeGen2ChildItem** untuk mencantumkan item.
Pernyataan ini mencakup token kelanjutan yang disimpan dalam variabel $Token.
$Token mengubah nilai saat pengulangan berjalan.
Perintah terakhir menggunakan perintah **Gema** untuk menampilkan total.

## PARAMETERS

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

### -ContinuationToken
Token Kelanjutan.

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

### -FetchProperty
Ambil properti item datalake dan ACL.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FetchPermission

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Nama FileSystem

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxCount
Jumlah maksimal dari blob yang dapat kembali.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputUserPrincipalName
Jika speicify parameter ini, nilai identitas pengguna yang dikembalikan dalam bidang pemilik dan grup dari setiap entri daftar akan diubah dari ID Objek Azure Active Directory menjadi Nama Pokok Pengguna. Jika tidak mempopulerkan parameter ini, nilai akan dikembalikan sebagai ID Objek Azure Active Directory. Perhatikan bahwa ID Objek grup dan aplikasi tidak diterjemahkan karena tidak memiliki nama yang bersahabat yang unik.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: UserPrincipalName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jalur
Jalur dalam Filesystem tertentu yang harus diambil.
Harus berupa direktori, dalam format 'directory1/directory2/'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Berulang
Menunjukkan apakah akan mendapatkan Item Anak secara rekurtif.
Defaultnya adalah false.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureDataLakeGen2Item

## NOTES

## RELATED LINKS
