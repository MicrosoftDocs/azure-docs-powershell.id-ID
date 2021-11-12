---
external help file: Microsoft.Azure.Commands.AzureBackup.dll-Help.xml
Module Name: AzureRM.Backup
ms.assetid: F3774658-A5E4-40BE-9A85-B33C70BC0A09
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.backup/get-azurermbackupcontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBackup/Commands.AzureBackup/help/Get-AzureRmBackupContainer.md
ms.openlocfilehash: abc4bce43c5be267e736cb93e03806cdd802fcb0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424322"
---
# Get-AzureRmBackupContainer

## SYNOPSIS
Mendapatkan wadah Cadangan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmBackupContainer [-Name <String>] -Type <AzureBackupContainerType>
 [-ManagedResourceGroupName <String>] [-Status <AzureBackupContainerRegistrationStatus>]
 [-Vault] <AzureRMBackupVault> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBackupContainer** mendapatkan wadah Azure Backup.

**AzureBackupContainer** encapsulates sumber data, item yang diproteksi, dan titik pemulihan.
**AzureBackupContainer** dapat menjadi salah satu dari yang berikut: 

- Komputer Windows Server
- Server System Center Data Protection Manager (SCDPM) 
- Infrastruktur Azure sebagai mesin virtual layanan (IaaS)

Sebelum Pencadangan dapat mencadangkan sumber data atau item, Anda harus mendaftarkan wadah yang menyimpannya dengan layanan Azure Backup.
Wadah harus diautentikasi untuk mengirimkan data cadangan ke vault Cadangan.
Untuk Windows Server dan server SCDPM, pendaftaran dilakukan dengan nama domain server yang sepenuhnya memenuhi syarat.

## EXAMPLES

### Contoh 1: Menampilkan semua server yang terdaftar di vault
```
PS C:\>$Vault = Get-AzureRmBackupVault -Name "Vault03"
PS C:\> Get-AzureRmBackupContainer -Vault $Vault -Type Windows
Name                         Type               Status
----                         ----               ------
SERVER01.CONTOSO.COM          Windows            Registered
SERVER02.CONTOSO.COM          Windows            Registered
```

Perintah pertama mengambil vault bernama Vault03 menggunakan cmdlet **Get-AzureRmBackupVault.**
Perintah menyimpan objek tersebut dalam $Vault variabel.

Perintah kedua berisi semua wadah tipe Windows dari vault di $Vault.

### Contoh 2: Mendapatkan wadah tertentu
```
PS C:\>Get-AzureRmBackupContainer -Vault $Vault -Type SCDPM -Name "DPMSERVER.CONTOSO.COM"
Name                         Type               Status
----                         ----               ------
DPMSERVER.CONTOSO.COM        SCDPM              Registered
```

Perintah ini mendapatkan wadah bernama DPMSERVER. CONTOSO.COM.
Perintah menentukan vault dalam $Vault dan tipe wadah.

### Contoh 3: Menampilkan semua mesin virtual Azure yang terdaftar
```
PS C:\>Get-AzureRmBackupContainer -Vault $Vault -Type AzureVM -Status Registered 
Name                         Type               Status
----                         ----               ------
co03-vm                      AzureVM            Registered
```

Perintah ini mendapatkan mesin virtual terdaftar dari vault di $Vault.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedResourceGroupName
Menentukan nama grup sumber daya yang terkait dengan wadah tersebut.
Nama ini adalah nilai yang sama dengan yang Anda tentukan *untuk* parameter *ServiceName atau ResourceGroupName* Register-AzureRmBackupContainer cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama wadah yang akan didaangkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status kontainer saat ini yang akan didaangkan cmdlet ini.
Nilai yang dapat diterima untuk parameter ini adalah:

- NotRegistered 
- Terdaftar 
- Mendaftar

```yaml
Type: AzureBackupContainerRegistrationStatus
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
Menentukan tipe wadah yang akan didaurkan cmdlet ini.

```yaml
Type: AzureBackupContainerType
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
Menentukan penyimpanan Cadangan tempat cmdlet ini mendapatkan wadah.
Untuk mendapatkan **AzureRmBackupVault,** gunakan cmdlet Get-AzureRmBackupVault cmdlet.

```yaml
Type: AzureRMBackupVault
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### AzureBackupVault

## OUTPUTS

### AzureBackupContainer

## CATATAN
* Tidak ada

## RELATED LINKS

[Get-AzureRmBackupVault](./Get-AzureRmBackupVault.md)

[Register-AzureRmBackupContainer](./Register-AzureRmBackupContainer.md)

[Unregister-AzureRmBackupContainer](./Unregister-AzureRmBackupContainer.md)


