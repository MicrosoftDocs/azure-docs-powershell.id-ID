---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 2021B6BC-7B59-4A88-B1DF-598203F58901
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9c2c3d833a3735b51dd55fc314e614881f2a7814
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141920706"
---
# New-AzureRemoteAppCollection

## SYNOPSIS
Membuat koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### AllParameterSets (Default)
```
New-AzureRemoteAppCollection [-CollectionName] <String> [-ImageName] <String> [-Plan] <String>
 [[-Location] <String>] [-Description <String>] [-CustomRdpProperty <String>] [-ResourceType <CollectionMode>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### AzureVNet
```
New-AzureRemoteAppCollection [-CollectionName] <String> [-ImageName] <String> [-Plan] <String>
 [[-Location] <String>] [-VNetName] <String> [-SubnetName] <String> [-DnsServers <String>] [[-Domain] <String>]
 [[-Credential] <PSCredential>] [-OrganizationalUnit <String>] [-Description <String>]
 [-CustomRdpProperty <String>] [-ResourceType <CollectionMode>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRemoteAppCollection** membuat koleksi Azure RemoteApp.

## EXAMPLES

### Contoh 1: Membuat koleksi
```
PS C:\> New-AzureRemoteAppCollection -CollectionName "Contoso" -ImageName "Windows Server 2012 R2" -Plan Standard -Location "West US" -Description CloudOnly
```

Perintah ini membuat kumpulan Azure RemoteApp.

### Contoh 2: Membuat koleksi menggunakan kredensial
```
PS C:\> $cred = Get-Credential corp.contoso.com\admin
PS C:\> New-AzureRemoteAppCollection -CollectionName "ContosoHybrid" -ImageName "Windows Server 2012 R2" -Plan Standard -VNetName azureVNet -Domain Contoso.com -Credential $cred -Description Hybrid
```

Perintah ini membuat kumpulan Azure RemoteApp menggunakan kredensial dari cmdlet **Get-Credential** .

## PARAMETERS

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

### -Kredensial
Menentukan kredensial akun layanan yang memiliki izin untuk bergabung dengan server Azure RemoteApp ke domain Anda.
Untuk mendapatkan objek **PSCredential** , gunakan cmdlet **Get-Credential** .

```yaml
Type: PSCredential
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomRdpProperty
Menentukan properti Protokal Desktop Jauh (RDP) kustom yang dapat digunakan untuk mengonfigurasi pengalihan drive dan pengaturan lainnya.
Lihat [Pengaturan RDP untuk Layanan Desktop Jarak Jauh di Server](https://technet.microsoft.com/library/ff393699(v=ws.10).aspx)`(https://technet.microsoft.com/library/ff393699(v=ws.10).aspx)` Windows untuk detailnya.  

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

### -Deskripsi
Menentukan deskripsi singkat untuk objek.

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

### -DnsServers
Menentukan daftar alamat IPv4 server DNS yang dipisahkan koma.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domain
Menentukan nama domain Active Directory Domain Services tempat untuk bergabung dalam server Host Sesi RD.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageName
Menentukan nama gambar templat Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan kawasan Azure koleksi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrganizationalUnit
Menentukan nama unit organisasi (OU) tempat untuk bergabung dalam server Host Sesi RD, misalnya, OU=MyOu,DC=MyDomain,DC=ParentDomain,DC=com.
Atribut seperti OU dan DC harus dalam huruf besar.
OU tidak dapat diubah setelah koleksi dibuat.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rencana
Menentukan rencana untuk kumpulan Azure RemoteApp, yang dapat menentukan batas penggunaan.
Gunakan **Get-AzureRemoteAppPlan** untuk melihat paket yang tersedia.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ResourceType
Menentukan tipe sumber daya kumpulan.
Nilai yang dapat diterima untuk parameter ini adalah: Aplikasi atau Desktop.

```yaml
Type: CollectionMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetName
Menentukan nama subnet di jaringan virtual untuk digunakan untuk membuat kumpulan Azure RemoteApp.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VNetName
Menentukan nama jaringan virtual Azure RemoteApp.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: True
Position: 4
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

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[Get-AzureRemoteAppPlan](./Get-AzureRemoteAppPlan.md)

[Hapus-AzureRemoteAppCollection](./Remove-AzureRemoteAppCollection.md)

[Set-AzureRemoteAppCollection](./Set-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


