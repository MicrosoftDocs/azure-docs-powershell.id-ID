---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2AEA385F-E180-4564-A62A-9E913C665801
online version: ''
schema: 2.0.0
ms.openlocfilehash: 995ea9fd34e19a394c932220cc5fef0e64016b2f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142381859"
---
# Reset-AzureRoleInstance

## SYNOPSIS
Meminta boot ulang atau reimage contoh peran tunggal atau semua contoh peran dari peran tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Reset-AzureRoleInstance [-ServiceName] <String> -Slot <String> -InstanceName <String> [-Reboot] [-Reimage]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Reset-AzureRoleInstance** meminta boot ulang atau penggantian instans peran yang berjalan dalam penyebaran.
Operasi ini dijalankan secara sinkron.
Saat Anda memulai ulang contoh peran, Azure mengambil instans offline, memulai ulang sistem operasi yang mendasar untuk contoh tersebut, dan menghadirkan instans kembali online.
Data apa pun yang ditulis ke disk lokal tetap ada di seluruh boot ulang.
Data apa pun yang ada dalam memori hilang.

Mengoptimalkan contoh peran menghasilkan perilaku yang berbeda tergantung pada tipe peran.
Untuk peran web atau pekerja, ketika peran direimage, Azure mengambil peran offline dan menulis instalasi baru sistem operasi tamu Azure ke mesin virtual.
Peran tersebut kemudian dibawa kembali secara online.
Untuk peran VM, ketika peran direimage, Azure mengambil peran offline, menerapkan kembali gambar kustom yang Anda sediakan untuknya, dan membawa peran kembali online.

Azure berusaha mempertahankan data di sumber daya penyimpanan lokal apa pun saat peran direimage; namun, jika terjadi kegagalan perangkat keras sementara, sumber daya penyimpanan lokal mungkin hilang.
Jika aplikasi Anda mengharuskan data tetap ada, disarankan menulis ke sumber data yang tahan lama, seperti drive Azure.
Setiap data yang ditulis ke direktori lokal selain yang ditentukan oleh sumber daya penyimpanan lokal akan hilang ketika peran direimaged.

## EXAMPLES

### Contoh 1: Boot ulang sebuah contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc01" -Slot "Staging" -InstanceName "MyWebRole_IN_0" -Reboot
```

Perintah ini me-boot ulang instans peran bernama MyWebRole_IN_0 dalam penyebaran pementasan layanan MySvc01.

### Contoh 2: Menginisiasi ulang contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc01" -Slot "Staging" -Reimage
```

Perintah ini mengoptimalkan contoh peran dalam penyebaran pementasan layanan cloud MySvc01.

### Contoh 3: Mengoptimalkan ulang semua contoh peran
```
PS C:\> ReSet-AzureRoleInstance -ServiceName "MySvc1" -Slot "Production" -Reimage
```

Perintah ini mereimages semua contoh peran dalam penyebaran produksi layanan MySvc01.

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

### -InstanceName
Menentukan nama instans peran untuk direimasi atau boot ulang.

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

### -Boot ulang
Menentukan bahwa cmdlet ini melakukan boot ulang instans peran yang ditentukan atau, jika tidak ada yang ditentukan, semua contoh peran.
Anda harus menyertakan parameter *Reboot* atau *Reimage* , tetapi tidak keduanya.

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
Menentukan bahwa cmdlet ini mereimage contoh peran yang ditentukan atau, jika tidak ada yang ditentukan, semua contoh peran.
Anda harus menyertakan parameter *Reboot* atau *Reimage* , tetapi tidak keduanya.

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
Menentukan lingkungan penyebaran tempat contoh peran berjalan.
Nilai yang valid adalah: Produksi dan Pementasan.
Anda dapat menyertakan parameter *DeploymentName* atau *Slot* , tetapi tidak keduanya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Set-AzureRole](./Set-AzureRole.md)


