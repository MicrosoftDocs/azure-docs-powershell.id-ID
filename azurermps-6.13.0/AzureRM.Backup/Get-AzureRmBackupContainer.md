---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: F3774658-A5E4-40BE-9A85-B33C70BC0A09
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupContainer.md
ms.openlocfilehash: e20276d8a2dfec8ffb39665e5122cfe4be74dc42
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142282651"
---
# Get-AzureRmBackupContainer

## SYNOPSIS
Mendapatkan pencadangan kontainer.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupContainer [-Name <String>] -Type <AzureBackupContainerType>
 [-ManagedResourceGroupName <String>] [-Status <AzureBackupContainerRegistrationStatus>]
 [-Vault] <AzureRMBackupVault> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupContainer mendapatkan kontainer** Azure Backup.
**AzureBackupContainer** merangkum sumber data, item yang diproteksi, dan titik pemulihan.
**AzureBackupContainer** dapat berupa salah satu hal berikut ini: 
- Komputer Server Windows
- Server Manajer Perlindungan Data Pusat Sistem (SCDPM, System Center Data Protection Manager) 
- Mesin virtual Azure infrastructure as a service (IaaS) Sebelum Backup dapat mencadangkan sumber data atau item, Anda harus mendaftarkan wadah yang menampungnya dengan layanan Azure Backup.
Kontainer harus diautentikasi untuk mengirim data cadangan ke kubah Cadangan.
Untuk komputer server Windows dan server SCDPM, pendaftaran diadakan dengan nama domain server yang sepenuhnya memenuhi syarat.

## EXAMPLES

### Contoh 1: Menampilkan semua server yang terdaftar ke kubah
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> Get-AzureRmBackupContainer -Vault $Vault -Type Windows
Name                         Type               Status
----                         ----               ------
SERVER01.CONTOSO.COM          Windows            Registered
SERVER02.CONTOSO.COM          Windows            Registered
```

Perintah pertama mendapatkan kubah bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault** .
Perintah menyimpan objek tersebut dalam variabel $Vault.
Perintah kedua mendapatkan semua wadah tipe Windows dari kubah di $Vault.

### Contoh 2: Mendapatkan wadah tertentu
```
PS C:\>Get-AzureRmBackupContainer -Vault $Vault -Type SCDPM -Name "DPMSERVER.CONTOSO.COM"
Name                         Type               Status
----                         ----               ------
DPMSERVER.CONTOSO.COM        SCDPM              Registered
```

Perintah ini mendapatkan wadah bernama DPMSERVER. CONTOSO.COM.
Perintah menentukan kubah dalam $Vault dan tipe wadah.

### Contoh 3: Menampilkan semua mesin virtual Azure yang terdaftar
```
PS C:\>Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Status Registered 
Name                         Type               Status
----                         ----               ------
co03-vm                      AzureVM            Registered
```

Perintah ini mendapatkan mesin virtual terdaftar dari kubah di $Vault.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedResourceGroupName
Menentukan nama grup sumber daya yang terkait dengan wadah.
Nama ini adalah nilai yang sama dengan yang Anda tentukan untuk parameter *ServiceName* atau *ResourceGroupName* cmdlet Register-AzureRmBackupContainer.

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

### -Nama
Menentukan nama wadah yang didapat cmdlet ini.

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

### -Status
Menentukan status kontainer saat ini yang didapatkan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- NotRegistered 
- Terdaftar 
- Mendaftar

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureBackupContainerRegistrationStatus
Parameter Sets: (All)
Aliases:
Accepted values: Registered, Registering, NotRegistered

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe wadah yang didapat cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureBackupContainerType
Parameter Sets: (All)
Aliases:
Accepted values: Windows, SCDPM, AzureVM, AzureBackupServer, Other

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Menentukan kubah Cadangan tempat cmdlet ini mendapatkan kontainer.
Untuk mendapatkan **AzureRmBackupVault**, gunakan cmdlet Get-AzureRmBackupVault.

```yaml
Type: Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupVault
Parameter: Vault (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.AzureBackup.Models.AzureRMBackupContainer

## CATATAN
* Tidak

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Daftarkan-AzureRmBackupContainer](./Register-AzureRmBackupContainer.md)

[Batalkan pendaftaran-AzureRmBackupContainer](./Unregister-AzureRmBackupContainer.md)


