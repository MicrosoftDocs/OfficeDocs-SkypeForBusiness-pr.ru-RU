
Для Комнаты Microsoft Teams устройства требуется собственная учетная запись ресурса. Учетная запись ресурса — это учетная запись, в Комнаты Teams которой устройство выполняет вход, и это учетная запись, в которой пользователи в организации приглашены на резервную запись комнаты Teams.

При создании почтового ящика ресурса можно указать, следует ли разрешать повторяющиеся собрания, автоматически принимать приглашения в комнату, сколько дней в будущем принимать приглашения и т. д.

> [!TIP]
> При именовании учетных записей ресурсов рекомендуется использовать стандартное соглашение об именовании в начале адреса электронной почты. Это поможет создать динамические группы для упрощения управления в Azure Active Directory. Например, можно использовать mtr-для всех учетных записей ресурсов, которые будут связаны с Комнаты Microsoft Teams.

> [!TIP]
> Рекомендуется создать все учетные записи ресурсов с помощью Exchange Online и Azure Active Directory.

Создайте учетную запись ресурса с помощью метода на одной из следующих вкладок:

#### <a name="in-microsoft-365-admin-center"></a>[**В Центр администрирования Microsoft 365**](#tab/m365-admin-center)

1. Войдите в Центр администрирования Microsoft 365.

2. Укажите учетные данные администратора для клиента Microsoft 365.

3. Перейдите **к разделу "** Ресурсы" на панели слева, а затем **выберите "Комнаты& оборудование.** Если эти параметры недоступны на левой панели, может потребоваться сначала выбрать **"Показать все** ".

4. Выберите **"Добавить ресурс** ", чтобы создать учетную запись ресурса. Введите отображаемое имя и адрес электронной почты для учетной записи, а затем нажмите кнопку **"Сохранить"**.

5. По умолчанию учетные записи ресурсов настраиваются со следующими параметрами:

    - Разрешить повторяющиеся собрания
    - Автоматическое отклонение собраний за пределами следующих ограничений
      - Окно резервирования (в днях): 180
      - Максимальная длительность (часы): 24
    - Автоматическое принятие приглашений на собрания

    Если вы хотите изменить их, выберите " **Изменить параметры резервирования** ", прежде чем нажмем кнопку **"Закрыть"**. Если вы хотите изменить их позже, перейдите  >  в раздел "Комнаты **ресурсов& оборудование**, выберите учетную запись ресурса. Затем в разделе **"Параметры резервирования**" выберите " **Изменить"**.

6. Перейдите **в раздел "** > Активные **пользователи**" и выберите комнату, которую вы создали, чтобы открыть панель свойств.

7. Затем назначьте пароль учетной записи ресурса. На панели выберите сброс **пароля**.

8. Требование пользователя изменить пароль на общем устройстве приведет к проблемам со входом. Снимите **флажок "Требовать от этого пользователя изменить пароль при первом** входе" и нажмите кнопку **"Сбросить пароль"**.

Вам также может потребоваться применить политики пропускной способности или политики собраний к этой учетной записи. Политики почтовых ящиков можно задать позже.

#### <a name="with-exchange-online"></a>[**С Exchange Online**](#tab/exchange-online)

1. Подключитесь [к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. По умолчанию почтовые ящики помещений не имеют связанных учетных записей. Добавьте учетную запись при создании почтового ящика помещения для проверки подлинности в Microsoft Teams.

    Если вы создаете новый почтовый ящик ресурса:

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    В этом примере создается почтовый ящик помещения со следующими параметрами:

    - Учетная запись: ConferenceRoom01@contoso.com

    - Имя: ConferenceRoom01

    - Псевдоним: ConferenceRoom01

    - Пароль учетной записи: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Если вы используете гибридную конфигурацию Exchange, необходимо добавить адрес электронной почты для учетной записи локального домена. Дополнительные сведения см. в статье ["Синхронизация локальных Office 365 учетных записей](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) пользователей".

#### <a name="with-exchange-server"></a>[**С Exchange Server**](#tab/exchange-server)

  1. Подключитесь к командной консоли Exchange. [Откройте командную консоль Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) [подключитесь к серверу Exchange Server с помощью удаленной оболочки PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

  2. Чтобы создать почтовый ящик помещения:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      В этом примере создается почтовый ящик помещения со следующими параметрами:

      - Учетная запись: ConferenceRoom01@contoso.com

      - Имя: ConferenceRoom01

      - Псевдоним: ConferenceRoom01

      - Пароль учетной записи: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Изменение существующего почтового ящика комнаты Exchange**](#tab/existing-account)

Чтобы изменить существующий почтовый ящик помещения, чтобы он стал учетной записью ресурса, используйте следующий синтаксис:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

В этом примере включается учетная запись для существующего почтового ящика помещения с псевдонимом ConferenceRoom02 и устанавливается пароль 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Если вы используете гибридную конфигурацию Exchange, вам также потребуется добавить адрес электронной почты для локальной учетной записи домена. Дополнительные сведения см. в статье ["Синхронизация локальных Office 365 учетных записей](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) пользователей".

Подробные сведения о синтаксисе и параметрах см. в разделах [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Если вы создаете эту учетную запись для комнат Teams на Surface Hub, необходимо также включить ActiveSync в этой учетной записи. Это позволит отправлять сообщения электронной почты непосредственно с Surface Hub, которые можно использовать для таких функций, как доска. Дополнительные сведения см. в статье "Применение политик [ActiveSync к учетным записям устройств (Surface Hub](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) )".

---

> [!IMPORTANT]
> Если вы используете эту учетную запись ресурса только для резервирования пространства и автоматически принимаете или отклоняете приглашения, настройка завершена. Если вы используете эту учетную запись ресурса для звонков по ТСОП, ознакомьтесь с лицензиями на надстройки [Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , чтобы определить требуемую лицензию.
