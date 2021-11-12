---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 6AC9DA05-756D-4D59-BD97-DBAAFBB3C7AC
online version: https://docs.microsoft.com/en-us/powershell/module/az.resources/get-Azadappcredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzADAppCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Resources/Resources/help/Get-AzADAppCredential.md
ms.openlocfilehash: fc8e454328706243e701c0f4df61733562ab73ce
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426183"
---
# Get-AzADAppCredential

## SYNOPSIS
Mengambil daftar kredensial yang terkait dengan aplikasi.

## SYNTAX

### ApplicationObjectIdParameterSet (Default)
```
Get-AzADAppCredential -ObjectId <Guid> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ApplicationIdParameterSet
```
Get-AzADAppCredential -ApplicationId <Guid> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### DisplayNameParameterSet
```
Get-AzADAppCredential -DisplayName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ApplicationObjectParameterSet
```
Get-AzADAppCredential -ApplicationObject <PSADApplication> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzADAppCredential ini dapat digunakan untuk mengambil daftar kredensial yang terkait dengan aplikasi.
Perintah ini akan mengambil semua properti kredensial (tetapi bukan nilai kredensial) yang terkait dengan aplikasi.

## EXAMPLES

### Contoh 1 - Dapatkan kredensial aplikasi dengan id objek

```
PS C:\> Get-AzADAppCredential -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476
```

Mengembalikan daftar kredensial yang terkait dengan aplikasi yang memiliki id objek '1f99cf81-0146-4f4e-beae-2007d0668476'.

### Contoh 2 - Dapatkan kredensial aplikasi dengan pemipaan

```
PS C:\> Get-AzADApplication -ObjectId 1f99cf81-0146-4f4e-beae-2007d0668476 | Get-AzADAppCredential
```

Dapatkan aplikasi dengan id objek '1f99cf81-0146-4f4e-beae-2007d0668476' dan pipes ke cmdlet Get-AzADAppCredential untuk mencantumkan semua kredensial untuk aplikasi tersebut.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureCredential

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
Id objek aplikasi untuk mengambil kredensial.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.Guid

### System.String

### Microsoft.Azure. Graph. RBAC. Version1_6.ActiveDirectory.FOLDApplication
Parameter: ApplicationObject (ByValue)

## OUTPUTS

### Microsoft.Azure. Graph. RBAC. Version1_6.ActiveDirectory.CREDCredential

## CATATAN

## RELATED LINKS

[New-AzADAppCredential](./New-AzADAppCredential.md)

[Remove-AzADAppCredential](./Remove-AzADAppCredential.md)

[Get-AzADApplication](./Get-AzADApplication.md)

