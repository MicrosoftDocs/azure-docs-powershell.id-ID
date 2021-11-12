---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 14B4050D-3597-4760-A152-82617B88078D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9c7704a7718bf142fdaf614efb5e8c90b06422b6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427436"
---
# Set-AzureRemoteAppCollection

## SYNOPSIS
Mengatur properti koleksi RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### DeskripsiSonly (Default)
```
Set-AzureRemoteAppCollection [-CollectionName] <String> -Description <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### PlanOnly
```
Set-AzureRemoteAppCollection [-CollectionName] <String> -Plan <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### DomainJoined
```
Set-AzureRemoteAppCollection [-CollectionName] <String> -Credential <PSCredential> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### RdpPropertyOnly
```
Set-AzureRemoteAppCollection [-CollectionName] <String> -CustomRdpProperty <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### AclLevelOnly
```
Set-AzureRemoteAppCollection [-CollectionName] <String> -AclLevel <CollectionAclLevel>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRemoteAppCollection** mengatur properti kumpulan Azure RemoteApp.

## EXAMPLES

## PARAMETERS

### -AclLevel
Menentukan tingkat daftar kontrol akses (ACL, Access Control List) untuk kumpulan.
Nilai yang dapat diterima untuk parameter ini adalah: Kumpulan dan Aplikasi.

```yaml
Type: CollectionAclLevel
Parameter Sets: AclLevelOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Menentukan kredensial akun layanan yang memiliki izin untuk bergabung dengan server Azure RemoteApp ke domain Anda.
Untuk mendapatkan objek **PSCredential,** gunakan cmdlet **Get-Credential.**

```yaml
Type: PSCredential
Parameter Sets: DomainJoined
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomRdpProperty
Menentukan properti custom Remote Desktop Protocol (RDP) yang bisa digunakan untuk mengonfigurasi pengalihan drive dan pengaturan lain. Lihat [RdP Pengaturan untuk Layanan Desktop Jarak Jauh di Windows Server](https://technet.microsoft.com/library/ff393699(v=ws.10).aspx) untuk `(https://technet.microsoft.com/library/ff393699(v=ws.10).aspx)` detailnya.  

```yaml
Type: String
Parameter Sets: RdpPropertyOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Deskripsi
Menentukan deskripsi singkat untuk koleksi.

```yaml
Type: String
Parameter Sets: DescriptionOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rencana
Menentukan paket untuk koleksi Azure RemoteApp, yang menentukan batas penggunaan.
Gunakan **Get-AzureRemoteAppPlan** untuk melihat paket yang tersedia.

```yaml
Type: String
Parameter Sets: PlanOnly
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[New-AzureRemoteAppCollection](./New-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


