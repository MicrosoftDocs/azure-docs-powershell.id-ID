---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyExemption.md
ms.openlocfilehash: beb1dbbc7beca157dd33c20ff95b97c7b28a9d57
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136701156"
---
# Set-AzPolicyExemption

## SYNOPSIS
Mengubah pengecualian kebijakan.

## SYNTAX

### NameParameterSet (Default)
```
Set-AzPolicyExemption -Name <String> [-Scope <String>] [-DisplayName <String>] [-Description <String>]
 [-ExemptionCategory <String>] [-PolicyDefinitionReferenceId <String[]>] [-ExpiresOn <DateTime>]
 [-ClearExpiration] [-Metadata <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSet
```
Set-AzPolicyExemption -Id <String> [-DisplayName <String>] [-Description <String>]
 [-ExemptionCategory <String>] [-PolicyDefinitionReferenceId <String[]>] [-ExpiresOn <DateTime>]
 [-ClearExpiration] [-Metadata <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Set-AzPolicyExemption [-DisplayName <String>] [-Description <String>] [-ExemptionCategory <String>]
 [-PolicyDefinitionReferenceId <String[]>] [-ExpiresOn <DateTime>] [-ClearExpiration] [-Metadata <String>]
 -InputObject <PsPolicyExemption> [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzPolicyExemption** mengubah pengecualian kebijakan.
Tentukan pengecualian menurut ID atau menurut nama dan lingkup.

## EXAMPLES

### Contoh 1: Perbarui nama tampilan
```
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId
PS C:\> Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -DisplayName 'Exempt VM creation limit'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup cmdlet.
Perintah menyimpan objek tersebut dalam $ResourceGroup variabel.
Perintah kedua mendapatkan pengecualian kebijakan bernama PolicyExemption07 menggunakan cmdlet Get-AzPolicyExemption cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyExemption variabel.
Perintah terakhir memperbarui nama tampilan pada pengecualian kebijakan pada grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 2: Memperbarui waktu tanggal kedaluwarsa
```
PS C:\> $NextMonth = (Get-Date).AddMonths(1)
PS C:\> $PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
PS C:\> Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ExpiresOn $NextMonth
```

Perintah pertama mendapatkan waktu tanggal saat ini menggunakan cmdlet Get-Date dan menambahkan 1 bulan ke waktu tanggal saat ini Perintah menyimpan objek tersebut dalam $NextMonth variabel.
Perintah kedua mendapatkan pengecualian kebijakan bernama PolicyExemption07 menggunakan cmdlet Get-AzPolicyExemption cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyExemption variabel.
Perintah terakhir memperbarui tanggal kedaluwarsa untuk pengecualian kebijakan pada langganan default.

### Contoh 3: Hapus waktu tanggal kedaluwarsa
```
PS C:\> $PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
PS C:\> Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ClearExpiration
```

Perintah pertama mendapatkan pengecualian kebijakan bernama PolicyExemption07 menggunakan cmdlet Get-AzPolicyExemption cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyExemption variabel.
Perintah kedua menghapus tanggal kedaluwarsa untuk pengecualian kebijakan pada langganan default.
Pengecualian yang diperbarui tidak akan pernah kedaluwarsa.

### Contoh 4: Perbarui kategori kedaluwarsa
```
PS C:\> $PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
PS C:\> Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ExemptionCategory Mitigated
```

Perintah pertama mendapatkan pengecualian kebijakan bernama PolicyExemption07 menggunakan cmdlet Get-AzPolicyExemption cmdlet.
Perintah menyimpan objek tersebut dalam $PolicyExemption variabel.
Perintah kedua memperbarui kategori kedaluwarsa untuk pengecualian kebijakan pada langganan default.
Pengecualian yang diperbarui tidak akan pernah kedaluwarsa.

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai versi terbaru yang tersedia.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearExpiration
Jika diatur, sakelar ini mengosongkan tanggal dan waktu kedaluwarsa pengecualian kebijakan yang diperbarui.

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

### -Deskripsi
Deskripsi untuk pengecualian kebijakan yang diperbarui.

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

### -DisplayName
Nama tampilan untuk pengecualian kebijakan yang diperbarui.

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

### -ExemptionCategory
Kategori pengecualian kebijakan dari pengecualian kebijakan yang diperbarui.
Nilai yang mungkin adalah Pelepasan dan Mitigasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Waiver, Mitigated

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Kedaluwarsa Pada
Tanggal dan waktu kedaluwarsa (dalam format UTC ISO 8601 yyyy-MM-ddTHH:mm:ssZ) dari pengecualian kebijakan yang diperbarui.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Id pengecualian kebijakan yang sepenuhnya memenuhi syarat untuk diperbarui, termasuk lingkup, misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Authorization/policyExemptions/{policyExemptionName}.

```yaml
Type: System.String
Parameter Sets: IdParameterSet
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Objek pengecualian kebijakan untuk pembaruan yang merupakan output dari cmdlet lainnya.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Metadata
Metadata untuk pengecualian kebijakan yang diperbarui.
Ini bisa berupa jalur ke file yang berisi JSON metadata, atau metadata sebagai string JSON.

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

### -Nama
Nama pengecualian kebijakan untuk pembaruan.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyDefinitionReferenceId
Daftar ID referensi definisi kebijakan saat penetapan kebijakan terkait adalah untuk satu set (inisiatif) kebijakan.

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

### -Pra
Saat diatur, cmdlet harus menggunakan versi API prari tamu ketika menentukan versi mana yang akan digunakan secara otomatis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup pengecualian kebijakan yang diperbarui, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
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

## INPUTS

### System.String

### System.String[]

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=5.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## CATATAN

## RELATED LINKS
