---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 4136A0EF-2682-4B17-BC37-53CD43F5940B
online version: ''
schema: 2.0.0
ms.openlocfilehash: 28b61b5d7b690a7c96eeea689c863e968c885e4f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141966369"
---
# Get-AzureRemoteAppOperationResult

## SYNOPSIS
Mengambil hasil operasi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppOperationResult [-TrackingId] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppOperationResult** mengambil hasil operasi Azure RemoteApp yang berjalan lama.
Azure RemoteApp menggunakan operasi yang berjalan lama untuk banyak tindakan yang memerlukan pemrosesan oleh layanan dan tidak dapat langsung kembali.
Contoh cmdlet yang mengembalikan ID pelacakan termasuk **Update-AzureRemoteAppCollection**, **Set-AzureRemoteAppWorkspace**, **Disconnect-AzureRemoteAppSession**, dan lainnya.

## EXAMPLES

### Contoh 1: Menggunakan ID pelacakan untuk mendapatkan hasil operasi
```
PS C:\> $result = New-AzureRemoteAppCollection -CollectionName Contoso -ImageName "Windows Server 2012 R2" -Plan Standard -Location "West US" -Description CloudOnly
PS C:\> Get-AzureRemoteAppOperationResult -TrackingId $result.Tracking
```

Perintah ini menyimpan ID pelacakan yang dikembalikan dari operasi Azure RemoteApp.
ID pelacakan dialihkan ke **Get-AzureRemoteAppOperationResult** dalam perintah berikut.

## PARAMETERS

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -TrackingId
Menentukan ID pelacakan operasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Putuskan sambungan-AzureRemoteAppSession](./Disconnect-AzureRemoteAppSession.md)

[Set-AzureRemoteAppWorkspace](./Set-AzureRemoteAppWorkspace.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


