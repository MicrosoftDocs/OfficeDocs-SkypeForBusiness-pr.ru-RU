
Как и для любой учетной записи Microsoft 365, срок действия пароля только что созданной учетной записи ресурса автоматически истекает через некоторое время. Однако если срок действия пароля учетной записи ресурса истек, Комнаты Teams устройство, на которое он выполнил вход, не сможет снова войти в систему с датой окончания срока действия. 

Чтобы избежать необходимости сброса пароля учетной записи ресурса и повторного входа в каждый Комнаты Teams устройства, можно отключить срок действия пароля для учетной записи.
  
> [!NOTE]
> Установка **бессрости пароля является** требованием для общих устройств Microsoft Teams. Если правила домена запрещают пароли, срок действия которых не истекает, необходимо создать исключение для каждой учетной записи ресурса устройства Teams.

Чтобы отключить срок действия пароля, выполните действия, описанные на одной из следующих вкладок:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Сначала подключитесь к Active Directory PowerShell:

```PowerShell
   Connect-AzureAD
```

Затем см. раздел ["Установка бессрости пароля"](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Подключитесь к MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Дополнительные сведения об Active Directory см. [в статье Об Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)

2. Задайте для пароля значение "Никогда не истекает", используя следующий синтаксис:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (локальная среда)**](#tab/active-directory1-password/)

1. Подключитесь к Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Дополнительные сведения об Active Directory PowerShell см. в [разделе ActiveDirectory](/powershell/module/activedirectory).

2. Задайте для пароля значение "Никогда не истекает", используя следующий синтаксис:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    В этом примере пароль для учетной записи ConferenceRoom01@contoso.com срок действия не истекает.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---