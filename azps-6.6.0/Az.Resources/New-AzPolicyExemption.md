---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
ms.openlocfilehash: 7ec6d46eb851351f3468eac2fdc8dec5464a0b25
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136340598"
---
# New-AzPolicyExemption

## SYNOPSIS
Membuat pengecualian kebijakan.

## SYNTAX

```
New-AzPolicyExemption -Name <String> [-Scope <String>] [-DisplayName <String>] [-Description <String>]
 -ExemptionCategory <String> -PolicyAssignment <PsPolicyAssignment> [-PolicyDefinitionReferenceId <String[]>]
 [-ExpiresOn <DateTime>] [-Metadata <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzPolicyExemption** membuat pengecualian kebijakan.
Menentukan penetapan kebijakan, kategori dan lingkup pengecualian.

## EXAMPLES

### Contoh 1: Pengecualian kebijakan di tingkat langganan
```powershell
PS C:\> $Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
PS C:\> $Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
PS C:\> New-AzPolicyExemption -Name 'VirtualMachinePolicyExemption' -PolicyAssignment $Assignment -Scope "/subscriptions/$($Subscription.Id)" -ExemptionCategory Waiver
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya di $Subscription variabel.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya di $Assignment variabel.
Perintah terakhir mengecualikan penetapan kebijakan di $Assignment pada tingkat langganan yang diidentifikasi oleh string lingkup langganan.

### Contoh 2: Pengecualian kebijakan pada tingkat grup sumber daya
```powershell
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
PS C:\> New-AzPolicyExemption -Name 'VirtualMachinePolicyAssignment' -PolicyAssignment $Assignment -Scope $ResourceGroup.ResourceId -ExemptionCategory Mitigated
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya di $ResourceGroup sumber daya.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya di $Assignment variabel.
Perintah terakhir mengecualikan penetapan kebijakan di $Assignment pada tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** dari $ResourceGroup.

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
Deskripsi untuk pembebasan kebijakan baru.

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
Nama tampilan untuk pengecualian kebijakan baru.

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
Kategori pengecualian kebijakan dari pengecualian kebijakan baru.
Nilai yang mungkin adalah Pelepasan dan Mitigasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Waiver, Mitigated

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Kedaluwarsa Pada
Tanggal dan waktu kedaluwarsa (dalam format UTC ISO 8601 yyyy-MM-ddTHH:mm:ssZ) dari pengecualian kebijakan baru.

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

### -Metadata
Metadata untuk pengecualian kebijakan baru.
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
Nama pengecualian kebijakan baru.

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

### -PolicyAssignment
Id penetapan kebijakan yang direferensikan untuk pengecualian kebijakan baru.

```yaml
Type: Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Cakupan pengecualian kebijakan baru, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

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

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

### System.String[]

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=5.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## CATATAN

## RELATED LINKS
