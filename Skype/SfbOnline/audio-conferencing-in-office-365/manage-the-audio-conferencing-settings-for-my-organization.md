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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'В статье Skype для бизнеса Online вы можете назначать лицензии для конференц-связи с телефонным подключением и ИДЕНТИФИКАТОРом конференции для пользователя и многих других параметров конференц-связи с телефонным подключением. '
ms.openlocfilehash: e699cf51f3a9366cdd86004e48eeb18235849680
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494249"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Управление параметрами аудиоконференций организации в Skype для бизнеса Online

> [!NOTE]
> Для получения информации о том, как управлять этими параметрами с помощью Microsoft Teams, см. [Управление параметрами аудиоконференций для организаций в Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Вы сможете более легко увидеть все настройки голосовой конференции Skype для бизнеса в одном приложении.


## <a name="assign-an-audio-conferencing-license"></a>Назначение лицензии на аудиоконференцию

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Назначение лицензии для пользователя**

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. В левой области навигации **центра администрирования Office 365**перейдите в раздел **Пользователи** > :**Активные**пользователи, а затем выберите пользователя или пользователей из списка доступных пользователей.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Включение и отключение электронных писем, отправляемых пользователям голосовой конференции

![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса**

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2.  > Перейдите в **центр администрирования Office 365**в**Skype для бизнеса** и на панели навигации слева выберите пункт **звуковые конференции**.

3. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.

4. Нажмите кнопку **Сохранить**.

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**

- You can also use the Windows PowerShell and run:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    С помощью [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) можно управлять другими параметрами организации, включая электронную почту.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Изменение контактных данных отправителя в сообщениях электронной почты, отправляемых пользователям

You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:

- Введите адрес электронной почты в параметре _сендемаилфромаддресс_ .

- Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.

- Присвойте параметру _SendEmailOverride_ значение _True_.

Если вы хотите изменить адрес электронной почты, вам нужно убедиться, что политика входящих сообщений организации позволяет получать письма, отправленные с настроенного адреса электронной почты.

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Чтобы изменить адрес электронной почты, нужно убедиться в том, что применяемая организацией политика входящих сообщений позволяет принимать сообщения, отправленные с настраиваемого адреса электронной почты.

Вы можете использовать командлет [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) для управления другими настройками организации, включая электронную почту.

Просмотр [сообщений, которые автоматически отправляются пользователям при изменении параметров голосовой конференции](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Войдите в Office 365 под своей учебной или рабочей учетной записью.

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.

3. На панели навигации слева в **центре администрирования Skype для бизнеса** перейдите к секции **Аудиоконференции** и на панели действий в области**Идентификатор конференции** нажмите на кнопку **Сброс**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2.  > Перейдите в **центр администрирования Office 365**в**Skype для бизнеса** и на панели навигации слева выберите пункт **звуковые конференции**.

3. Нажмите кнопку **Пользователи**, а затем выберите пользователя, для которого вы хотите сбросить PIN-код.

4. На панели действий в разделе **ПИН-код**нажмите кнопку **Сброс**.

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

Посмотрите [, как сбросить ПИН-код голосовых конференций](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Отправка пользователю сообщения электронной почты с данными голосовой конференции

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2.  > Перейдите в **центр администрирования Office 365**в**Skype для бизнеса** и на панели навигации слева выберите пункт **звуковые конференции**.

3. Нажмите кнопку **Пользователи**, а затем выберите пользователя, для которого вы хотите сбросить PIN-код.

4. На панели действий щелкните **Отправить информацию о конференции по электронной почте**.

    > [!NOTE]
    > После этого ПИН-код для голосовой конференции не отправляется пользователю.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Настройка номеров телефонов, включенных в приглашения

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. На панели «Действия» можно указать **Платный номер** и, если разрешено, **Бесплатный номер**.

5. Нажмите кнопку **Сохранить**.

Ознакомьтесь [с разделами Настройка номеров телефонов, включенных в приглашения](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Выбор параметров моста аудиоконференций

**Настройка процесса собрания, когда абоненты присоединяются к собранию**


1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите к **центру администрирования Office 365** > **Skype для бизнеса**.

3. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста**видеоконференций **** > Microsoft.

4. В разделе **Присоединение к собранию**выберите указанные ниже действия.

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     Это может быть задано для каждого собрания, когда пользователь присоединяется к собранию с помощью приложения Skype для бизнеса, и при **входе или выходе** пользователей из него в меню **параметров** собрания Skype на собрании вы можете изменить параметр объявлять.

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. См. статью **Изменение параметров моста аудиоконференций**.
    
Ознакомьтесь [с разрешениями изменение параметров для моста](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)видеоконференций.
  
 **Установка длины ПИН-кода для собраний**

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите к **центру администрирования Office 365** > **Skype для бизнеса**.

3. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста**видеоконференций **** > Microsoft.

4. В разделе **Безопасность**введите нужное количество цифр для ПИН-кода в списке **длина ПИН** -кода и нажмите кнопку **сохранить**.

    The PIN must be between 4 and 12 digits. The default is 5.
    
Ознакомьтесь [с разрешениями изменение параметров для моста](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)видеоконференций.
  
 **Включение и отключение отправки электронной почты пользователям с аудио**

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2.  > Перейдите в **центр администрирования Office 365**в**Skype для бизнеса** и на панели навигации слева выберите пункт **звуковые конференции**.

3. На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.

4. Нажмите кнопку **Сохранить**.

    Кроме того, вы можете отправлять электронную почту пользователю с помощью параметров голосовой конференции, перейдя к свойствам голосовой конференции пользователя и выбрав команду **отправить сведения о конференции по электронной почте**.

    В этом случае, пользователям отправляются сообщения, содержащие идентификатор конференции и номер телефона, но не включающие в себя ПИН-код.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Просмотр и установка основных (по умолчанию) и дополнительных (альтернативных) языков для моста голосовой конференц-связи


1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.

3. В **центре администрирования Skype для бизнеса**на панели навигации слева выберите пункт "звуковые **конференции**", а затем — **Microsoft Bridge**.

4. Выберите номер телефона в списке, нажмите кнопку **задать языки** на панели действий, а затем на странице Set Languages ( **настроить языки** ) нажмите кнопку использовать **основной язык** , чтобы просмотреть полный список поддерживаемых языков.

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Просмотр номеров для телефонной конференции

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Просмотрите номера телефонов, заданные в Office 365, которые будут использоваться для голосовой конференции.

   - Просмотрите расположение и основной и дополнительный языки, которые будут использоваться автосекретарем по голосовой конференции.

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

Вы можете перейти в раздел**Пользователи** **голосовой конференции** > и выбрать свойства пользователя, чтобы изменить номер по умолчанию для пользователя, выбрав новый номер из списка номеров, доступных в вашей организации.

Посмотрите [список номеров звуковых конференций](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Войдите в Office 365 под своей учебной или рабочей учетной записью.

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.

3. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите в раздел видеоконференции _гт_ и нажмите **Пользователи**. ****

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

Ниже указаны параметры на уровне Организации.

- **Настройка уведомлений о входе и выходе** Значением по умолчанию является _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Настройка записи имени** Значением по умолчанию является _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Настройка длины ПИН-кода** Значение по умолчанию равно 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Настройка с телефона только для собраний с телефонным подключением** Значением по умолчанию является _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Настройки отправки сообщений пользователям** Значением по умолчанию является _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Настройка отправки сообщений с другой учетной записи** Значением по умолчанию является _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Настройка адреса отправителя в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Настройка имени, отображаемого в сообщениях, отправляемых пользователям** Значением по умолчанию является _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell
- Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Статьи по теме

[Управление настройками аудиоконференции для пользователя](manage-the-audio-conferencing-settings-for-a-user.md)


