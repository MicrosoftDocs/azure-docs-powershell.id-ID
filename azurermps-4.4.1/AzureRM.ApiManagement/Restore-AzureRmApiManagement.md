---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
Module Name: AzureRM.ApiManagement
ms.assetid: 022BBF5F-AFF1-45D5-9153-872779FFBAF4
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Restore-AzureRmApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Restore-AzureRmApiManagement.md
ms.openlocfilehash: 9e19d8e205010ce55886761d2cbb7fd904d5277d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423923"
---
# Restore-AzureRmApiManagement

## SYNOPSIS
Memulihkan Layanan Manajemen API dari blob penyimpanan Azure tertentu.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Restore-AzureRmApiManagement -ResourceGroupName <String> -Name <String> [-StorageContext] <IStorageContext>
 -SourceContainerName <String> -SourceBlobName <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Restore-AzureRmApiManagement** memulihkan Layanan Manajemen API dari cadangan tertentu yang berada di blob Azurestorage.

## EXAMPLES

### Contoh 1: Memulihkan layanan Manajemen API
```
PS C:\>Restore-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Name "RestoredContosoApi" -StorageContext $StorageContext -SourceContainerName "ContosoBackups" -SourceBlobName "ContosoBackup.apimbackup"
```

Perintah ini memulihkan layanan Manajemen API dari blob penyimpanan Azure.

## PARAMETERS

### -Nama
Menentukan nama instans Manajemen API yang akan dipulihkan dengan cadangan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -ResourceGroupName
Menentukan nama grup sumber daya di mana Manajemen API ada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceBlobName
Menentukan nama blob sumber cadangan penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceContainerName
Menentukan nama wadah sumber cadangan penyimpanan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext
Menentukan konteks koneksi penyimpanan.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## CATATAN

## RELATED LINKS

[Backup-AzureRmApiManagement](./Backup-AzureRmApiManagement.md)

[Get-AzureRmApiManagement](./Get-AzureRmApiManagement.md)

[New-AzureRmApiManagement](./New-AzureRmApiManagement.md)

[Remove-AzureRmApiManagement](./Remove-AzureRmApiManagement.md)


