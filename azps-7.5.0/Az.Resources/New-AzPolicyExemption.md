---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azpolicyexemption
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzPolicyExemption.md
ms.openlocfilehash: e3c66df5cfd1fbdeec32efc10e2335e618e66247
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144198777"
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
Tentukan penetapan kebijakan, kategori pengecualian, dan cakupan.

## EXAMPLES

### Contoh 1: Pembebasan kebijakan di tingkat langganan
```powershell
$Subscription = Get-AzSubscription -SubscriptionName 'Subscription01'
$Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
New-AzPolicyExemption -Name 'VirtualMachinePolicyExemption' -PolicyAssignment $Assignment -Scope "/subscriptions/$($Subscription.Id)" -ExemptionCategory Waiver
```

Perintah pertama mendapatkan langganan bernama Subscription01 dengan menggunakan cmdlet Get-AzSubscription dan menyimpannya dalam variabel $Subscription.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment dengan menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam variabel $Assignment.
Perintah akhir mengecualikan penetapan kebijakan dalam $Assignment pada tingkat langganan yang diidentifikasi oleh string cakupan langganan.

### Contoh 2: Pengecualian kebijakan di tingkat grup sumber daya
```powershell
$ResourceGroup = Get-AzResourceGroup -Name 'ResourceGroup11'
$Assignment = Get-AzPolicyAssignment -Name 'VirtualMachinePolicyAssignment'
New-AzPolicyExemption -Name 'VirtualMachinePolicyAssignment' -PolicyAssignment $Assignment -Scope $ResourceGroup.ResourceId -ExemptionCategory Mitigated
```

Perintah pertama mendapatkan grup sumber daya bernama ResourceGroup11 dengan menggunakan cmdlet Get-AzResourceGroup dan menyimpannya dalam variabel $ResourceGroup.
Perintah kedua mendapatkan penetapan kebijakan bernama VirtualMachinePolicyAssignment dengan menggunakan cmdlet Get-AzPolicyAssignment dan menyimpannya dalam variabel $Assignment.
Perintah akhir mengecualikan penetapan kebijakan di $Assignment pada tingkat grup sumber daya yang diidentifikasi oleh properti **ResourceId** $ResourceGroup.

## PARAMETERS

### -ApiVersion
Saat diatur, menunjukkan versi API penyedia sumber daya yang akan digunakan.
Jika tidak ditentukan, versi API secara otomatis ditentukan sebagai yang terbaru yang tersedia.

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
Deskripsi untuk pengecualian kebijakan baru.

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
Kategori pembebasan kebijakan dari pengecualian kebijakan baru.
Nilai yang mungkin adalah Pengabaian dan Dimitigasi.

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

### -ExpiresOn
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
Ini bisa menjadi jalur ke file yang berisi metadata JSON, atau metadata sebagai string JSON.

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

### -Name
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
Id penetapan kebijakan yang dirujuk untuk pengecualian kebijakan baru.

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
Daftar ID referensi definisi kebijakan saat penetapan kebijakan terkait adalah untuk kumpulan kebijakan (inisiatif).

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
Saat diatur, menunjukkan bahwa cmdlet harus menggunakan versi API pra-rilis saat secara otomatis menentukan versi mana yang akan digunakan.

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

### -Cakupan
Cakupan pengecualian kebijakan baru, misalnya /providers/managementGroups/{managementGroupName}, default ke langganan saat ini.

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

### System.String

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment

### System.String[]

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=5.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyExemption

## NOTES

## RELATED LINKS
