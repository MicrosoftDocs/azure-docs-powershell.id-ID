---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
ms.openlocfilehash: f149cfb24811c187f6f5ce11b38e170d333c3c1f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142122245"
---
# New-AzPolicyExemption

## SYNOPSIS
Membuat pengecualian kebijakan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/new-azpolicyexemption) untuk informasi terbaru.

## SYNTAX

```
New-AzPolicyExemption -Name <String> [-Scope <String>] [-DisplayName <String>] [-Description <String>]
 -ExemptionCategory <String> -PolicyAssignment <PsPolicyAssignment> [-PolicyDefinitionReferenceId <String[]>]
 [-ExpiresOn <DateTime>] [-Metadata <String>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzPolicyExemption** membuat pengecualian kebijakan.
Tentukan penetapan kebijakan, kategori pembebasan, dan lingkup.

## EXAMPLES

### Contoh 1: Pembebasan kebijakan pada tingkat langganan
```powershell
PS C:\> $Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
PS C:\> $Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
PS C:\> New-AzPolicyExemption -Name 'VirtualMachinePolicyExemption' -PolicyAssignment $Assignment -Scope "/subscriptions/$($Subscription.Id)" -ExemptionCategory Waiver
```

Perintah pertama mendapatkan langganan bernama Subscription01 menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment dengan menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam variabel $Assignment.
Perintah akhir mengecualikan penetapan kebijakan dalam $Assignment pada tingkat langganan yang diidentifikasi oleh string lingkup langganan.

### Contoh 2: Pembebasan kebijakan di tingkat grup sumber daya
```powershell
PS C:\> $ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
PS C:\> $Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
PS C:\> New-AzPolicyExemption -Name 'VirtualMachinePolicyAssignment' -PolicyAssignment $Assignment -Scope $ResourceGroup.ResourceId -ExemptionCategory Mitigated
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment dengan menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam variabel $Assignment.
Perintah akhir mengecualikan penetapan kebijakan dalam $Assignment pada tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

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
Nama tampilan untuk pembebasan kebijakan baru.

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
Kategori pembebasan kebijakan dari pembebasan kebijakan baru.
Nilai yang memungkinkan adalah Pengabaian dan Dimitigasi.

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

### -KedaluwarsaOn
Tanggal dan waktu kedaluwarsa (dalam format UTC ISO 8601 yyyy-MM-ddTHH:mm:ssZ) dari pembebasan kebijakan baru.

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
Metadata untuk pembebasan kebijakan baru.
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
Nama pembebasan kebijakan baru.

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
Id penugasan kebijakan yang dirujuk untuk pembebasan kebijakan baru.

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
Lingkup pembebasan kebijakan baru, misalnya /providers/managementGroups/{managementGroupName}, default untuk langganan saat ini.

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

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

### System.String[]

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=5.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## CATATAN

## RELATED LINKS
