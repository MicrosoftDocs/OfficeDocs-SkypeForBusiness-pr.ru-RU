---
title: Развертывание комнаты Microsoft Teams в локальной среде Exchange
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в гибридной среде с локальным сервером Exchange.
ms.openlocfilehash: c361b6f09bd3acbdf6d8448d168798306cc49ff8
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573510"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Развертывание комнаты Microsoft Teams в локальной среде Exchange

В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в гибридной среде с Exchange для локальных и Microsoft Teams или Skype для бизнеса Online.
  
Если в вашей организации есть смесь служб, а некоторые размещены в локальной сети, а некоторые — в Интернете, ваша конфигурация будет зависеть от того, где размещена каждая служба. В этой статье рассказывается о гибридных развертываниях комнат Microsoft Teams с размещенным на локальном сервере Exchange. Так как в этом типе развертывания существует множество различных вариантов, невозможно предоставить подробные инструкции для всех. Для многих конфигураций будет работать следующий процесс. Если вы не можете выполнить процесс настройки, мы рекомендуем использовать Windows PowerShell, чтобы получить тот же самый конечный результат, который вы описывали здесь, и для других вариантов развертывания.

Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams. Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.
  
## <a name="requirements"></a>Требования

Перед развертыванием комнат Microsoft Teams на локальном сервере Exchange убедитесь, что вы удовлетворены требованиями. Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).
  
При развертывании комнат Microsoft Teams на локальном сервере Exchange вы будете использовать средства администрирования Active Directory для добавления адреса электронной почты для локальной учетной записи домена. Эта учетная запись будет синхронизирована с Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизируйте ее с Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначение лицензии на Office 365.

- Включите учетную запись устройства в Skype для бизнеса Server. Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.

  - Вам потребуется Skype для бизнеса Online (план 2) или более позднюю версию в плане Office 365. План должен поддерживать функции конференц-связи.
  
  - - Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для комнат Microsoft Teams, которым нужен Skype для бизнеса Online (план 3).
  
  - - Ваши пользователи клиента должны иметь почтовые ящики Exchange.
  
  - - Для вашей учетной записи Microsoft Team комнат требуется лицензия Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), но для нее не требуется лицензия на Exchange Online.

- Назначьте лицензию Skype для бизнеса Server учетной записи комнат Microsoft Teams.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Создание учетной записи и ее синхронизация с Active Directory

1. В средстве " **Пользователи и компьютеры Active Directory** " щелкните правой кнопкой мыши папку или подразделение, в котором будут создаваться учетные записи Microsoft Teams, и нажмите кнопку " **создать**", а затем выберите пункт " **пользователь**".

2. Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор **срока действия пароля неограничен** — требование для сервера Skype для бизнеса в комнатах Microsoft Teams. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. Если это так, вам потребуется создать исключение для каждой учетной записи устройства Microsoft Teams в комнатах.
  
4. После создания учетной записи выполните синхронизацию каталогов. По завершении перейдите на страницу пользователи в центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная в предыдущих шагах, объединена в Интернет.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте консоль управления Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) или [подключитесь к серверу Exchange с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. В Exchange PowerShell можно создать почтовый ящик для учетной записи (почтовый ящик — включение учетной записи), выполнив следующую команду:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Включение и использование почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. В Exchange PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:

   - Аутоматепроцессинг: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)

   - Аддорганизертосубжект: $false (Организатор собрания не добавляется в тему приглашения на собрание.)

   - Делетекомментс: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)

   - Делетесубжект: $false (сохранить тему приглашений на входящие собрания).

   - Ремовеприватепроперти: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)

   - Аддаддитионалреспонсе: $true (текст, указанный в параметре Аддитионалреспонсе, добавляется в приглашения на собрание.)

   - Аддитионалреспонсе: "это комната для собраний Skype!" (Дополнительный текст, добавляемый в приглашение на собрание.)

   Этот пример настраивает эти параметры в почтовом ящике комнаты с именем Project-Рижел-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-календарпроцессинг](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Подключитесь к Azure Active Directory. Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается. 

2. Учетная запись устройства должна иметь действительную лицензию на Office 365, или Exchange и Microsoft Teams не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Получение списка доступных SKU.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Затем вы можете добавить лицензию с помощью`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Включение учетной записи устройства

Skype для бизнеса Online PowerShell используется для управления службами как в Microsoft Teams, так и в Skype для бизнеса Online.

1. Создайте удаленный сеанс Windows PowerShell на компьютере, выполнив указанные ниже действия.

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Получите SIP Address для учетной записи:

  ``` Powershell
   $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
   ```

3. Чтобы включить учетную запись комнаты Microsoft Teams, выполните следующую команду:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Если вы не знаете, какое значение использовать для параметра Регистрарпул в вашей среде, вы можете получить значение от существующего пользователя с помощью этой команды:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии для учетной записи комнат Microsoft Teams

1. Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, чтобы изменить данные учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Если вы хотите использовать корпоративную голосовую связь в комнатах Microsoft Teams, вам придется использовать лицензию на план 3.
6. Нажмите кнопку **Сохранить**.

Для проверки подлинности вы можете использовать любой клиент для входа в эту учетную запись.
  
## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат Microsoft Teams](room-systems-v2-configure-accounts.md)

[Планирование комнат Microsoft Teams](skype-room-systems-v2-0.md)
  
[Развертывание комнат Microsoft Teams](room-systems-v2.md)
  
[Настройка консоли Microsoft Teams](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
