---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/update-azstoragefileserviceproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageFileServiceProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageFileServiceProperty.md
ms.openlocfilehash: 086f6ace441057fc7bf74b9e4beb93d4b8a479d9
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144211694"
---
# Update-AzStorageFileServiceProperty

## SYNOPSIS
Memodifikasi properti layanan untuk layanan file Azure Storage.

## SYNTAX

### AccountName (Default)
```
Update-AzStorageFileServiceProperty [-ResourceGroupName] <String> [-StorageAccountName] <String>
 [-EnableShareDeleteRetentionPolicy <Boolean>] [-ShareRetentionDays <Int32>] [-EnableSmbMultichannel <Boolean>]
 [-SmbProtocolVersion <String[]>] [-SmbAuthenticationMethod <String[]>] [-SmbChannelEncryption <String[]>]
 [-SmbKerberosTicketEncryption <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObject
```
Update-AzStorageFileServiceProperty -StorageAccount <PSStorageAccount>
 [-EnableShareDeleteRetentionPolicy <Boolean>] [-ShareRetentionDays <Int32>] [-EnableSmbMultichannel <Boolean>]
 [-SmbProtocolVersion <String[]>] [-SmbAuthenticationMethod <String[]>] [-SmbChannelEncryption <String[]>]
 [-SmbKerberosTicketEncryption <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FileServicePropertiesResourceId
```
Update-AzStorageFileServiceProperty [-ResourceId] <String> [-EnableShareDeleteRetentionPolicy <Boolean>]
 [-ShareRetentionDays <Int32>] [-EnableSmbMultichannel <Boolean>] [-SmbProtocolVersion <String[]>]
 [-SmbAuthenticationMethod <String[]>] [-SmbChannelEncryption <String[]>]
 [-SmbKerberosTicketEncryption <String[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzStorageFileServiceProperty** memodifikasi properti layanan untuk layanan file Azure Storage.

## EXAMPLES

### Contoh 1: Aktifkan penghapusan sementara berbagi file
```powershell
PS C:\> Update-AzStorageFileServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -EnableShareDeleteRetentionPolicy $true -ShareRetentionDays 5

StorageAccountName                            : mystorageaccount
ResourceGroupName                             : myresourcegroup
ShareDeleteRetentionPolicy.Enabled            : True
ShareDeleteRetentionPolicy.Days               : 5
ProtocolSettings.Smb.Multichannel.Enabled     : False
ProtocolSettings.Smb.Versions                 : 
ProtocolSettings.Smb.AuthenticationMethods    : 
ProtocolSettings.Smb.KerberosTicketEncryption : 
ProtocolSettings.Smb.ChannelEncryption        :
```

Perintah ini memungkinkan penghapusan penghapusan penghapusan sementara berbagi file dengan hari retensi sebagai 5

### Contoh 2: Aktifkan Smb Multichannel
```powershell
PS C:\> Update-AzStorageFileServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -EnableSmbMultichannel $true

StorageAccountName                            : mystorageaccount
ResourceGroupName                             : myresourcegroup
ShareDeleteRetentionPolicy.Enabled            : True
ShareDeleteRetentionPolicy.Days               : 5
ProtocolSettings.Smb.Multichannel.Enabled     : True
ProtocolSettings.Smb.Versions                 : 
ProtocolSettings.Smb.AuthenticationMethods    : 
ProtocolSettings.Smb.KerberosTicketEncryption : 
ProtocolSettings.Smb.ChannelEncryption        :
```

Perintah ini memungkinkan Smb Multichannel, hanya didukung pada akun Premium FileStorage.

### Contoh 3: Memperbarui pengaturan smb aman
```powershell
PS C:\> Update-AzStorageFileServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" `
            -SMBProtocolVersion SMB2.1,SMB3.0,SMB3.1.1  `
            -SMBAuthenticationMethod Kerberos,NTLMv2 `
            -SMBKerberosTicketEncryption RC4-HMAC,AES-256 `
            -SMBChannelEncryption AES-128-CCM,AES-128-GCM,AES-256-GCM 

StorageAccountName                            : mystorageaccount
ResourceGroupName                             : myresourcegroup
ShareDeleteRetentionPolicy.Enabled            : True
ShareDeleteRetentionPolicy.Days               : 5
ProtocolSettings.Smb.Multichannel.Enabled     : True
ProtocolSettings.Smb.Versions                 : {SMB2.1, SMB3.0, SMB3.1.1}
ProtocolSettings.Smb.AuthenticationMethods    : {Kerberos, NTLMv2}
ProtocolSettings.Smb.KerberosTicketEncryption : {RC4-HMAC, AES-256}
ProtocolSettings.Smb.ChannelEncryption        : {AES-128-CCM, AES-128-GCM, AES-256-GCM}
```

Perintah ini memperbarui pengaturan smb aman.

### Contoh 4: Menghapus pengaturan smb aman
```powershell
PS C:\> Update-AzStorageFileServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" `
            -SMBProtocolVersion @() `
            -SMBAuthenticationMethod @() `
            -SMBKerberosTicketEncryption @() `
            -SMBChannelEncryption @() 

StorageAccountName                            : mystorageaccount
ResourceGroupName                             : myresourcegroup
ShareDeleteRetentionPolicy.Enabled            : True
ShareDeleteRetentionPolicy.Days               : 5
ProtocolSettings.Smb.Multichannel.Enabled     : True
ProtocolSettings.Smb.Versions                 : 
ProtocolSettings.Smb.AuthenticationMethods    : 
ProtocolSettings.Smb.KerberosTicketEncryption : 
ProtocolSettings.Smb.ChannelEncryption        :
```

Perintah ini menghapus pengaturan smb yang aman.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableShareDeleteRetentionPolicy
Aktifkan Kebijakan Penyimpanan Penghapusan berbagi untuk akun penyimpanan dengan diatur ke $true, nonaktifkan berbagi Kebijakan Penyimpanan Penghapusan dengan diatur ke $false.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSmbMultichannel
Aktifkan Multichannel dengan diatur ke $true, nonaktifkan Multichannel dengan diatur ke $false. Berlaku hanya untuk Premium FileStorage.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Masukkan Id Sumber Daya akun Storage, atau Properti layanan file Id Sumber Daya.

```yaml
Type: System.String
Parameter Sets: FileServicePropertiesResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShareRetentionDays
Mengatur jumlah hari retensi untuk berbagi DeleteRetentionPolicy.
Nilai hanya boleh diatur saat mengaktifkan Kebijakan Penyimpanan Penghapusan berbagi.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Days, RetentionDays

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmbAuthenticationMethod
Mendapatkan atau mengatur metode autentikasi SMB yang didukung oleh server. Nilai yang valid adalah NTLMv2, Kerberos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Kerberos, NTLMv2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmbChannelEncryption
Mendapatkan atau mengatur enkripsi saluran SMB yang didukung oleh server. Nilai yang valid adalah AES-128-CCM, AES-128-GCM, AES-256-GCM.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: AES-128-CCM, AES-128-GCM, AES-256-GCM

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmbKerberosTicketEncryption
Mendapatkan atau mengatur enkripsi tiket kerberos yang didukung oleh server. Nilai yang valid adalah RC4-HMAC, AES-256.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: AES-256, RC4-HMAC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SmbProtocolVersion
Mendapatkan atau mengatur versi protokol SMB yang didukung oleh server. Nilai yang valid adalah SMB2.1, SMB3.0, SMB3.1.1.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: SMB2.1, SMB3.0, SMB3.1.1

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccount
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Nama Akun.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases: AccountName, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSFileServiceProperties

## NOTES

## RELATED LINKS
