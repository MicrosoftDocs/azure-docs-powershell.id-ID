---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2CBF8DEF-954C-4D9F-B495-C2F76550BC79
online version: ''
schema: 2.0.0
ms.openlocfilehash: 58929cd88749c2388a55d6c38f436d7a3e8bc74b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981469"
---
# Get-AzureRoleSize

## SYNOPSIS
Mendapatkan informasi ukuran peran untuk langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRoleSize [[-InstanceSize] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRoleSize** mendapatkan informasi ukuran peran untuk langganan saat ini.

## EXAMPLES

### Contoh 1: Dapatkan informasi ukuran peran
```
PS C:\> Get-AzureRoleSize

          InstanceSize               : A6
          RoleSizeLabel              :
          Cores                      : 4
          MemoryInMb                 : 28672
          SupportedByWebWorkerRoles  : True
          SupportedByVirtualMachines : True
          OperationDescription       : Get-AzureRoleSize
          OperationId                : c5ed7b3a-03b3-548d-876b-6688c5b29cce
          OperationStatus            : Succeeded

          InstanceSize               : A7
          RoleSizeLabel              :
          Cores                      : 8
          MemoryInMb                 : 57344
          SupportedByWebWorkerRoles  : True
          SupportedByVirtualMachines : True
          OperationDescription       : Get-AzureRoleSize
          OperationId                : c5ed7b3a-03b3-548d-876b-6688c5b29cce
          OperationStatus            : Succeeded
```

Perintah ini mendapatkan informasi ukuran peran untuk langganan saat ini.

### Contoh 2: Dapatkan informasi ukuran peran dan tentukan nama ukuran peran
```
PS C:\> Get-AzureRoleSize -InstanceSize A7

          InstanceSize               : A7
          RoleSizeLabel              :
          Cores                      : 8
          MemoryInMb                 : 57344
          SupportedByWebWorkerRoles  : True
          SupportedByVirtualMachines : True
          OperationDescription       : Get-AzureRoleSize
          OperationId                : c5ed7b3a-03b3-548d-876b-6688c5b29cce
          OperationStatus            : Succeeded
```

Perintah ini mendapatkan informasi ukuran peran untuk ukuran peran yang ditentukan.

### Contoh 3: Dapatkan informasi ukuran peran untuk semua mesin virtual di semua layanan Azure
```
PS C:\> Get-AzureService | Get-AzureVM | Get-AzureRoleSize
```

Perintah ini mendapatkan informasi ukuran peran untuk semua mesin virtual di semua layanan Azure.

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

### -Instancesize
Menentukan nama ukuran peran, misalnya: ExtraSmall, Small, Large, ExtraLarge, A5, A6, A7.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRole](./Get-AzureRole.md)

[Get-AzureService](./Get-AzureService.md)

[Get-AzureVM](./Get-AzureVM.md)


