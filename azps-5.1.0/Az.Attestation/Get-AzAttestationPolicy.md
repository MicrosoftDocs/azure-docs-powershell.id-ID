---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Attestation.dll-Help.xml
Module Name: Az.Attestation
online version: https://docs.microsoft.com/en-us/powershell/module/az.attestation/get-azattestationpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Attestation/Attestation/help/Get-AzAttestationPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Attestation/Attestation/help/Get-AzAttestationPolicy.md
ms.openlocfilehash: 64a74902d1a5b10ed36c635b58910246634e68b0
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136029554"
---
# Get-AzAttestationPolicy

## SYNOPSIS
Dapatkan kebijakan dari penyewa di Azure Attestation.

## SINTAKS

### NameParameterSet
```
Get-AzAttestationPolicy [-Name] <String> [-ResourceGroupName] <String> -Tee <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Get-AzAttestationPolicy [-ResourceId] <String> -Tee <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefaultProviderParameterSet
```
Get-AzAttestationPolicy [-Location] <String> [-DefaultProvider] -Tee <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet Get-AzAttestationPolicy baru mendapatkan kebijakan dari penyewa di Azure Attestation.

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzAttestationPolicy -Name pshtest -ResourceGroupName psh-test-rg -Tee SgxEnclave                                                                                                                                                                                                                    
Text       : version= 1.0;
             authorizationrules{
                 c:[type=="$is-debuggable"] => permit();
             };
             issuancerules{
                 c:[type=="$is-debuggable"] => issue(type="is-debuggable", value=c.value);
                 c:[type=="$sgx-mrsigner"] => issue(type="sgx-mrsigner", value=c.value);
                 c:[type=="$sgx-mrenclave"] => issue(type="sgx-mrenclave", value=c.value);
                 c:[type=="$product-id"] => issue(type="product-id", value=c.value);
                 c:[type=="$svn"] => issue(type="svn", value=c.value);
                 c:[type=="$tee"] => issue(type="tee", value=c.value);
                 c:[type=="$tee-future"] => issue(type="tee-future", value=c.value);
             };

TextLength : 604
Jwt        : eyJhbGciOiJub25lIn0.eyJBdHRlc3RhdGlvblBvbGljeSI6ICJkbVZ5YzJsdmJqMGdNUzR3T3cwS1lYVjBhRzl5YVhwaGRHbHZibkoxYkdWemV3MEtJQ0FnSUdNNlczUjVjR1U5UFNJa2FYTXRaR1ZpZFdkbllXSnNaU0pkSUQwLUlIQmxjbTFwZENncE93MEtmVHNOQ21semMzVmhibU5sY25Wc1pYTjdEUW9nSUNBZ1l6cGJkSGx3WlQwOUlpUnBjeTFrWldKMVoyZGhZbXhsSWwwZ1BUNGdhWE56ZFdVb2RIbHdaVDBpYVhNdFpHVmlkV2RuWVdKc1pTSXNJSFpoYkhWbFBXTXVkbUZzZFdVcE93MEtJQ0FnSUdNNlczUjVjR1U5UFNJa2MyZDRMVzF5YzJsbmJtVnlJbDBnUFQ0Z2FYTnpkV1VvZEhsd1pUMGljMmQ0TFcxeWMybG5ibVZ5SWl3Z2RtRnNkV1U5WXk1MllXeDFaU2s3RFFvZ0lDQWdZenBiZEhsd1pUMDlJaVJ6WjNndGJYSmxibU5zWVhabElsMGdQVDRnYVhOemRXVW9kSGx3WlQwaWMyZDRMVzF5Wlc1amJHRjJaU0lzSUhaaGJIVmxQV011ZG1Gc2RXVXBPdzBLSUNBZ0lHTTZXM1I1Y0dVOVBTSWtjSEp2WkhWamRDMXBaQ0pkSUQwLUlHbHpjM1ZsS0hSNWNHVTlJbkJ5YjJSMVkzUXRhV1FpTENCMllXeDFaVDFqTG5aaGJIVmxLVHNOQ2lBZ0lDQmpPbHQwZVhCbFBUMGlKSE4yYmlKZElEMC1JR2x6YzNWbEtIUjVjR1U5SW5OMmJpSXNJSFpoYkhWbFBXTXVkbUZzZFdVcE93MEtJQ0FnSUdNNlczUjVjR1U5UFNJa2RHVmxJbDBnUFQ0Z2FYTnpkV1VvZEhsd1pUMGlkR1ZsSWl3Z2RtRnNkV1U5WXk1MllXeDFaU2s3RFFvZ0lDQWdZenBiZEhsd1pUMDlJaVIwWldVdFpuVjBkWEpsSWwwZ1BUNGdhWE56ZFdVb2RIbHdaVDBpZEdWbExXWjFkSFZ5WlNJc0lIWmhiSFZsUFdNdWRtRnNkV1VwT3cwS2ZUc05DZyJ9.
JwtLength  : 1129
Algorithm  : none
```

Dapatkan kebijakan untuk *Pshtest Penyedia Attestation untuk* Tipe *SgxEnclave*.

### Contoh 2
```powershell
PS C:\> Get-AzAttestationPolicy -DefaultProvider -Location "UK South" -Tee SgxEnclave
Text       : version= 1.0;authorizationrules{c:[type=="$is-debuggable"] => permit();};issuancerules{c:[type=="$is-debuggable"] => issue(type="is-debuggable",
             value=c.value);c:[type=="$sgx-mrsigner"] => issue(type="sgx-mrsigner", value=c.value);c:[type=="$sgx-mrenclave"] => issue(type="sgx-mrenclave",
             value=c.value);c:[type=="$product-id"] => issue(type="product-id", value=c.value);c:[type=="$svn"] => issue(type="svn", value=c.value);c:[type=="$tee"]
             => issue(type="tee", value=c.value);};
TextLength : 479
Jwt        : eyJhbGciOiJub25lIn0.eyJBdHRlc3RhdGlvblBvbGljeSI6ICJkbVZ5YzJsdmJqMGdNUzR3TzJGMWRHaHZjbWw2WVhScGIyNXlkV3hsYzN0ak9sdDBlWEJsUFQwaUpHbHpMV1JsWW5WbloyRmliR1Vp
             WFNBOVBpQndaWEp0YVhRb0tUdDlPMmx6YzNWaGJtTmxjblZzWlhON1l6cGJkSGx3WlQwOUlpUnBjeTFrWldKMVoyZGhZbXhsSWwwZ1BUNGdhWE56ZFdVb2RIbHdaVDBpYVhNdFpHVmlkV2RuWVdKc1pT
             SXNJSFpoYkhWbFBXTXVkbUZzZFdVcE8yTTZXM1I1Y0dVOVBTSWtjMmQ0TFcxeWMybG5ibVZ5SWwwZ1BUNGdhWE56ZFdVb2RIbHdaVDBpYzJkNExXMXljMmxuYm1WeUlpd2dkbUZzZFdVOVl5NTJZV3gx
             WlNrN1l6cGJkSGx3WlQwOUlpUnpaM2d0YlhKbGJtTnNZWFpsSWwwZ1BUNGdhWE56ZFdVb2RIbHdaVDBpYzJkNExXMXlaVzVqYkdGMlpTSXNJSFpoYkhWbFBXTXVkbUZzZFdVcE8yTTZXM1I1Y0dVOVBT
             SWtjSEp2WkhWamRDMXBaQ0pkSUQwLUlHbHpjM1ZsS0hSNWNHVTlJbkJ5YjJSMVkzUXRhV1FpTENCMllXeDFaVDFqTG5aaGJIVmxLVHRqT2x0MGVYQmxQVDBpSkhOMmJpSmRJRDAtSUdsemMzVmxLSFI1
             Y0dVOUluTjJiaUlzSUhaaGJIVmxQV011ZG1Gc2RXVXBPMk02VzNSNWNHVTlQU0lrZEdWbElsMGdQVDRnYVhOemRXVW9kSGx3WlQwaWRHVmxJaXdnZG1Gc2RXVTlZeTUyWVd4MVpTazdmVHMifQ.
JwtLength  : 907
Algorithm  : none
```

Mendapatkan kebijakan untuk Penyedia Default Attestation dari Location *UK South* untuk Tipe *SgxEnclave*.

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

### -DefaultProvider
Menentukan ini adalah permintaan ke penyedia attestation default.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultProviderParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan Lokasi penyedia attestation default.

```yaml
Type: System.String
Parameter Sets: DefaultProviderParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama penyewa.
Cmdlet ini mendapatkan kebijakan attestation untuk penyewa yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya dari penyedia attestation.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Menentukan ResourceID dari penyedia attestation.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tee
Menentukan tipe Lingkungan Eksekusi Tepercaya.
Kami mendukung empat tipe lingkungan: SgxEnclave, OpenEnclave, CyResComponent dan VBSEnclave.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Attestation.Models.PSPolicy

## CATATAN

## LINK TERKAIT
