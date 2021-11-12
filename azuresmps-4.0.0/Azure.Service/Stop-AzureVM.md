---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 4F347DD1-907C-47DB-8F1D-636DE031A56A
online version: ''
schema: 2.0.0
ms.openlocfilehash: 23a501811ea4d6a1994631b10b6c837d44dcab61
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427409"
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

### Contoh 1: Shut down a virtual machine
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM"
```

Perintah ini mematikan mesin virtual yang berisi layanan tertentu.

### Contoh 2: Mematikan mesin virtual menggunakan objek mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService01" -Name "MyVM" | Stop-AzureVM
```

Perintah ini mematikan mesin virtual yang terdapat dalam layanan tertentu, dengan menggunakan objek mesin virtual yang dikembalikan **Get-AzureVM.**

### Contoh 3: Shut down a VM and keep the VM provisioned
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM" -StayProvisioned
```

Perintah ini mematikan mesin virtual yang ada dalam layanan tertentu, dan mempertahankannya tetap menyediakannya.

### Contoh 4: Shut down a VM and allow deallocation of the last VM in the deployment
```
PS C:\> Stop-AzureVM -ServiceName "ContosoService01" -Name "MyVM" -Force
```

Perintah ini mematikan mesin virtual dalam isi layanan tertentu dan memungkinkan lokasi penawaran mesin virtual terakhir dalam penyebaran.

### Contoh 5: Mematikan beberapa VM
```
PS C:\> Stop-AzureVM -ServiceName "PSTestService" -Name "*" -Force
```

Perintah ini mematikan beberapa mesin virtual yang terdapat di layanan tertentu.

## PARAMETERS

### -Force
Menentukan apakah akan mengizinkan lokasi lokasi mesin virtual terakhir dalam penyebaran.

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
Menentukan nama mesin virtual untuk mematikan.

Gunakan karakter wildcard untuk menghentikan beberapa komputer virtual secara asinkron.
Dengan karakter wildcard, cmdlet ini menyebut operasi Peran Penutupan https://msdn.microsoft.com/en-us/library/azure/dn469421.aspx ( , bukan operasi Peran Penutupan ( https://msdn.microsoft.com/en-us/library/azure/dn469421.aspx) https://msdn.microsoft.com/en-us/library/azure/jj157195.aspx https://msdn.microsoft.com/en-us/library/azure/jj157195.aspx) .

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
Menentukan nama layanan Azure yang berisi mesin virtual untuk mematikan.

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
Menentukan bahwa cmdlet ini mempertahankan mesin virtual yang disediakan.

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
Menentukan objek mesin virtual yang mengidentifikasi mesin virtual untuk mematikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVM](./Get-AzureVM.md)

[New-AzureVM](./New-AzureVM.md)

[Mulai Ulang-AzureVM](./Restart-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)


