---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A9754159-420F-412A-B2EA-17E29B43D611
---

# Remove-AzureKeyVaultKey

## SYNOPSIS
Deletes a key in a vault.

## SYNTAX

```
Remove-AzureKeyVaultKey [-VaultName] <String> [-Name] <String> [-Force] [-PassThru] [-Profile <AzureProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureKeyVaultKey** cmdlet deletes a key in an Azure Key Vault.
This cmdlet has a value of high for the **ConfirmImpact** property.

## EXAMPLES

### Example 1: Remove a key from a vault
```
PS C:\>Remove-AzureKeyVaultKey -VaultName "Contoso" -Name "ITSoftware"
```

This command removes the key named ITSoftware from the vault named Contoso.

### Example 2: Remove a key without user confirmation
```
PS C:\>Remove-AzureKeyVaultKey -VaultName "Contoso" -Name "ITSoftware" -Force -Confirm:$False
```

This command removes the key named ITSoftware from the vault named Contoso.
The command specifies the *Force* and *Confirm* parameters, and, therefore, the cmdlet does not prompt you for confirmation.

### Example 3: Remove keys by using the pipeline operator
```
PS C:\>Get-AzureKeyVaultKey -VaultName "Contoso" | Where-Object {$_.Attributes.Enabled -eq $False} | Remove-AzureKeyVaultKey
```

This command gets all the keys in the vault named Contoso, and passes them to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet passes the keys that have a value of $False for the **Enabled** attribute to the current cmdlet.
That cmdlet removes those keys.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Specifies the name of the key to remove.
This cmdlet constructs the fully qualified domain name (FQDN) of a key based on the name that this parameter specifies, the name of the vault, and your current environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KeyName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a **Microsoft.Azure.Commands.KeyVault.Models.KeyBundle** object.
By default, this cmdlet does not generate any output.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Specifies the name of the vault from which to remove the key.
This cmdlet constructs the FQDN of a vault based on the name that this parameter specifies and your current environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.KeyBundle
This cmdlet returns a value only if you specify the *PassThru* parameter.

## NOTES

## RELATED LINKS

[Add-AzureKeyVaultKey](./Add-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](./Get-AzureKeyVaultKey.md)

[Set-AzureKeyVaultKeyAttribute](./Set-AzureKeyVaultKeyAttribute.md)


