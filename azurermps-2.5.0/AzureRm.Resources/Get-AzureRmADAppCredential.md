---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 6AC9DA05-756D-4D59-BD97-DBAAFBB3C7AC
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermadappcredential
schema: 2.0.0
ms.openlocfilehash: 5390cf033174f473a08a8407028a709a02677352
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142392172"
---
# Get-AzureRmADAppCredential

## SYNOPSIS
Mengambil daftar kredensial yang terkait dengan aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ApplicationObjectIdParameterSet (Default)
```
Get-AzureRmADAppCredential -ObjectId <Guid> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ApplicationIdParameterSet
```
Get-AzureRmADAppCredential -ApplicationId <Guid> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzureRmADAppCredential -DisplayName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ApplicationObjectParameterSet
```
Get-AzureRmADAppCredential -ApplicationObject <PSADApplication> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzureRmADAppCredential dapat digunakan untuk mengambil daftar kredensial yang terkait dengan aplikasi.
Perintah ini akan mengambil semua properti kredensial (tetapi bukan nilai kredensial) yang terkait dengan aplikasi.

## EXAMPLES

### Contoh 1 - Dapatkan kredensial aplikasi menurut id objek

```
PS C:\> Get-AzureRmADAppCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476
```

Mengembalikan daftar kredensial yang terkait dengan aplikasi yang memiliki id objek '1f99cf81-0146-4f4e-beae-2007d0668476'.

### Contoh 2 - Dapatkan kredensial aplikasi dengan pipa

```
PS C:\> Get-AzureRmADApplication -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476 | Get-AzureRmADAppCredential
```

Mendapatkan aplikasi dengan id objek '1f99cf81-0146-4f4e-beae-2007d0668476' dan menyalurkannya ke cmdlet Get-AzureRmADAppCredential untuk mencantumkan semua kredensial untuk aplikasi itu.

## PARAMETERS

### -ApplicationId
Id aplikasi untuk mengambil kredensial dari.

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

### -ApplicationObject
Objek aplikasi untuk mengambil kredensial dari.

```yaml
Type: Microsoft.Azure.Graph.RBAC.Version1_6.ActiveDirectory.PSADApplication
Parameter Sets: ApplicationObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -ObjectId
Id objek aplikasi untuk mengambil kredensial dari.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

### System.String

### Microsoft.Azure. Graph. RBAC. Version1_6.ActiveDirectory.PSADAplikasi
Parameter: ApplicationObject (ByValue)

## OUTPUTS

### Microsoft.Azure. Graph. RBAC. Version1_6.ActiveDirectory.PSADCredential

## CATATAN

## RELATED LINKS

[AzureRmADAppCredential baru](./New-AzureRmADAppCredential.md)

[Hapus-AzureRmADAppCredential](./Remove-AzureRmADAppCredential.md)

[Get-AzureRmADAplikasi](./Get-AzureRmADApplication.md)

