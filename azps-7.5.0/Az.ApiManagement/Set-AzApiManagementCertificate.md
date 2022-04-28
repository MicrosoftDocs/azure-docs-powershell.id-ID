---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: 12FC21EB-0B4E-4275-88FB-7FF42730A6A0
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagementcertificate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementCertificate.md
ms.openlocfilehash: 804130dd2889bdffa5522587386c0e8599606a49
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144230083"
---
# Set-AzApiManagementCertificate

## SYNOPSIS
Memodifikasi sertifikat API Management yang dikonfigurasi untuk autentikasi bersama dengan backend.

## SYNTAX

### LoadFromFile (Default)
```
Set-AzApiManagementCertificate -Context <PsApiManagementContext> -CertificateId <String>
 [-PfxFilePath <String>] [-PfxPassword <String>] [-PassThru] [-KeyVault <PsApiManagementKeyVaultEntity>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Mentah
```
Set-AzApiManagementCertificate -Context <PsApiManagementContext> -CertificateId <String> [-PfxBytes <Byte[]>]
 [-PfxPassword <String>] [-PassThru] [-KeyVault <PsApiManagementKeyVaultEntity>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApiManagementCertificate** memodifikasi sertifikat Azure API Management.

## EXAMPLES

### Contoh 1: Mengubah sertifikat
```powershell
$ApiMgmtContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementCertificate -Context $ApiMgmtContext -CertificateId "0123456789" -PfxFilePath "C:\contoso\certificates\apimanagementnew.pfx" -PfxPassword "2222"
```

Perintah ini memodifikasi sertifikat API Management yang ditentukan.

## PARAMETERS

### -CertificateId
Menentukan ID sertifikat yang akan diubah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Context
Menentukan objek **PsApiManagementContext** .

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -KeyVault
KeyVault digunakan untuk mengambil data sertifikat. Parameter ini diperlukan jika -PfxFilePath tidak ditentukan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementKeyVaultEntity
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
passthru

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxBytes
Menentukan array byte file sertifikat dalam format .pfx.
Parameter ini diperlukan jika Anda tidak menentukan parameter *PfxFilePath* .

```yaml
Type: System.Byte[]
Parameter Sets: Raw
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxFilePath
Menentukan jalur ke file sertifikat dalam format .pfx untuk membuat dan mengunggah.
Parameter ini diperlukan jika Anda tidak menentukan parameter *PfxBytes* .

```yaml
Type: System.String
Parameter Sets: LoadFromFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PfxPassword
Menentukan kata sandi untuk sertifikat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Byte[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementCertificate

## NOTES

## RELATED LINKS

[Get-AzApiManagementCertificate](./Get-AzApiManagementCertificate.md)

[New-AzApiManagementCertificate](./New-AzApiManagementCertificate.md)

[Remove-AzApiManagementCertificate](./Remove-AzApiManagementCertificate.md)


