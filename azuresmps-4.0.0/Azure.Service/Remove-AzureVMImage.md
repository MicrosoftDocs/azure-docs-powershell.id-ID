---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7C9470E5-21D2-4AF5-9F11-F66F94B133C0
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2e381f0b0a4e51e199efd47cedd6e406b4f1d247
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427456"
---
# Remove-AzureVMImage

## SYNOPSIS
Menghapus gambar sistem operasi dari penyimpanan gambar.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVMImage [-ImageName] <String> [-DeleteVHD] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVMImage** menghapus gambar sistem operasi dari penyimpanan gambar.
Secara default, cmdlet ini tidak menghapus blob gambar fisik terkait dari akun penyimpanan.
Untuk menghapus hard drive virtual (VHD) yang terkait, gunakan parameter **DeleteVHD.**

## EXAMPLES

### Contoh 1: Hapus gambar dari penyimpanan gambar
```
PS C:\> Remove-AzureVMImage -ImageName "Image001"
```

Perintah ini akan menghapus gambar yang bernama Image001 dari penyimpanan gambar.

### Contoh 2: Hapus gambar dari penyimpanan gambar dan juga VHD
```
PS C:\> Remove-AzureVMImage -ImageName " Image001" -DeleteVHD
```

Perintah ini akan menghapus gambar yang bernama Image001 dari penyimpanan gambar dan juga menghapus gambar VHD fisik dari akun penyimpanan.

### Contoh 3: Atur konteks langganan, lalu hapus semua gambar
```
PS C:\> $SubsId = &amp;lt;MySubscriptionID&amp;gt;
PS C:\> $Cert = Get-AzureCertificate cert:\LocalMachine\MY\&amp;lt;CertificateThumbprint&amp;gt;
PS C:\> Get-AzureVMImage `
| Where-Object {$_.Label -match "Beta" }`
| Foreach-Object {Remove-AzureVMImage -ImageName $_.name }
```

Perintah ini mengatur konteks langganan lalu menghapus semua gambar dari penyimpanan gambar yang Labelnya menyertakan nama Beta.

## PARAMETERS

### -DeleteVHD
Mengindikasikan bahwa cmdlet ini menghapus blob gambar VHD fisik dari akun penyimpanan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Menentukan sistem operasi atau gambar mesin virtual untuk dihapus dari penyimpanan gambar.

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

[Add-AzureVMImage](./Add-AzureVMImage.md)

[Get-AzureVMImage](./Get-AzureVMImage.md)

[Save-AzureVMImage](./Save-AzureVMImage.md)

[Update-AzureVMImage](./Update-AzureVMImage.md)


