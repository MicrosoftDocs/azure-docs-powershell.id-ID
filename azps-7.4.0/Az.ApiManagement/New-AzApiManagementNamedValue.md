---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementnamedvalue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementNamedValue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementNamedValue.md
ms.openlocfilehash: 9bb70fdbba3f4e338118f823dd936d107175859b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144676330"
---
# New-AzApiManagementNamedValue

## SYNOPSIS
Membuat Nilai Bernama baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementnamedvalue) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementNamedValue -Context <PsApiManagementContext> [-NamedValueId <String>] [-Name <String>]
 [-Value <String>] [-Secret] [-Tag <String[]>] [-KeyVault <PsApiManagementKeyVaultEntity>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementNamedValue** membuat **Nilai Bernama** API Management Azure.

## EXAMPLES

### Contoh 1: Membuat nilai bernama yang menyertakan tag
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
$Tags = 'sdk', 'powershell'
New-AzApiManagementNamedValue -Context $apimContext -NamedValueId "Property11" -Name "Property Name" -Value "Property Value" -Tag $Tags
```

Perintah pertama menetapkan dua nilai ke variabel $Tags.
Perintah kedua membuat nilai bernama dan menetapkan string dalam $Tags sebagai tag pada properti .

### Contoh 2: Membuat nilai bernama yang memiliki nilai rahasia
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
New-AzApiManagementNamedValue -Context $apimContext -NamedValueId "Property12" -Name "Secret Property" -Value "Secret Property Value" -Secret
```

Perintah ini membuat **Nilai Bernama** yang memiliki nilai yang dienkripsi.

### Contoh 3 : Membuat keyVault Namedvalue
```powershell
$secretIdentifier = 'https://contoso.vault.azure.net/secrets/xxxx'
$keyvault = New-AzApiManagementKeyVaultObject -SecretIdentifier $secretIdentifier 
$keyVaultNamedValue = New-AzApiManagementNamedValue -Context $context -NamedValueId $keyVaultNamedValueId -Name $keyVaultNamedValueName -keyVault $keyvault -Secret
```

Perintah pertama membuat keyvault.
Perintah kedua membuat nilai bernama menggunakan rahasia dari keyvault ini.

## PARAMETERS

### -Context
Instans PsApiManagementContext.
Parameter ini diperlukan.

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

### -KeyVault
KeyVault digunakan untuk mengambil data Namedvalue. Parameter ini diperlukan jika Nilai tidak ditentukan.
Lihat New-AzApiManagementKeyVaultObject untuk detailnya.

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

### -Name
Nama nilai bernama.
Panjang maksimum adalah 100 karakter.
Ini hanya boleh berisi huruf, digit, titik, tanda hubung, dan karakter garis bawah.
Parameter ini diperlukan.

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

### -NamedValueId
Pengidentifikasi nilai bernama baru.
Parameter ini bersifat opsional.
Jika tidak ditentukan akan dihasilkan.

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

### -Rahasia
Menentukan apakah nilainya adalah rahasia dan harus dienkripsi atau tidak.
Parameter ini bersifat opsional.
Nilai Default adalah false.

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

### -Tag
Tag yang akan dikaitkan dengan nilai bernama.
Parameter ini bersifat opsional.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nilai
Nilai nilai bernama.
Dapat berisi ekspresi kebijakan.
Panjang maksimum adalah 1000 karakter.
Ini mungkin tidak kosong atau hanya terdiri dari spasi kosong.
Parameter ini diperlukan.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Management.Automation.SwitchParameter

### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementNamedValue

## NOTES

## RELATED LINKS
