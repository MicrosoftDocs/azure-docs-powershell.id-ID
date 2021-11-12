---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: E54E4D16-DB2A-4626-B543-773C187B2E08
online version: ''
schema: 2.0.0
ms.openlocfilehash: 64489e3fef338c58c7b7a6e4f4f75e68b8da9524
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423189"
---
# Set-AzureStaticVNetIP

## SYNOPSIS
Mengatur informasi alamat IP VNet statis untuk objek mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureStaticVNetIP [-IPAddress] <String> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureStaticVNetIP** mengatur informasi alamat IP jaringan virtual statis (VNet) untuk objek mesin virtual.

## EXAMPLES

### Contoh 1: Menyetel alamat IP jaringan virtual yang terkait dengan mesin virtual
```
PS C:\> # Prerequisite: VNet has been set up with SubNet
          # Set-AzureVNetConfig -ConfigurationPath $vnetConfigPath;

          $vm = New-AzureVMConfig -Name $vmname -ImageName $img -InstanceSize $sz | Add-AzureProvisioningConfig -Windows -Password $pwd -AdminUsername $usr;
          $vm = Set-AzureSubNet -VM $vm -SubNetNames $sn;
          Set-AzureStaticVNetIP -IPAddress $ip -VM $vm;
          New-AzureVM -ServiceName $svc -VMs $vm -VNetName $vnetName -Location $loc;
```

Perintah pertama mengatur jalur konfigurasi untuk jaringan virtual.

Perintah kedua akan membuat konfigurasi mesin virtual.

Perintah ketiga mengatur subnet untuk komputer virtual.

Perintah keempat mengatur alamat IP untuk komputer virtual.

Perintah kelima membuat mesin virtual menggunakan mesin virtual.

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

### -IPAddress
Menentukan alamat IP VNet statis

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### -VM
Menentukan objek mesin virtual tetap yang untuk menyetel alamat IP VNet statis.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureStaticVNetIP](./Get-AzureStaticVNetIP.md)

[Test-AzureStaticVNetIP](./Test-AzureStaticVNetIP.md)


