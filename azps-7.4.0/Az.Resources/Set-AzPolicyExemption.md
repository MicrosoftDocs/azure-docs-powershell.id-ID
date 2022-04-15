---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzPolicyExemption.md
ms.openlocfilehash: 350f4d4d9d4bd281fb1b0fcad64deb8426107a50
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142166009"
---
# Set-AzPolicyExemption

## SYNOPSIS
Mengubah pembebasan kebijakan.

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
Cmdlet **Set-AzPolicyExemption** mengubah pembebasan kebijakan.
Tentukan pengecualian menurut ID atau menurut nama dan lingkup.

## EXAMPLES

### Contoh 1: Memperbarui nama tampilan
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
 $PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07' -Scope $ResourceGroup.ResourceId
Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -DisplayName 'Exempt VM creation limit'
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 menggunakan cmdlet Get-AzResourceGroup.
Perintah menyimpan objek tersebut dalam variabel $ResourceGroup.
Perintah kedua mendapatkan pembebasan kebijakan bernama PolicyExemption07 dengan menggunakan cmdlet Get-AzPolicyExemption.
Perintah menyimpan objek tersebut dalam variabel $PolicyExemption.
Perintah akhir memperbarui nama tampilan pada pembebasan kebijakan pada grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

### Contoh 2: Memperbarui waktu tanggal kedaluwarsa
```powershell
$NextMonth = (Get-Date).AddMonths(1)
$PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ExpiresOn $NextMonth
```

Perintah pertama mendapatkan waktu tanggal saat ini dengan menggunakan cmdlet Get-Date dan menambahkan 1 bulan ke waktu tanggal saat ini Perintah menyimpan objek tersebut dalam variabel $NextMonth.
Perintah kedua mendapatkan pembebasan kebijakan bernama PolicyExemption07 dengan menggunakan cmdlet Get-AzPolicyExemption.
Perintah menyimpan objek tersebut dalam variabel $PolicyExemption.
Perintah terakhir memperbarui waktu tanggal kedaluwarsa untuk pembebasan kebijakan pada langganan default.

### Contoh 3: Hapus tanggal kedaluwarsa
```powershell
$PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ClearExpiration
```

Perintah pertama mendapatkan pembebasan kebijakan bernama PolicyExemption07 dengan menggunakan cmdlet Get-AzPolicyExemption.
Perintah menyimpan objek tersebut dalam variabel $PolicyExemption.
Perintah kedua menghapus tanggal kedaluwarsa untuk pembebasan kebijakan pada langganan default.
Pengecualian yang diperbarui tidak akan pernah kedaluwarsa.

### Contoh 4: Memperbarui kategori kedaluwarsa
```powershell
$PolicyExemption = Get-AzPolicyExemption -Name 'PolicyExemption07'
Set-AzPolicyExemption -Id $PolicyExemption.ResourceId -ExemptionCategory Mitigated
```

Perintah pertama mendapatkan pembebasan kebijakan bernama PolicyExemption07 dengan menggunakan cmdlet Get-AzPolicyExemption.
Perintah menyimpan objek tersebut dalam variabel $PolicyExemption.
Perintah kedua memperbarui kategori kedaluwarsa untuk pembebasan kebijakan pada langganan default.
Pengecualian yang diperbarui tidak akan pernah kedaluwarsa.

## PARAMETERS

### -ApiVersion
Ketika diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
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
Jika diatur, sakelar ini menghapus tanggal dan waktu kedaluwarsa pada pembebasan kebijakan yang diperbarui.

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
Deskripsi untuk pembebasan kebijakan yang diperbarui.

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
Nama tampilan untuk pembebasan kebijakan yang diperbarui.

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
Kategori pembebasan kebijakan dari pembebasan kebijakan yang diperbarui.
Nilai yang memungkinkan adalah Pengabaian dan Dimitigasi.

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

### -KedaluwarsaOn
Tanggal dan waktu kedaluwarsa (dalam format UTC ISO 8601 yyyy-MM-ddTHH:mm:ssZ) dari pembebasan kebijakan yang diperbarui.

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
Id pembebasan kebijakan yang sepenuhnya memenuhi syarat untuk diperbarui, termasuk lingkup, misalnya /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Authorization/policyExemptions/{policyExemptionName}.

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
Objek pembebasan kebijakan untuk memperbarui yang merupakan output dari cmdlet lain.

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
Metadata untuk pembebasan kebijakan yang diperbarui.
Ini bisa berupa jalur ke file yang berisi metadata JSON, atau metadata sebagai string JSON.

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
Nama pembebasan kebijakan untuk diperbarui.

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
Daftar ID referensi definisi kebijakan ketika penetapan kebijakan terkait adalah untuk kumpulan kebijakan (inisiatif).

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
Ketika diatur, menunjukkan bahwa cmdlet harus menggunakan versi API prarilis saat menentukan versi mana yang akan digunakan secara otomatis.

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
Lingkup pembebasan kebijakan yang diperbarui, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=5.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## CATATAN

## RELATED LINKS
