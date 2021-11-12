---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 649D0A6C-77CE-4E49-AFF8-DF70ABE9FA13
online version: ''
schema: 2.0.0
ms.openlocfilehash: d1f186a2799cad592eabb88a94d39fcacead94f3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423178"
---
# Set-AzureVMDscExtension

## SYNOPSIS
Mengonfigurasi ekstensi DSC di komputer virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVMDscExtension [-ReferenceName <String>] [-ConfigurationArgument <Hashtable>]
 [-ConfigurationDataPath <String>] [-ConfigurationArchive] <String> [-ConfigurationName <String>]
 [-ContainerName <String>] [-Force] [-StorageContext <AzureStorageContext>] [-Version <String>]
 [-StorageEndpointSuffix <String>] [-WmfVersion <String>] [-DataCollection <String>] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVMDscExtension** mengonfigurasi ekstensi Desired State Configuration (DSC) pada komputer virtual.

## EXAMPLES

### Contoh 1: Konfigurasi ekstensi DSC di komputer virtual
```
PS C:\> Set-AzureVMDscExtension -VM $VM -ConfigurationArchive MyConfiguration.ps1.zip  -ConfigurationName MyConfiguration -ConfigurationArgument @{ Path = 'C:\MyDirectory' }
DeploymentName              : my-vm-svc
Name                        : my-vm
Label                       :
VM                          : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVM
InstanceStatus              : ReadyRole
IpAddress                   : 10.10.10.10
InstanceStateDetails        :
PowerState                  : Started
InstanceErrorCode           :
InstanceFaultDomain         : 0
InstanceName                : my-vm
InstanceUpgradeDomain       : 0
InstanceSize                : Small
AvailabilitySetName         :
DNSName                     : http://my-vm-svc.cloudapp.net/
Status                      : ReadyRole
GuestAgentStatus            : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVMModel.GuestAgentStatus
ResourceExtensionStatusList : {Contoso.Compute.BGInfo}
PublicIPAddress             :
PublicIPName                :
ServiceName                 : my-vm-svc
OperationDescription        : Get-AzureVM
OperationId                 : a0217a7af900c1f8a212299a3333cdbd6
OperationStatus             : OK
```

Perintah ini mengonfigurasi ekstensi DSC di komputer virtual.

Paket MyConfiguration.ps1.zip tersebut harus telah diunggah sebelumnya ke penyimpanan Azure menggunakan perintah **Publish-AzureVMDscConfiguration** dan menyertakan skrip MyConfiguration.ps1 dan modul yang bergantung padanya.

Argumen MyConfiguration menunjukkan konfigurasi DSC tertentu dalam skrip untuk dijalankan.
Parameter *- KonfigurasiParameter* menentukan hashtable dengan argumen yang disampaikan ke fungsi konfigurasi.

### Contoh 2: Mengonfigurasi ekstensi DSC di komputer virtual menggunakan jalur ke data konfigurasi
```
PS C:\> $VM | Set-AzureVMDscExtension -ConfigurationArchive MyConfiguration.ps1.zip  -ConfigurationName MyConfiguration -ConfigurationArgument @{ Credential = Get-Credential } -ConfigurationDataPath MyConfigurationData.psd1
DeploymentName              : my-vm-svc
Name                        : my-vm
Label                       :
VM                          : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVM
InstanceStatus              : ReadyRole
IpAddress                   : 10.10.10.10
InstanceStateDetails        :
PowerState                  : Started
InstanceErrorCode           :
InstanceFaultDomain         : 0
InstanceName                : my-vm
InstanceUpgradeDomain       : 0
InstanceSize                : Small
AvailabilitySetName         :
DNSName                     : http://my-vm-svc.cloudapp.net/
Status                      : ReadyRole
GuestAgentStatus            : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVMModel.GuestAgentStatus
ResourceExtensionStatusList : {Microsoft.Compute.BGInfo, Microsoft.Powershell.DSC}
PublicIPAddress             :
PublicIPName                :
ServiceName                 : my-vm-svc
OperationDescription        : Get-AzureVM
OperationId                 : a0217a7af900c1f8a212299a3333cdbd7
OperationStatus             : OK
```

Perintah ini mengonfigurasi ekstensi DSC di komputer virtual menggunakan jalur ke data konfigurasi.

## PARAMETERS

### -ConfigurationArchive
Menentukan nama paket konfigurasi (file .zip) yang sebelumnya diunggah oleh Publish-AzureVMDscConfiguration.
Parameter ini harus menentukan nama file saja, tanpa jalur apa pun.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationA argumentment
Menentukan tabel hash yang menentukan argumen untuk fungsi konfigurasi.
Kunci terkait dengan nama parameter dan nilai untuk nilai parameter.

Nilai yang dapat diterima untuk parameter ini adalah:

- tipe primitif
- string
- larik
- PSCredential

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationDataPath
Menentukan jalur file .psd1 yang menentukan data untuk fungsi konfigurasi.
File ini harus berisi hashtable seperti yang diuraikan dalam Memisahkan Konfigurasi dan Data https://msdn.microsoft.com/en-us/PowerShell/DSC/configData Lingkungan.

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

### -ConfigurationName
Menentukan nama skrip konfigurasi atau modul yang diminta oleh ekstensi DSC.

Nilai parameter ini harus nama salah satu fungsi konfigurasi yang terdapat dalam skrip atau modul yang di packaged in *ConfigurationArchive*.

Cmdlet ini akan menggunakan nama file yang diberikan oleh parameter *ConfigurationArchive* jika Anda menghilangkan parameter ini, tidak termasuk ekstensi apa pun.
Misalnya, jika *ConfigurationArchive adalah* "SalesWebSite.ps1.zip", nilai default untuk *ConfigurationName adalah* "SalesWebSite".

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

### -ContainerName
Menentukan nama wadah penyimpanan Azure tempat *ConfigurationArchive* berada.

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

### -DataCollection
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

### -Force
Mengindikasikan bahwa cmdlet ini menimpa blob yang sudah ada.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -ReferenceName
Menentukan string yang ditentukan pengguna yang bisa digunakan untuk merujuk ke ekstensi.
Parameter ini ditentukan saat ekstensi ditambahkan ke mesin virtual untuk pertama kalinya.
Untuk pembaruan berikutnya, Anda harus menentukan nama referensi yang digunakan sebelumnya saat memperbarui ekstensi.
*NamaReferensi* yang ditetapkan untuk ekstensi dikembalikan menggunakan cmdlet **Get-AzureVM.**

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

### -StorageContext
Menentukan konteks penyimpanan Azure yang menyediakan pengaturan keamanan yang digunakan untuk mengakses skrip konfigurasi.
Konteks ini menyediakan akses baca ke wadah yang ditentukan oleh parameter *ContainerName.*

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEndpointFix
Menentukan akhiran titik akhir DNS untuk semua layanan penyimpanan, misalnya, "core.contoso.net".

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

### -Versi
Menentukan versi ekstensi DSC tertentu yang akan digunakan.
Nilai default diatur ke "1.*" jika parameter ini tidak ditentukan.

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

### -VM
Menentukan objek mesin virtual persisten.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WmfVersion
Menentukan versi instalan Windows Management Framework (WMF) di komputer virtual.
Ekstensi DSC bergantung pada fitur DSC yang hanya tersedia di pembaruan WMF.
Parameter ini menentukan versi pembaruan untuk diinstal di komputer virtual.
Nilai yang dapat diterima untuk parameter ini adalah:

- 4.0.
Menginstal WMF 4.0 kecuali versi yang lebih baru telah diinstal.
- 5.0.
Menginstal rilis terbaru WMF 5.0.
- terbaru.
Menginstal WMF terbaru, saat ini WMF 5.0.

Nilai default adalah yang terbaru.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVMDscExtension](./Get-AzureVMDscExtension.md)

[Remove-AzureVMDscExtension](./Remove-AzureVMDscExtension.md)

[Remove-AzureVMDscExtension](./Remove-AzureVMDscExtension.md)

[Get-AzureVM](./Get-AzureVM.md)

[Publish-AzureVMDscConfiguration](./Publish-AzureVMDscConfiguration.md)


