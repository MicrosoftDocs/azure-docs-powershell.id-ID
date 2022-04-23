---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: BBA0D5D3-29A5-4E00-9075-702E2F81CA52
online version: ''
schema: 2.0.0
ms.openlocfilehash: 79a03d4a689ca483666e82d17cfcf024629278f6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104751"
---
# Get-AzureVM

## SYNOPSIS
Mengambil informasi dari satu atau beberapa mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ListAllVMs (Default)
```
Get-AzureVM [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### GetVMByServiceAndVMName
```
Get-AzureVM [-ServiceName] <String> [[-Name] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVM** mengambil informasi tentang mesin virtual yang berjalan di Azure.
Ini mengembalikan objek dengan informasi di mesin virtual tertentu, atau jika tidak ada mesin virtual yang ditentukan, untuk semua mesin virtual dalam layanan tertentu dari langganan saat ini.

## EXAMPLES

### Contoh 1: Mengambil informasi di mesin virtual tertentu
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01" -Name "VirtualMachine02"
```

Perintah ini mengembalikan objek dengan informasi di mesin virtual VirtualMachine02 yang berjalan di layanan cloud ContosoService01.

### Contoh 2: Mengambil informasi di semua mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01"
```

Perintah ini mengambil objek daftar dengan informasi tentang semua mesin virtual yang berjalan di layanan awan ContosoService01.

### Contoh 3: Menampilkan tabel status mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01"  | Format-Table AutoSize -Property "Name",@{Expression={$_.InstanceUpgradeDomain};Label="UpgDom";Align="Right"},"InstanceStatus"
```

Perintah ini menampilkan tabel yang memperlihatkan mesin virtual yang berjalan pada layanan ContosoService01, Domain Pemutakhiran, dan status saat ini dari setiap mesin virtual.

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

### -Nama
Menentukan nama mesin virtual untuk mengambil informasi.
Jika parameter ini tidak disediakan, cmdlet mengembalikan objek daftar dengan informasi tentang semua mesin virtual dalam layanan yang ditentukan.

```yaml
Type: String
Parameter Sets: GetVMByServiceAndVMName
Aliases: 

Required: False
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
Menentukan nama layanan awan untuk mengembalikan informasi mesin virtual.

```yaml
Type: String
Parameter Sets: GetVMByServiceAndVMName
Aliases: 

Required: True
Position: 0
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

[AzureVM baru](./New-AzureVM.md)

[AzureVMConfig baru](./New-AzureVMConfig.md)

[Hapus-AzureVM](./Remove-AzureVM.md)

[Mulai ulang-AzureVM](./Restart-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)

[Stop-AzureVM](./Stop-AzureVM.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


