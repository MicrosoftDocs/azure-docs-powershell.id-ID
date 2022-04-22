---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7C50472E-CE36-4BF1-92C9-A3B9B183ACD1
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2ae2a1a141ac3bd7dd149b2496728f450920c25f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043902"
---
# Get-AzureRole

## SYNOPSIS
Mengembalikan daftar peran dalam layanan Microsoft Azure Anda.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRole [-ServiceName] <String> [[-Slot] <String>] [[-RoleName] <String>] [-InstanceDetails]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRole** mengembalikan objek daftar dengan detail peran dalam layanan Microsoft Azure Anda.
Jika Anda menentukan parameter *RoleName* , **Get-AzureRole** hanya mengembalikan detail peran tersebut.
Jika Anda menentukan parameter *InstanceDetails* , detail tambahan khusus instans akan dikembalikan.

## EXAMPLES

### Contoh 1: Dapatkan daftar peran untuk layanan
```
PS C:\> Get-AzureRole -ServiceName "MySvc01" -Slot "Production"
```

Perintah ini mengembalikan objek dengan detail tentang semua peran produksi yang berjalan di layanan MySvc01.

### Contoh 2: Dapatkan detail tentang peran yang berjalan di layanan
```
PS C:\> Get-AzureRole -ServiceName "MySvc1" -Slot "Staging" -RoleName "MyTestVM3"
```

Perintah ini mengembalikan objek dengan detail tentang peran MyTestVM3, berjalan pada lingkungan pementasan layanan MySvc01.

### Contoh 3: Dapatkan informasi instans tentang contoh peran yang berjalan di layanan
```
PS C:\> Get-AzureRole -ServiceName "MySvc01" -Slot "Production" -RoleName "MyTestVM02" -InstanceDetails
```

Perintah ini mengembalikan objek dengan detail tentang contoh peran MyTestVM02 yang berjalan dalam lingkungan produksi pada layanan MySvc01.

### Contoh 4: Mendapatkan tabel contoh peran yang terkait dengan layanan
```
PS C:\> Get-AzureRole -ServiceName "MySvc01" -Slot "Production" -InstanceDetails | Format-Table -Auto "InstanceName", "InstanceSize", "InstanceStatus"
```

Perintah ini mengembalikan tabel nama instans, ukuran, dan status semua instans peran yang berjalan di lingkungan produksi pada layanan MySvc01.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceDetails
Menentukan bahwa cmdlet ini mengembalikan detail tentang instans pada setiap peran.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

### -RoleName
Menentukan nama peran yang akan didapatkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan lingkungan penyebaran Azure.
Nilai yang dapat diterima untuk parameter ini adalah: Produksi atau Staging.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureRole](./Set-AzureRole.md)


