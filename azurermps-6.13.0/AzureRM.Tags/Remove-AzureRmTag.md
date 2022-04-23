---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM.Tags
ms.assetid: 66B25541-0FA5-46CF-90D8-FE9527BE11C6
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.tags/remove-azurermtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Remove-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Remove-AzureRmTag.md
ms.openlocfilehash: 1c7f55bb3f84051326cd102c1c12a2d978a79f71
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212706"
---
# Remove-AzureRmTag

## SYNOPSIS
Menghapus tag atau nilai Azure yang sudah ditentukan sebelumnya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmTag [-Name] <String> [[-Value] <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmTag** menghapus tag dan nilai Azure yang sudah ditentukan sebelumnya dari langganan Anda.
Untuk menghapus nilai tertentu dari tag yang sudah ditentukan sebelumnya, gunakan parameter *Nilai* .
Secara default, **Remove-AzureRmTag** menghapus tag yang ditentukan dan semua nilainya. Anda tidak dapat menghapus tag atau nilai yang saat ini diterapkan ke grup sumber daya atau sumber daya.
Sebelum menggunakan **Remove-AzureRmTag**, gunakan parameter *Tag* cmdlet Set-AzureRMResourceGroup untuk menghapus tag atau nilai dari grup sumber daya atau sumber daya.
Modul Tag Azure yang **menghapus-AzureRmTag** adalah bagian dari dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang bisa Anda gunakan untuk mengategorikan sumber daya dan grup sumber daya Azure Anda, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.
Anda bisa menentukan dan menerapkan tag dalam satu langkah, tetapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan dapat diprediksi untuk tag dalam langganan Anda.

## EXAMPLES

### Contoh 1: Menghapus tag yang sudah ditentukan sebelumnya
```
PS C:\>Remove-AzureRmTag -Name "Department"
```

Perintah ini menghapus tag yang sudah ditentukan sebelumnya bernama Departemen dan semua sumber dayanya.
Jika tag telah diterapkan ke sumber daya atau grup sumber daya, perintah gagal.

### Contoh 2: Menghapus nilai dari tag yang sudah ditentukan sebelumnya
```
PS C:\>Remove-AzureRmTag -Name "Department" -Value "HumanResources" -PassThru
Name:   Department
Count:  14
Values: 

        Name        Count
        =========   =====

        Finance        2
        IT            12
```

Perintah ini menghapus nilai HumanResources dari tag Departemen yang sudah ditentukan sebelumnya.
Ini tidak menghapus tag.
Jika nilai telah diterapkan ke sumber daya atau grup sumber daya, perintah gagal.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Menentukan nama tag yang akan dihapus.
Secara default, **Remove-AzureRmTag** menghapus tag yang ditentukan dan semua nilainya.
Untuk menghapus nilai yang dipilih, tetapi tidak menghapus tag, gunakan parameter *Nilai* .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili tag yang dihapus atau tag yang dihasilkan dengan nilai yang dihapus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Menghapus nilai yang ditentukan dari tag yang sudah ditentukan sebelumnya, tetapi tidak menghapus tag.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Common.Tags.PSTag

## NOTES

## RELATED LINKS

[Get-AzureRmTag](./Get-AzureRmTag.md)

[AzureRmTag Baru](./New-AzureRmTag.md)


