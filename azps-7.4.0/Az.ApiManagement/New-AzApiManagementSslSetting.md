---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementsslsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementSslSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementSslSetting.md
ms.openlocfilehash: 59f712434c65999037a485e2dad098d9c993e1c1
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144616136"
---
# New-AzApiManagementSslSetting

## SYNOPSIS
Membuat instans PsApiManagementSslSetting

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementsslsetting) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementSslSetting [-FrontendProtocol <Hashtable>] [-BackendProtocol <Hashtable>]
 [-CipherSuite <Hashtable>] [-ServerProtocol <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah pembantu untuk membuat instans PsApiManagementSslSetting.
Perintah ini akan digunakan dengan perintah New-AzApiManagement.

## EXAMPLES

### Contoh 1: Membuat Pengaturan SSL untuk mengaktifkan TLS 1.0 di Backend dan Frontend
```powershell
$enableTls=@{"Tls10" = "True"}
New-AzApiManagementSslSetting -FrontendProtocol $enableTls -BackendProtocol $enableTls
```

```output
FrontendProtocols BackendProtocols CipherSuites ServerProtocols
----------------- ---------------- ------------ ---------------
{Tls10}           {Tls10}
```

Buat instans baru PsApiManagementSslSetting untuk Mengaktifkan TLSv 1.0 di Frontend (antara klien dan APIM) dan Backend (antara APIM dan Backend) ApiManagement Gateway.

## PARAMETERS

### -BackendProtocol
Pengaturan protokol Keamanan Backend. Parameter ini bersifat opsional.
Pengaturan Protokol yang valid adalah `Tls11` - Tls 1.1 `Tls10` - Tls 1.0 `Ssl30` - SSL 3.0

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherSuite
Pengaturan suite sandi Ssl dalam urutan yang ditentukan. Parameter ini bersifat opsional.
Pengaturan yang valid adalah `TripleDes168` - Aktifkan / Nonaktifkan Tripe Des 168

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -FrontendProtocol
Pengaturan protokol Keamanan Frontend. Parameter ini bersifat opsional.
Pengaturan Protokol yang valid adalah `Tls11` - Tls 1.1 `Tls10` - Tls 1.0 `Ssl30` - SSL 3.0


```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerProtocol
Pengaturan protokol server seperti Http2. Parameter ini bersifat opsional.
Pengaturan yang valid adalah `Http2` - Aktifkan Http 2.0

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSslSettings

## NOTES

## RELATED LINKS

[New-AzApiManagement](./New-AzApiManagement.md)

