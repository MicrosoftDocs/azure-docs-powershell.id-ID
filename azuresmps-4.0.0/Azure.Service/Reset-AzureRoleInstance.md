---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2AEA385F-E180-4564-A62A-9E913C665801
online version: ''
schema: 2.0.0
ms.openlocfilehash: 995ea9fd34e19a394c932220cc5fef0e64016b2f
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "132415354"
---
# Reset-AzureRoleInstance

## SYNOPSIS
Meminta reboot atau mengganti satu contoh peran atau semua contoh peran dari peran tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Reset-AzureRoleInstance [-ServiceName] <String> -Slot <String> -InstanceName <String> [-Reboot] [-Reimage]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Reset-AzureRoleInstance** meminta mulai ulang atau mengganti contoh peran yang berjalan dalam penyebaran.
Operasi ini dijalankan secara sinkron.
Saat Memulai ulang instans peran, Azure akan menjalankannya secara offline, memulai ulang sistem operasi yang mendasarinya, dan mengembalikannya secara online.
Setiap data yang ditulis ke disk lokal tetap ada dalam reboot.
Data apa pun yang dalam memori hilang.

Bayangkan contoh peran menghasilkan perilaku yang berbeda bergantung pada tipe peran.
Untuk peran web atau pekerja, ketika peran tersebut diganti, Azure mengambil peran offline dan menulis instalasi baru dari sistem operasi tamu Azure ke mesin virtual.
Peran tersebut kemudian akan kembali online.
Untuk peran VM, ketika peran diganti, Azure mengambil peran secara offline, menerapkan kembali gambar kustom yang Anda berikan untuk peran itu, dan membawa peran kembali online.

Azure berusaha mempertahankan data di setiap sumber daya penyimpanan lokal saat peran tersebut diganti; namun, dalam kasus kegagalan perangkat keras sementara, sumber daya penyimpanan lokal mungkin hilang.
Jika aplikasi Anda mengharuskan data tetap ada, menulis ke sumber data yang tahan lama, seperti drive Azure, disarankan.
Setiap data yang ditulis ke direktori lokal selain yang ditentukan oleh sumber daya penyimpanan lokal akan hilang saat peran diganti.

## EXAMPLES

### Contoh 1: Reboot sebuah contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc01" -Slot "Staging" -InstanceName "MyWebRole_IN_0" -Reboot
```

Perintah ini memulai ulang contoh peran yang MyWebRole_IN_0 dalam penyebaran layanan MySvc01.

### Contoh 2: Mengganti contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc01" -Slot "Staging" -Reimage
```

Perintah ini mengulangi contoh peran dalam pementasan penyebaran layanan awan MySvc01.

### Contoh 3: Mengganti semua contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc1" -Slot "Production" -Reimage
```

Perintah ini akan mengulangi semua contoh peran dalam penggunaan produksi layanan MySvc01.

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

### -InstanceName
Menentukan nama instans peran untuk mengganti atau memulai ulang.

```yaml
Type: String
Parameter Sets: (All)
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

### -Reboot
Menentukan bahwa cmdlet ini memulai ulang instans peran yang ditentukan atau, jika tidak ada yang ditentukan, semua instans peran.
Anda harus menyertakan *parameter Reboot* *atau Reimage* , tapi tidak keduanya.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Reimage
Menentukan bahwa cmdlet ini penggantian contoh peran yang ditentukan atau, jika tidak ada yang ditentukan, semua contoh peran.
Anda harus menyertakan *parameter Reboot* *atau Reimage* , tapi tidak keduanya.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan.

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
Menentukan lingkungan penyebaran di mana contoh peran dijalankan.
Nilai yang valid adalah: Produksi dan Pementasan.
Anda dapat menyertakan parameter *DeploymentName* *atau Slot* , tetapi tidak keduanya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Set-AzureRole](./Set-AzureRole.md)


