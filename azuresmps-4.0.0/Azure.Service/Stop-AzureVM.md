---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 4F347DD1-907C-47DB-8F1D-636DE031A56A
online version: ''
schema: 2.0.0
ms.openlocfilehash: 23a501811ea4d6a1994631b10b6c837d44dcab61
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653910"
---
# Stop-AzureVM

## SYNOPSIS
Mematikan mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByName (Default)
```
Stop-AzureVM [-Name] <String[]> [-StayProvisioned] [-Force] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Input
```
Stop-AzureVM -VM <IPersistentVM[]> [-StayProvisioned] [-Force] [-ServiceName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureVM** mematikan mesin virtual.

## EXAMPLES

### Contoh 1: Mematikan mesin virtual
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM"
```

Perintah ini mematikan mesin maya yang memuat layanan yang ditentukan.

### Contoh 2: Mematikan mesin virtual menggunakan objek mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01" -Name "MyVM" | Stop-AzureVM
```

Perintah ini mematikan mesin virtual yang dimuat oleh layanan tertentu, dengan menggunakan objek mesin virtual yang dikembalikan **Get-AzureVM** .

### Contoh 3: Matikan VM dan pertahankan VM yang disediakan
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM" -StayProvisioned
```

Perintah ini mematikan mesin virtual yang berisi layanan tertentu, dan mempertahankannya tetap tersedia.

### Contoh 4: Matikan VM dan izinkan deallokasi VM terakhir dalam penyebaran
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM" -Force
```

Perintah ini mematikan mesin virtual yang berisi layanan yang ditentukan dan memungkinkan deallokasi mesin virtual terakhir dalam penyebaran.

### Contoh 5: Mematikan beberapa VM
```
PS C:\> Stop-AzureVM -ServiceName "PSTestService" -Name "*" -Force
```

Perintah ini mematikan beberapa mesin virtual yang memuat layanan yang ditentukan.

## PARAMETERS

### -Paksa
Menentukan apakah akan mengizinkan penawaran mesin virtual terakhir dalam penyebaran.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Nama
Menentukan nama mesin maya untuk dimatikan.

Gunakan karakter wildcard untuk menghentikan beberapa mesin virtual secara asinkron.
Dengan karakter wildcard, cmdlet ini memanggil operasi Peranhttps://msdn.microsoft.com/en-us/library/azure/dn469421.aspx Shutdown (https://msdn.microsoft.com/en-us/library/azure/dn469421.aspx), bukan operasi Peranhttps://msdn.microsoft.com/en-us/library/azure/jj157195.aspx Shutdown (https://msdn.microsoft.com/en-us/library/azure/jj157195.aspx).

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: 

Required: True
Position: 1
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

### -ServiceName
Menentukan nama layanan Azure yang berisi mesin virtual untuk dimatikan.

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

### -StayProvisioned
Menentukan bahwa cmdlet ini menyimpan mesin virtual yang disediakan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual yang mengidentifikasi mesin virtual untuk dimatikan.

```yaml
Type: IPersistentVM[]
Parameter Sets: Input
Aliases: InputObject

Required: True
Position: Named
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

[Get-AzureVM](./Get-AzureVM.md)

[AzureVM baru](./New-AzureVM.md)

[Mulai ulang-AzureVM](./Restart-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)


