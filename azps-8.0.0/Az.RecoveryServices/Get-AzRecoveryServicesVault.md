---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: 818B5302-91EE-425F-B1CD-86B626F1B7A3
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesVault.md
ms.openlocfilehash: 9028b5fd532bba21eb0c6c1959030f673fb00a37
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513342"
---
# Get-AzRecoveryServicesVault

## SYNOPSIS

Mendapatkan daftar vault Layanan Pemulihan.

## SYNTAX

### ByTagNameValueParameterSet
```
Get-AzRecoveryServicesVault [[-ResourceGroupName] <String>] [[-Name] <String>] [-TagName <String>]
 [-TagValue <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByTagObjectParameterSet
```
Get-AzRecoveryServicesVault [[-ResourceGroupName] <String>] [[-Name] <String>] -Tag <Hashtable>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

Cmdlet **Get-AzRecoveryServicesVault** mendapatkan daftar vault Layanan Pemulihan dalam langganan saat ini.

## EXAMPLES

### Contoh 1

```powershell
Get-AzRecoveryServicesVault
```

Dapatkan daftar vault dalam langganan yang dipilih.

### Contoh 2

```powershell
Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup"
```

Dapatkan daftar vault dalam grup sumber daya di langganan yang dipilih.

### Contoh: 3

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "resourceGroup" -Name "vaultName"
$vault.Identity | Format-List
```

```output
PrincipalId : XXXXXXXX-XXXX-XXXX
TenantId    : XXXXXXXX-XXXX-XXXX
Type        : SystemAssigned
```

Cmdlet pertama mendapatkan vault dalam grup sumber daya dengan nama tertentu. Kemudian kami mengakses informasi MSI dari vault.

## PARAMETERS

### -DefaultProfile

Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

Menentukan nama vault yang akan dikueri.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName

Menentukan nama grup sumber daya Azure untuk mengambil objek Layanan Pemulihan yang ditentukan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag

Menentukan Tag yang akan dikueri

```yaml
Type: System.Collections.Hashtable
Parameter Sets: ByTagObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagName

Menentukan Kunci Tag yang akan dikueri

```yaml
Type: System.String
Parameter Sets: ByTagNameValueParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagValue

Menentukan Nilai Tag yang akan dikueri

```yaml
Type: System.String
Parameter Sets: ByTagNameValueParameterSet
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

### Microsoft.Azure.Commands.RecoveryServices.ARSVault

## NOTES
Get-AzRecoveryServicesVault dalam versi lama Az.RecoveryServices(<=2.10.0) tidak dapat bekerja dengan Az.Accounts(>=1.8.1) karena referensi rakitan yang salah. Modul Az.RecoveryServices perlu ditingkatkan ke 2.11.0 atau yang lebih baru jika Anda menggunakan Az atau Az.Accounts terbaru.

## RELATED LINKS

[Get-AzRecoveryServicesVaultSettingsFile](./Get-AzRecoveryServicesVaultSettingsFile.md)

[New-AzRecoveryServicesVault](./New-AzRecoveryServicesVault.md)

[Remove-AzRecoveryServicesVault](./Remove-AzRecoveryServicesVault.md)
