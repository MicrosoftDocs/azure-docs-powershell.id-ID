---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
Module Name: AzureRM.Tags
ms.assetid: 66B25541-0FA5-46CF-90D8-FE9527BE11C6
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Remove-AzureRmTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Tags/Commands.Tags/help/Remove-AzureRmTag.md
ms.openlocfilehash: 909781b8cd441daab8bf5f567404a5e99e88cd0d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422306"
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
Untuk menghapus nilai tertentu dari tag yang sudah ditentukan sebelumnya, gunakan parameter *Nilai.*
Secara default, **Remove-AzureRmTag** menghapus tag yang ditentukan dan semua nilainya. Anda tidak bisa menghapus tag atau nilai yang saat ini diterapkan ke grup sumber daya atau sumber daya.

Sebelum menggunakan **Remove-AzureRmTag,** gunakan parameter *Tag* cmdlet Set-AzureRMResourceGroup cmdlet untuk menghapus tag atau nilai dari grup sumber daya atau sumber daya.

Modul Tag Azure yang **dihapus-AzureRmTag merupakan** bagian dari dapat membantu Anda mengelola tag Azure yang sudah ditentukan sebelumnya.
Tag Azure adalah pasangan nilai nama yang dapat digunakan untuk mengategorikan sumber daya dan grup sumber daya Azure, seperti menurut departemen atau pusat biaya, atau untuk melacak catatan atau komentar tentang sumber daya dan grup.

Anda bisa menetapkan dan menerapkan tag dalam satu langkah, tapi tag yang sudah ditentukan sebelumnya memungkinkan Anda menetapkan nama dan nilai standar, konsisten, dan yang bisa diprediksi untuk tag di langganan Anda.
Jika langganan menyertakan tag yang sudah ditentukan sebelumnya, Anda tidak dapat menerapkan tag atau nilai yang tidak didefinisikan ke sumber daya atau grup sumber daya apa pun dalam langganan.

## EXAMPLES

### Contoh 1: Menghapus tag yang sudah ditentukan sebelumnya
```
PS C:\>Remove-AzureRmTag -Name "Department"
```

Perintah ini menghapus tag yang sudah ditentukan sebelumnya bernama Departemen dan semua sumber dayanya.
Jika tag telah diterapkan ke sumber daya atau grup sumber daya, perintah akan gagal.

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
Tag tidak akan menghapus tag.
Jika nilai telah diterapkan ke sumber daya atau grup sumber daya, perintah akan gagal.

## PARAMETERS

### -Nama
Menentukan nama tag yang akan dihapus.
Secara default, **Remove-AzureRmTag** menghapus tag yang ditentukan dan semua nilainya.
Untuk menghapus nilai yang dipilih, tetapi tidak menghapus tag, gunakan parameter *Value.*

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
Mengembalikan objek yang mewakili tag yang dihapus atau tag hasil dengan nilai yang dihapus.

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
Menghapus nilai tertentu dari tag yang sudah ditentukan sebelumnya, tapi tidak menghapus tag.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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

### Tidak ada

## OUTPUTS

### Tidak Ada atau Microsoft.Azure.Commands.Tags.Model.PSTag

## CATATAN

## RELATED LINKS

[Get-AzureRmTag](./Get-AzureRmTag.md)

[New-AzureRmTag](./New-AzureRmTag.md)


