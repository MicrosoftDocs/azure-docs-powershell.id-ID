---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 66AC5120-80B1-46F2-AA51-132BF361602E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermadapplication
schema: 2.0.0
ms.openlocfilehash: 4e7abd4a3b33f54e5a0ec0bdde01e3fe11da31c4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421521"
---
# Get-AzureRmADApplication

## SYNOPSIS
Mencantumkan aplikasi azure active directory yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADApplication [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount] [-Skip <UInt64>]
 [-First <UInt64>] [<CommonParameters>]
```

### ApplicationObjectIdParameterSet
```
Get-AzureRmADApplication -ObjectId <Guid> [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount]
 [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

### ApplicationIdParameterSet
```
Get-AzureRmADApplication -ApplicationId <Guid> [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount]
 [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

### SearchStringParameterSet
```
Get-AzureRmADApplication -DisplayNameStartWith <String> [-DefaultProfile <IAzureContextContainer>]
 [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzureRmADApplication -DisplayName <String> [-DefaultProfile <IAzureContextContainer>] [-IncludeTotalCount]
 [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

### ApplicationIdentifierUriParameterSet
```
Get-AzureRmADApplication -IdentifierUri <String> [-DefaultProfile <IAzureContextContainer>]
 [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan aplikasi azure active directory yang sudah ada.
Pencarian aplikasi dapat dilakukan oleh ObjectId, ApplicationId, IdentifierUri atau DisplayName.
Jika tidak ada parameter yang diberikan, parameter itu mengambil semua aplikasi di bawah penyewa.

## EXAMPLES

### Contoh 1 - Daftar semua aplikasi

```
PS C:\> Get-AzureRmADApplication
```

Mencantumkan semua aplikasi di bawah penyewa.

### Contoh 2 - Daftar aplikasi menggunakan paging

```
PS C:\> Get-AzureRmADApplication -First 100
```

Mencantumkan 100 aplikasi pertama di bawah penyewa.

### Contoh 3 - Dapatkan aplikasi berdasarkan URI pengidentifikasi

```
PS C:\> Get-AzureRmADApplication -IdentifierUri http://mySecretApp1
```

Dapatkan aplikasi dengan uri pengidentifikasi sebagai " http://mySecretApp1 ".

### Contoh 4 - Dapatkan aplikasi menurut id objek

```
PS C:\> Get-AzureRmADApplication -ObjectId 39e64ec6-569b-4030-8e1c-c3c519a05d69
```

Dapatkan aplikasi dengan id objek '39e64ec6-569b-4030-8e1c-c3c519a05d69'.

## PARAMETERS

### -ApplicationId
Id aplikasi dari aplikasi yang akan diambil.

```yaml
Type: System.Guid
Parameter Sets: ApplicationIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -DisplayName
Nama tampilan aplikasi.

```yaml
Type: System.String
Parameter Sets: DisplayNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayNameStartWith
Ambil semua aplikasi yang dimulai dengan nama tampilan.

```yaml
Type: System.String
Parameter Sets: SearchStringParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -First
Jumlah maksimum objek untuk dikembalikan.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentifierUri
Uri pengidentifikasi unik dari aplikasi untuk diambil.

```yaml
Type: System.String
Parameter Sets: ApplicationIdentifierUriParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeTotalCount
Melaporkan jumlah objek dalam set data. Saat ini, parameter ini tidak melakukan apa-apa.

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

### -ObjectId
Id objek aplikasi yang akan diambil.

```yaml
Type: System.Guid
Parameter Sets: ApplicationObjectIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lewati
Mengabaikan objek N pertama, lalu mendapatkan objek yang tersisa.

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.Guid

### System.String

## OUTPUTS

### Microsoft.Azure. Graph. RBAC. Version1_6.ActiveDirectory.FOLDApplication

## CATATAN

## RELATED LINKS

[Remove-AzureRmADAppCredential](./Remove-AzureRmADAppCredential.md)

[New-AzureRmADAppCredential](./New-AzureRmADAppCredential.md)

[Get-AzureRmADAppCredential](./Get-AzureRmADAppCredential.md)

[Remove-AzureRmADApplication](./Remove-AzureRmADApplication.md)



[Aplikasi New-AzureRmAD](./New-AzureRmADApplication.md)

