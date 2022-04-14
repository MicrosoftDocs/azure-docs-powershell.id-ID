---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: E771D1F2-A06B-44BB-AAFF-9459DC6303E6
online version: ''
schema: 2.0.0
ms.openlocfilehash: ce3cef70ab7ea8c0198eea9340c8985b5bb8e326
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142093383"
---
# Select-AzureStorSimpleResource

## SYNOPSIS
Mengatur sumber daya sebagai sumber daya saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Select-AzureStorSimpleResource -ResourceName <String> [-RegistrationKey <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Select-AzureStorSimpleResource** mengatur sumber daya sebagai sumber daya saat ini.
Setelah Anda memilih sumber daya, cmdlet lain diterapkan dalam konteks sumber daya tersebut.

## EXAMPLES

### Contoh 1: Pilih sumber daya untuk pertama kalinya
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa" -RegistrationKey "<your registration key>"
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa
```

Perintah ini memilih sumber daya yang bernama Contoso64-Tsqa sebagai konteks saat ini.
Dalam contoh ini, komputer belum memiliki konteks ini yang diinisialisasi sebelumnya, dan oleh karena itu, Anda harus menentukan nilai untuk parameter *RegistrationKey* .

### Contoh 2: Mencoba memilih sumber daya
```
This command gets the current context for this computer by using the **Get-AzureStorSimpleResourceContext** cmdlet. The current selected resource is Contoso64-Tsqa. This is consistent with the previous example. 
PS C:\>Get-AzureStorSimpleResourceContext
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa 

This command attempts to reset the resource to be Contoso02-Resource. For this example, this resource has not been previously selected. The registration key is not saved or included in the command. The command cannot select the resource. 
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso02-Resource"
Select-AzureStorSimpleResource : Could not find the persisted secret. Please use Select-AzureStorSimpleResource and
provide the Registration key once again.
```

### Contoh 3: Memilih sumber daya yang dipilih sebelumnya
```
PS C:\>Select-AzureStorSimpleResource -ResourceName "Contoso64-Tsqa"
ResourceId           ResourceName
----------           ------------
1909806764156522689  Contoso64-Tsqa
```

Perintah ini memilih sumber daya yang bernama Contoso64-Tsqa sebagai konteks saat ini.
Dalam contoh ini, konteks tersebut sebelumnya telah dipilih, dan oleh karena itu, Anda tidak perlu menentukan nilai untuk parameter *RegistrationKey* .

## PARAMETERS

### -Profil
Menentukan profil Azure.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegistrationKey
Menentukan kunci registrasi.
Tentukan kunci saat pertama kali Anda memilih sumber daya.
Setelah cmdlet ini memilih sumber daya saat ini, cmdlet menggunakan kunci ini, sesuai kebutuhan.
Untuk informasi selengkapnya, lihat [Mendapatkan kunci registrasi layanan](https://msdn.microsoft.com/en-us/library/azure/dn772346.aspx)  (https://msdn.microsoft.com/en-us/library/azure/dn772346.aspx) di Microsoft Developer Network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceName
Menentukan nama sumber daya untuk dipilih sebagai sumber daya saat ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### StorSimpleResourceContext
Cmdlet ini mengembalikan objek **StorSimpleResourceContext** yang berisi detail untuk konteks sumber daya.

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleResource](./Get-AzureStorSimpleResource.md)

[Get-AzureStorSimpleResourceContext](./Get-AzureStorSimpleResourceContext.md)


