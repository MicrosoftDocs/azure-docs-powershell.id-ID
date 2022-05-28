---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/new-aznetappfilesexportpolicyruleobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesExportPolicyRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesExportPolicyRuleObject.md
ms.openlocfilehash: df0f12936a49d38acd3cc933f52011b33e46a959
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145535187"
---
# New-AzNetAppFilesExportPolicyRuleObject

## SYNOPSIS
Membuat objek aturan kebijakan ekspor.

## SYNTAX

```
New-AzNetAppFilesExportPolicyRuleObject -RuleIndex <Int32> [-UnixReadOnly] [-UnixReadWrite]
 [-Kerberos5ReadOnly] [-Kerberos5ReadWrite] [-Kerberos5iReadOnly] [-Kerberos5iReadWrite] [-Kerberos5p]
 [-Kerberos5pReadWrite] [-Cifs] [-Nfsv3] [-Nfsv41] [-AllowedClient <String>] [-HasRootAccess]
 [-ChownMode <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
New-AzNetAppFilesExportPolicyRuleObject adalah cmdlet pembantu yang membuat objek aturan kebijakan ekspor yang dapat digunakan dengan New-AzExportPolicyObject dan New-AzNetAppFilesVolume.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $exportPolicyRule = New-AzNetAppFilesExportPolicyRuleObject -RuleIndex 1 -AllowedClients '0.0.0.0/0' -UnixReadOnly -UnixReadWrite -Cifs -Nfsv3 
PS C:\> $exportPolicyRules = $($exportPolicyRule)
PS C:\> $newExportPolicy = New-AzNetAppFilesExportPolicyObject -Rules $exportPolicyRules
PS C:\> New-AzNetAppFilesVolume -ResourceGroupName "MyRG" -AccountName "MyAnfAccount" -PoolName "MyAnfPool" -Name "MyAnfVolume" -l "westus2" -CreationToken "MyAnfVolume" -UsageThreshold 1099511627776 -ServiceLevel "Premium" -SubnetId "/subscriptions/subsId/resourceGroups/MyRG/providers/Microsoft.Network/virtualNetworks/MyVnetName/subnets/MySubNetName" -ExportPolicy $newExportPolicy
```

Contoh ini membuat ExportPolicyRule dalam variabel $exportPolicyRule, menetapkannya sebagai objek kebijakan ekspor $exportPolicyRules yang kemudian digunakan dalam pembuatan volume AFN "MyAnfVolume""

## PARAMETERS

### -AllowedClient
Spesifikasi masuk klien sebagai string yang dipisahkan koma dengan CIDR IPv4, alamat host IPv4, dan nama host.

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

### -ChownMode
Menentukan siapa yang berwenang untuk mengubah kepemilikan file.
dibatasi - Hanya pengguna root yang dapat mengubah kepemilikan file.
unrestricted - Pengguna non-root dapat mengubah kepemilikan file yang mereka miliki.

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

### -Cifs
Memungkinkan protokol CIFS.

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

### -HasRootAccess
Memiliki akses root ke volume.

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

### -Kerberos5iReadOnly
Akses Baca saja Kerberos5i.

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

### -Kerberos5iReadWrite
Kerberos5i Akses baca dan tulis.

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

### -Kerberos5p
Akses Baca-saja Kerberos5p.

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

### -Kerberos5pReadWrite
Akses baca dan tulis Kerberos5p.

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

### -Kerberos5ReadOnly
Akses baca-saja Kerberos5.

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

### -Kerberos5ReadWrite
Akses baca dan tulis Kerberos5.

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

### -Nfsv3
Memungkinkan protokol NFSv3.

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

### -Nfsv41
Memungkinkan protokol NFSv41.

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

### -RuleIndex
Indeks pesanan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnixReadOnly
Akses baca saja.

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

### -UnixReadWrite
Akses baca dan tulis.

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesExportPolicyRule

## NOTES

## RELATED LINKS

[New-AzExportPolicyObject](./New-AzExportPolicyObject.md)
 [Get-AzNetAppFilesVolume](./Get-AzNetAppFilessVolume.md)
 [New-AzNetAppFilesVolume](./New-AzNetAppFilessVolume.md)
 [Update-AzNetAppFilesVolume](./Update-AzNetAppFilessVolume.md)
 [Remove-AzNetAppFilesVolume](./Remove-AzNetAppFilessVolume.md)