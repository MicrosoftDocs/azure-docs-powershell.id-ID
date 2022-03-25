---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: C92B4B70-4342-4219-80D3-FB79BDC171A3
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7e9d40468283ae0d5f695982679b344c5721b719
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414760"
---
# Set-AzureAutomationCredential

## SYNOPSIS

Mengubah kredensial dalam Otomatisasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureAutomationCredential -Name <String> [-Description <String>] [-Value <PSCredential>]
 -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Set-AzureAutomationCredential** memodifikasi kredensial sebagai objek **PSCredential** dalam Microsoft Azure Automation.

## EXAMPLES

### Contoh 1: Memperbarui kredensial
```
PS C:\> $user = "MyDomain\MyUser"
PS C:\> $pw = ConvertTo-SecureString "PassWord!" -AsPlainText -Force
PS C:\> $cred = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $user, $pw
PS C:\> New-AzureAutomationCredential -AutomationAccountName "Contos17" -Name "MyCredential" -Value $cred
```

Perintah ini memperbarui kredensial yang sudah ada bernama MyCredential.
Objek kredensial pertama kali dibuat yang menyertakan nama pengguna dan kata sandi.
Lalu ini akan digunakan dalam perintah terakhir untuk memperbarui kredensial otomatisasi.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi dengan kredensial.

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

### -Deskripsi
Menentukan deskripsi untuk kredensial.

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

### -Nama
Menentukan nama kredensial.

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

### -Value
Menentukan kredensial sebagai objek **PSCredential** .

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CredentialInfo

## CATATAN

## RELATED LINKS

[Get-AzureAutomationCredential](./Get-AzureAutomationCredential.md)

[New-AzureAutomationCredential](./New-AzureAutomationCredential.md)

[Remove-AzureAutomationCredential](./Remove-AzureAutomationCredential.md)


