---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 1BD296FB-8BFC-473F-951D-D2BF265E50AC
online version: ''
schema: 2.0.0
ms.openlocfilehash: bfe41faa373097fda909d367ede6659c3cb961e9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816444"
---
# Remove-AzureStorSimpleStorageAccountCredential

## SYNOPSIS
Menghapus kredensial akun penyimpanan yang sudah ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifikasiByName
```
Remove-AzureStorSimpleStorageAccountCredential -StorageAccountName <String> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByObject
```
Remove-AzureStorSimpleStorageAccountCredential -SAC <StorageAccountCredentialResponse> [-WaitForComplete]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureStorSimpleStorageAccountCredential** menghapus kredensial akun penyimpanan yang sudah ada.
Tentukan akun berdasarkan nama atau gunakan cmdlet **Get-AzureStorSimpleStorageAccountCredential** untuk mendapatkan objek **StorageAccountCredential** untuk menghapus.

## EXAMPLES

### Contoh 1: Menghapus kredensial akun penyimpanan
```
PS C:\>Remove-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoStorage07" -Force
VERBOSE: ClientRequestId: 8e10d56b-ddb1-459b-b26e-a185f5a303de_PS
VERBOSE: About to create a job to remove your Storage Access Credential! 
VERBOSE: ClientRequestId: 55cb6296-0156-4266-8591-d9e9bf8cc584_PS
982f4b19-ccb0-4ad3-9b02-f8ad25bf2e72
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
982f4b19-ccb0-4ad3-9b02-f8ad25bf2e72 for tracking the task's status
```

Perintah ini menghapus kredensial akun untuk akun penyimpanan bernama ContosoStorage07.
Perintah ini menentukan parameter *Paksa* .
Cmdlet menghapus kredensial tanpa meminta konfirmasi.

### Contoh 2: Menghapus kredensial akun penyimpanan menggunakan operator saluran
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoStorage07" | Remove-AzureStorSimpleStorageAccountCredential -Force -WaitForComplete
VERBOSE: ClientRequestId: f1b46216-bf4c-4c19-8e92-1dfe3894e258_PS
VERBOSE: ClientRequestId: 0d946f8f-c771-4ade-8a83-7c08dad86c52_PS
VERBOSE: ClientRequestId: 2000bab6-8311-4192-ad12-c67e35fc2697_PS
VERBOSE: Storage Access Credential with name ContosoStorage07 found! 
VERBOSE: About to run a job to remove your Storage Access Credential! 
VERBOSE: ClientRequestId: b803b165-bef8-4a8f-9509-4b515ea8bdec_PS
VERBOSE: Your delete operation completed successfully!
```

Perintah ini mendapatkan akun penyimpanan bernama ContosoStorage07 dengan menggunakan cmdlet **Get-AzureStorSimpleStorageAccountCredential** , lalu meneruskan objek tersebut ke cmdlet saat ini.
Cmdlet saat ini menghapus kredensial untuk akun penyimpanan tersebut.
Perintah ini menentukan parameter *WaitForComplete* .
Cmdlet tidak mengembalikan kontrol ke konsol hingga operasi penghapusan selesai.

## PARAMETERS

### -Paksa
Menunjukkan bahwa cmdlet ini tidak meminta konfirmasi kepada Anda.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SAC
Menentukan kredensial, sebagai objek **StorageAccountCredential** , untuk dihapus.
Untuk mendapatkan objek **StorageAccountCredential** , gunakan cmdlet **Get-AzureStorSimpleStorageAccountCredential** .

```yaml
Type: StorageAccountCredentialResponse
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama kredensial akun penyimpanan untuk dihapus.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Menunjukkan bahwa cmdlet ini menunggu operasi selesai sebelum mengembalikan kontrol ke konsol Windows PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### StorageAccountCredential
Cmdlet ini menerima objek **StorageAccountCredential** menggunakan pipeline.

## OUTPUTS

### TaskStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** , jika Anda menentukan parameter *WaitForComplete* .

## CATATAN

## RELATED LINKS

[Get-AzureStorSimpleStorageAccountCredential](./Get-AzureStorSimpleStorageAccountCredential.md)

[New-AzureStorSimpleStorageAccountCredential](./New-AzureStorSimpleStorageAccountCredential.md)

[Set-AzureStorSimpleStorageAccountCredential](./Set-AzureStorSimpleStorageAccountCredential.md)

[Get-AzureStorSimpleJob](./Get-AzureStorSimpleJob.md)


