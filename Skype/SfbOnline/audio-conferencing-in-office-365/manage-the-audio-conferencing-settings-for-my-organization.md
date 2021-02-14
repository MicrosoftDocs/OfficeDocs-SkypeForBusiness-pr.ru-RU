---
title: Управление параметрами аудиоконференций организации в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'См. по шагам Skype для бизнеса Online, чтобы назначить пользователю лицензию на конференц-вызов и ИД конференции, а также другие параметры конференц-зала. '
ms.openlocfilehash: aa8e9cbaf063ebf1780e3f8ce45b7bd54ced474f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164148"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Управление параметрами аудиоконференций организации в Skype для бизнеса Online

> [!NOTE]
> Для получения информации о том, как управлять этими параметрами с помощью Microsoft Teams, см. [Управление параметрами аудиоконференций для организаций в Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Возможно, вам будет проще увидеть все параметры аудиоконференции для Skype для бизнеса в одном месте.


## <a name="assign-an-audio-conferencing-license"></a>Назначение лицензии на аудиоконференцию

> [!NOTE]
> В Центре администрирования Skype для бизнеса нельзя **назначать лицензии.** Необходимо использовать Центр администрирования Microsoft 365. См. ["Назначение лицензий Skype для бизнеса".](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

 **Назначение лицензии пользователю**

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. В левой области навигации Центра администрирования перейдите к списку "Пользователи активных пользователей", а затем выберите пользователя или пользователей из списка  >  доступных.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> После назначения лицензии Майкрософт может не отображаться в списке в качестве поставщика аудиоконференций. В этом случае выйдите из Центра администрирования или нажмите CTRL+F5, чтобы обновить окно браузера.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Включить или отключить сообщения электронной почты, отправленные пользователям аудиоконференции

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > Skype для бизнеса **и** на левой навигации щелкните "Аудиоконференция". 

3. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.

4. Щелкните **Сохранить**.

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**

- You can also use the Windows PowerShell and run:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    С помощью [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) можно управлять другими настройками для организации, включая электронную почту.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Изменение контактных данных отправитель в сообщениях электронной почты, отправляемых пользователям

Вы можете внести изменения в электронные письма, которые автоматически отправляются пользователям, включая фактический адрес электронной почты и отображаемую информацию о контактных данных отправщика. По умолчанию отправитель электронных писем — Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell [и cmdlet Set-CsOnlineDialInConferencingTenantSettings.](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Чтобы изменить адрес электронной почты, отправляемый пользователям, необходимо:

- Введите адрес электронной почты в параметр _SendEmailFromAddress._

- Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.

- Присвойте параметру _SendEmailOverride_ значение _True_.

Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Чтобы изменить адрес электронной почты, нужно убедиться в том, что применяемая организацией политика входящих сообщений позволяет принимать сообщения, отправленные с настраиваемого адреса электронной почты.

Для управления другими настройками для организации, включая электронную почту, можно использовать [cmdlet Set-CsOnlineDialInConferencingTenantSettings.](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

См. [электронные письма, которые автоматически отправляются пользователям](emails-sent-to-users-when-their-settings-change.md)при изменении параметров аудиоконференции.

## <a name="reset-the-meeting-conference-id"></a>Войдите в Office 365 под своей учебной или рабочей учетной записью.

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. На панели навигации слева в **центре администрирования Skype для бизнеса** перейдите к секции **Аудиоконференции** и на панели действий в области **Идентификатор конференции** нажмите на кнопку **Сброс**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > Skype для бизнеса **и** на левой навигации щелкните "Аудиоконференция". 

3. Щелкните **"Пользователи"** и выберите пользователя, для который вы хотите сбросить ПИН-код.

4. На области действий в области **"ПИН-код"** нажмите кнопку **"Сброс".**

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

См. ["Сброс ПИН-кода аудиоконференции".](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > Skype для бизнеса **и** на левой навигации щелкните "Аудиоконференция". 

3. Щелкните **"Пользователи"** и выберите пользователя, для который вы хотите сбросить ПИН-код.

4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.

    > [!NOTE]
    > При этом ПИН-код аудиоконференции не отправляется пользователю.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Настройка номеров телефонов, включенных в приглашения

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. На панели «Действия» можно указать **Платный номер** и, если разрешено, **Бесплатный номер**.

5. Щелкните **Сохранить**.

См. ["Настройка номеров телефонов, включенных в приглашения".](set-the-phone-numbers-included-on-invites.md)


## <a name="choosing-audio-conferencing-bridge-settings"></a>Выбор параметров моста аудиоконференций

**Настройка окна собрания, когда звоня люди присоединяются к собранию**


1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**

4. В **области "Присоединиться к собранию"** выберите следующие действия:

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     Этот параметр можно настроить на основе собраний, когда пользователь присоединяется к собранию с  помощью приложения Skype для бизнеса  и может изменить параметр "Объявлять" при входе или выходе пользователей в меню параметров собрания Skype.

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. См. статью **Изменение параметров моста аудиоконференций**.
    
См. [статью "Изменение параметров моста аудиоконференций".](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Настройка длины ПИН-кода для собраний**

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**

4. В **области "Безопасность"** введите в списке  длины ПИН-кода нужное количество цифр и нажмите кнопку **"Сохранить".**

    The PIN must be between 4 and 12 digits. The default is 5.
    
См. [статью "Изменение параметров моста аудиоконференций".](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Включить или отключить отправку электронной почты пользователям аудиосвязи**

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > Skype для бизнеса **и** на левой навигации щелкните "Аудиоконференция". 

3. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.

4. Щелкните **Сохранить**.

    Вы также можете отправить сообщение электронной почты пользователю с помощью параметров аудиоконференции, щелкнув ссылку "Отправить сведения о конференции по электронной почте".

    В этом случае, пользователям отправляются сообщения, содержащие идентификатор конференции и номер телефона, но не включающие в себя ПИН-код.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>См. и установите основной (по умолчанию) и дополнительный (альтернативный) языки на мосте аудиоконференции


1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В Центре **администрирования Skype** для бизнеса на левой навигации перейдите к аудиоконференции **и** выберите мост **Microsoft.**

4. Выберите номер телефона в списке, щелкните "Выбрать языки"  в области действий,  а затем на странице "Выбор языков" щелкните список "Использовать основной язык", чтобы просмотреть полный список поддерживаемых языков. 

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>См. номера для аудиоконференции с телефонным номером

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**
 
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Просмотр телефонных номеров, которые настроены Microsoft 365 или Office 365 для использования для аудиоконференции.

   - Просмотр местоположения, основного и дополнительных языков, который будет использовать автофиденс аудиоконференции.

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

Вы можете перейти на сайт "Пользователи аудиоконференции" и выбрать свойства пользователя, чтобы изменить номер по умолчанию для пользователя, выбрав новый номер в списке номеров, доступных в вашей  >   организации.

См. список номеров для [аудиоконференций.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>Войдите в Office 365 под своей учебной или рабочей учетной записью.

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В Центре **администрирования Skype** для бизнеса на  левой навигации перейдите в меню "Аудиоконференция" и> **"Пользователи".**

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

Ниже параметров на уровне организации.

- **Настройка уведомлений о входе и выходе** Значением по умолчанию является _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Настройка записи имени** Значением по умолчанию является _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Настройка длины ПИН-кода** Значение по умолчанию равно 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Настройка с телефона только для собраний с телефонным подключением** Значением по умолчанию является _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Настройки отправки сообщений пользователям** Значением по умолчанию является _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Настройка отправки сообщений с другой учетной записи** Значением по умолчанию является _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Настройка адреса отправителя в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Настройка имени, отображаемого в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell
- Windows PowerShell все о том, как управлять пользователями, а также о том, какие пользователи разрешены или не разрешены. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, см. указанные здесь разделы.

  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих темах:

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Статьи по теме

[Управление настройками аудиоконференции для пользователя](manage-the-audio-conferencing-settings-for-a-user.md)


