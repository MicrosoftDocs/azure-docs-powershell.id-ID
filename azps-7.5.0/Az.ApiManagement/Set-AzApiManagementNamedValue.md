---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagementnamedvalue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementNamedValue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementNamedValue.md
ms.openlocfilehash: a5e350ac727c3d5110986d0444499aeda15eb657
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145686298"
---
# Set-AzApiManagementNamedValue

## SYNOPSIS
Memodifikasi nilai bernama API Management.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/set-azapimanagementnamedvalue) untuk informasi terbaru.

## SYNTAX

```
Set-AzApiManagementNamedValue -Context <PsApiManagementContext> -NamedValueId <String> [-Name <String>]
 [-Value <String>] [-Secret <Boolean>] [-Tag <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApiManagementNamedValue** memodifikasi Nilai Bernama API Management Azure.

## EXAMPLES

### Contoh 1: Mengubah tag pada nilai bernama
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
$Tags = 'sdk', 'powershell'
Set-AzApiManagementNamedValue -Context $apimContext -NamedValueId "Property11" -Tag $Tags -PassThru
```

Perintah pertama menetapkan dua nilai ke variabel $Tags.
Perintah kedua memodifikasi nilai bernama yang memiliki ID Property11.
Perintah menetapkan string dalam $Tags sebagai tag pada nilai bernama.

### Contoh 2: Ubah nilai bernama agar memiliki nilai rahasia
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementNamedValue -Context $apimContext -NamedValueId "Property12" -Secret $True -PassThru
```

Perintah ini mengubah nilai bernama menjadi Terenkripsi.

### Contoh: 3

Memodifikasi nilai bernama API Management. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzApiManagementNamedValue -Context <PsApiManagementContext> -Name 'ContosoApi' -NamedValueId 'Property11' -Secret $true -Tag <String[]> -Value 'Property Value'
```

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

### -Name
Nama nilai bernama.
Panjang maksimum adalah 100 karakter.
Ini hanya boleh berisi huruf, digit, titik, tanda hubung, dan karakter garis bawah.
Parameter ini bersifat opsional.

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
Pengidentifikasi nilai bernama untuk diperbarui.
Parameter ini bersifat wajib.

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

### -PassThru
Jika ditentukan, maka instans jenis Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementProperty yang mewakili properti yang dimodifikasi akan ditulis ke output.

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

### -Rahasia
Apakah nilai bernama adalah rahasia dan nilainya harus dienkripsi.
Parameter ini bersifat opsional.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tag yang terkait dengan nilai bernama.
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
Parameter ini bersifat opsional.

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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementNamedValue

## NOTES

## RELATED LINKS
