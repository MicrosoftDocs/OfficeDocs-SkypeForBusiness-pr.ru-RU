---
title: Развертывание Microsoft группами комнат с сервером Exchange при локальном
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: В данном разделе приведены сведения о способах развертывания комнат группами Майкрософт в гибридной среде с сервером Exchange при локальном.
ms.openlocfilehash: 6975d64de9353cb17817c96d18a0bc0c8440602c
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362982"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Развертывание Microsoft группами комнат с сервером Exchange при локальном

В данном разделе приведены сведения о способах развертывания комнат группами Майкрософт в гибридной среде с Exchange на локальную организацию и группами Майкрософт или Скайп для бизнеса в Интернет.
  
Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы. В этом разделе описываются гибридные развертывания для комнат группами Майкрософт с сервером Exchange, размещенных на локальном. Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все. Процесс будет работать для многих конфигураций. Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.

Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей комнат группами Майкрософт. При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства комнат группами Майкрософт.
  
## <a name="requirements"></a>Требования

Перед развертыванием комнат группами Майкрософт с сервером Exchange при локальном убедитесь, что удовлетворены требования. Для получения дополнительных сведений в разделе [requirements комнат группами Майкрософт](requirements.md).
  
При развертывании комнат группами Майкрософт с сервером Exchange при локальном использовании средств администрирования Active Directory для добавления адрес электронной почты для учетной записи домена в локальной. Эта учетная запись будет синхронизирован с Office 365. Выполните указанные ниже действия.
  
- Создайте учетную запись и синхронизируйте ее с Active Directory.

- Включите удаленный почтовый ящик и задайте его свойства.

- Назначение лицензии Office 365.

- Включение учетной записи устройства с Скайп для Business Server. Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.

  - Необходимо иметь Скайп для бизнеса Online (план 2) или более поздней версии в плане Office 365. План должен поддерживать функции конференц-связи.
  
  - - Если вам требуется корпоративной голосовой связи (телефонии PSTN) с помощью службы телефонии для комнат группы Microsoft необходимо Скайп для бизнеса Online (план 3).
  
  - - Клиент пользователи должны иметь почтовые ящики Exchange.
  
  - - Учетной записи Microsoft группами комнат Скайп для бизнеса Online (план 2) и Скайп требуются для бизнеса в Интернет (план 3) лицензии, но не требует лицензии Exchange Online.

- Назначьте Скайп лицензию Business Server для учетной записи Microsoft группами комнат.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Создание учетной записи и ее синхронизация с Active Directory

1. Средства **Active Directory — пользователи и компьютеры** щелкните правой кнопкой мыши папку или подразделение, что вашей комнат группами Майкрософт, учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.

2. Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.

3. Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.

    > [!NOTE]
    > Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server на комнат группами Майкрософт. В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена. Если Да, необходимо создать исключение для каждой учетной записи Microsoft группами комнат устройства.
  
4. После создания учетной записи выполните синхронизацию каталогов. После завершения перейдите на страницу пользователей в центре администрирования Office 365 и убедитесь, что учетной записи, созданной на предыдущих шагах содержащей объединенные в Интернете.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Включите удаленный почтовый ящик и задайте его свойства.

1. [Откройте командную консоль Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) или [подключиться к серверу Exchange server с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. В Exchange PowerShell создавать почтового ящика для учетной записи (почтового ящика включения учетной записи), выполнив следующую команду:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Подробный синтаксис и сведений о параметрах в разделе [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. В Exchange PowerShell настройте следующие параметры на почтовый ящик помещения, чтобы улучшить работу в собрание:

   - AutomateProcessing: AutoAccept (организаторам собрания принимать решение резервирования помещений напрямую без участия: свободен = принять; занят = отклонить.)

   - AddOrganizerToSubject: $false (организатор собрания не добавляется к теме запроса на проведение собрания).

   - DeleteComments: $false (сохранения любого текста в теле сообщения входящих приглашений на собрания).

   - DeleteSubject: $false (Keep темы входящих приглашений на собрания).

   - RemovePrivateProperty: $false (гарантирует пометку "частное", которые были отправлены организатором собрания в исходное приглашение на собрание запросить остается как указано).

   - AddAdditionalResponse: $true (текста, указанного с помощью параметра AdditionalResponse добавляется для приглашений на собрания).

   - AdditionalResponse: «это Скайп конференц-зала!» (Дополнительный текст для добавления в запрос на собрание.)

   В этом примере настраивается эти параметры в почтовый ящик помещения, с именем Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Подробный синтаксис и сведений о параметрах в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Назначение лицензии Office 365

1. Подключитесь к PowerShell Azure Active Directory. Сведения содержатся в разделе [подключение с помощью Azure Active Directory PowerShell для модуля "график"](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

2. Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и группами Майкрософт не будут работать. При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи. Вы можете использовать`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Чтобы получить список доступных номеров SKU.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Теперь можно добавить лицензии с помощью`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> командлет. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).

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

   Подробные сведения содержатся в разделе [Назначение лицензий для учетных записей пользователей с Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Включение учетной записи устройства

Скайп для бизнеса Online PowerShell используется для управления службами для групп Майкрософт и Скайп для бизнеса в Интернет.

1. Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Чтобы включить учетную запись Microsoft группами комнат, выполните следующую команду.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего пользователя с помощью следующей команды:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Назначение лицензии свою учетную запись Microsoft группами комнат

1. Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.
2. Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.
3. Щелкните учетную запись Microsoft группами комнат и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.
4. Щелкните **Лицензии**.
5. В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи. Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать корпоративной голосовой связи на вашей комнат группы Microsoft.
6. Нажмите кнопку **Сохранить**.

Для проверки можно использовать любой клиент для входа в эту учетную запись.
  
## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат группами Майкрософт](room-systems-v2-configure-accounts.md)

[Планирование для групп Майкрософт комнат](skype-room-systems-v2-0.md)
  
[Развертывание групп Майкрософт комнат](room-systems-v2.md)
  
[Настройка консоли комнат группами Майкрософт](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
