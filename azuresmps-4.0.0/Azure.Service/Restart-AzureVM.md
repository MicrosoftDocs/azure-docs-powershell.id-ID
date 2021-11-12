---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 596B8A6F-D3C2-4170-BCD7-B7A1CDB656D8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 36520cac5ec0fba3760787e675ea9855d00cd901
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422047"
---
# Restart-AzureVM

## SYNOPSIS
Memulai ulang mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### RestartByName (Default)
```
Restart-AzureVM [-Name] <String> [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RedeployByName
```
Restart-AzureVM [-Name] <String> [-Redeploy] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### InitiateMaintenanceByName
```
Restart-AzureVM [-Name] <String> [-InitiateMaintenance] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Mulai UlangInput
```
Restart-AzureVM -VM <PersistentVM> [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### RedeployInput
```
Restart-AzureVM -VM <PersistentVM> [-Redeploy] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### InitiateMaintenanceInput
```
Restart-AzureVM -VM <PersistentVM> [-InitiateMaintenance] [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Mulai Ulang-AzureVM** meminta mulai ulang komputer virtual Azure.

## EXAMPLES

### Contoh 1: Hidupkan ulang mesin virtual
```
PS C:\> Restart-AzureVM -ServiceName "MyService01" -Name "MyVM"
```

Perintah ini memulai ulang mesin virtual VirtualMachine27 yang berjalan di layanan Azure yang bernama Service01.

### Contoh 2: Mulai ulang mesin virtual dengan menggunakan objek mesin virtual
```
PS C:\> Get-AzureVM -ServiceName "MyService01" -Name "VirtualMachine27" | Restart-AzureVM
```

Perintah ini mengambil objek mesin virtual untuk komputer virtual bernama MyVM, lalu memulai ulang.

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

### -InitiateMaintenance
Memulai Pemeliharaan di Komputer Virtual

```yaml
Type: SwitchParameter
Parameter Sets: InitiateMaintenanceByName, InitiateMaintenanceInput
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama komputer virtual untuk memulai ulang.

```yaml
Type: String
Parameter Sets: RestartByName, RedeployByName, InitiateMaintenanceByName
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

### -Redeploy
Menunjukkan bahwa cmdlet akan menjelaskan kembali mesin virtual tersebut.

```yaml
Type: SwitchParameter
Parameter Sets: RedeployByName, RedeployInput
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan Azure yang berisi mesin virtual untuk dimulai ulang.

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

### -VM
Menentukan objek mesin virtual yang mengidentifikasi komputer virtual untuk memulai ulang.

```yaml
Type: PersistentVM
Parameter Sets: RestartInput, RedeployInput, InitiateMaintenanceInput
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVM](./Get-AzureVM.md)

[Remove-AzureVM](./Remove-AzureVM.md)

[Start-AzureVM](./Start-AzureVM.md)

[Stop-AzureVM](./Stop-AzureVM.md)

[Update-AzureVM](./Update-AzureVM.md)


