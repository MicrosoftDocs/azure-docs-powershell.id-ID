---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: BBA0D5D3-29A5-4E00-9075-702E2F81CA52
online version: ''
schema: 2.0.0
ms.openlocfilehash: 79a03d4a689ca483666e82d17cfcf024629278f6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421565"
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

### GetvmByServiceAndvMName
```
Get-AzureVM [-ServiceName] <String> [[-Name] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVM** mengambil informasi tentang mesin virtual yang berjalan di Azure.
Fungsi ini akan mengembalikan objek dengan informasi pada komputer virtual tertentu, atau jika tidak ada mesin virtual yang ditentukan, untuk semua mesin virtual dalam layanan tertentu dari langganan saat ini.

## EXAMPLES

### Contoh 1: Mengambil informasi di komputer virtual yang ditentukan
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01" -Name "VirtualMachine02"
```

Perintah ini mengembalikan objek dengan informasi di mesin virtual VirtualMachine02 yang berjalan di layanan awan ContosoService01.

### Contoh 2: Mengambil informasi pada semua mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01"
```

Perintah ini mengambil objek daftar dengan informasi di semua komputer virtual yang berjalan di layanan awan ContosoService01.

### Contoh 3: Menampilkan tabel status mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01"  | Format-Table AutoSize -Property "Name",@{Expression={$_.InstanceUpgradeDomain};Label="UpgDom";Align="Right"},"InstanceStatus"
```

Perintah ini menampilkan tabel yang memperlihatkan komputer virtual yang berjalan di layanan ContosoService01, Domain Pemutakhiran, dan status terkini setiap komputer virtual.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

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
Jika parameter ini tidak tersedia, cmdlet akan mengembalikan objek daftar dengan informasi tentang semua mesin virtual di layanan yang ditentukan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-AzureVM](./New-AzureVM.md)

[New-AzureVMConfig](./New-AzureVMConfig.md)

[Remove-AzureVM](./Remove-AzureVM.md)

[Mulai Ulang-AzureVM](./Restart-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)

[Stop-AzureVM](./Stop-AzureVM.md)

[Update-AzureVM](./Update-AzureVM.md)


