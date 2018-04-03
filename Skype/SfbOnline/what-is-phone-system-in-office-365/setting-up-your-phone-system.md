---
title: Setting up Phone System in your organization
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 02/28/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up Phone System (Cloud PBX) for your organization. '
ms.openlocfilehash: a9715797284f08c3d7f2ecbf3ba45a9269a5e0e0
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-phone-system-in-your-organization"></a>Setting up Phone System in your organization

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Step 1: Make sure that Phone System is available in your country or region

1.  First go to [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page. 
2.  Under **Phone System**, review the list of features and details. 
3.  If Phone System is available, go to step 2. 

**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Step 2: Buy and assign Phone System and Calling Plan licenses

To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). If you want to assign multiple users in bulk, see (../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Step 3: Get phone numbers for your users

[] Прежде чем настраивать возможности совершения и получения телефонных звонков для пользователей в организации, необходимо получить для них номера телефонов. 

You have three ways of getting numbers for your users: 
- Get new numbers using the Skype for Business admin center.
- Get new numbers that aren't available in the Skype for Business admin center.
- Перенести или передать существующие номера от вашего текущего поставщика услуг или оператора телефонной связи в Office 365.

Необходимо воспользоваться страницей **Добавление новых пользовательских номеров** для просмотра, поиска, получения и резервирования этих номеров. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users. 

### <a name="get-new-user-phone-numbers"></a>Get new user phone numbers 
  
1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![Add button](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Get new numbers that aren't available in the Skype for Business admin center
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Port or transfer phone numbers from your service provider or phone carrier
  
- Если требуется 999 и менее телефонных номеров, можно использовать мастер **Заказ на перенос нового номера** в центре администрирования Skype для бизнеса. Follow the steps found in [Transfer phone numbers to Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365. 

**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Номера телефонов служб позволяют обслуживать большее число одновременных звонков по сравнению с абонентскими номерами. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Получение новых номеров служб

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.
    
    > [!IMPORTANT] 
    > For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Get new numbers that aren't available in the Skype for Business admin center
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Перенос существующих номеров служб

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Step 5: If you want to set up Calling Plans

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Add emergency addresses and locations for your organization

1. On the **Voice** page, choose **Emergency locations** > **Add new address**.
    
2. Укажите адрес в поле **Новый адрес** и заполните остальные поля.
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Для пользователей из Англии необходимо указать "st" или "th" для названий улиц с номером (как на рисунке выше). 
  
3. Выберите **Проверить**.
    
    При необходимости внесите изменения в адрес. 
    
    > [!CAUTION]
    > На этом этапе проверяется правильность и формат указанного городского адреса или адреса с указанием улицы и здания. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Даже в таком случае сочетание названия города и правильно указанного почтового адреса позволяет диспетчеру направить службы экстренного реагирования по нужному адресу. 
  
    > [!TIP]
    > Если адрес для экстренного реагирования исправлен, отобразится зеленый баннер, уведомляющий о том, что адрес был обновлен. 
  
4. После подтверждения адреса щелкните **Сохранить**.
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Назначьте пользователям номера телефонов и адреса для экстренного реагирования

> [!TIP]
> Если перед выполнением этого шага вы добавили несколько новых пользователей, обратите внимание, что они могут появиться на странице **Пользователи голосовой связи** только спустя **несколько часов**. Это связано с определенной задержкой.
  
1. On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.
    
2. In the Action pane, click **Assign number**.
    
3. On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.
    
4. To select an emergency address, enter name of the city in the box and choose **Search**.
    
    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md). 
  
5. После назначения номера телефона и адреса для обращения в экстренных случаях нажмите **Сохранить**.
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>Сообщить пользователям о своих новых номеров телефонов


Мы рекомендуем использовать для этого электронную почту или другой выбранный вашей компанией способ связи. 

Вот, как он будет видеть этот номер телефона в свои приложения **Скайп для бизнеса** :
  
1. Войдите в приложение Skype для бизнеса на рабочем столе.
    
2. Выберите **Настройки** > **Инструменты** > **Параметры**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Выберите **Телефоны**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
В **Группами Майкрософт**пользователи могут видеть телефонный номер, щелкнув **звонки** в левой панели навигации. The phone number is shown above the dial pad.

![A user can see their number in Microsoft Teams by clicking Calls in the left navigation.](../images/teams-phone-number.png)

**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Step 6: If you want to set up Audio Conferencing

В некоторых случаях пользователям в организации требуется телефон, чтобы присоединиться к собранию. Скайп для бизнеса и группами Майкрософт включить функцию аудиоконференций для только что этой ситуации! Люди могут вызывать в Скайп для бизнеса или группами Майкрософт собраний с помощью телефона, вместо использования Скайп для бизнеса или группами Майкрософт приложения на мобильном устройстве или Компьютере. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).
    
1. If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider: 

    > [!NOTE]
    > Microsoft Teams users can't user a third-party audio conferencing provider. 
  
    - **Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2.  Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
    1. [Настройка приглашения на собрания](../set-up-skype-for-business-online/customize-meeting-invitations.md). Номеру телефона, задайте для пользователя будет автоматически добавляется в приглашения на собрания, отправляемые участникам. Тем не менее можно добавить свои собственные справки и юридических ссылок, текстовое сообщение и рисунок небольшого предприятия.
    
    2. [Набор номера телефона аудиоконференции для организации, которые включены в приглашения на собрания](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). Это номер телефона, который будет отображаться в собрание, запланированное для пользователя.
    
    3. [Задайте auto attendant языков звукового конференц-связи](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) , автосекретаря аудиоконференций для приветствовать абонента, когда они звонить на номер телефона аудиоконференций. Этот шаг применяется только в том случае, если вы используете Microsoft как звука поставщика.
    
    4. [Задать длину ПИН-кода для собраний аудио конференц-связи](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).
    
    > [!NOTE]
    > Этот компонент еще не доступен для клиентов с помощью Office 365 обслуживается 21Vianet в Китае. [Дополнительные сведения об Office 365, которой с 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)Дополнительные сведения см. 

**Дополнительные сведения о аудиоконференции см [звук конференц-связи](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Шаг 7: Если вы хотите настроить очереди вызовов с телефонной системой

Телефонный звонок системы очередей включают приветствие, используемые при получении звонка на номер телефона для вашей организации, возможность автоматически переводить звонки в режим удержания и возможность поиска для следующего агента доступные вызова для обработки вызова при людей, вызов прослушивают музыку при удержании. Можно создать один или несколько очередей звонка для вашей организации.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **Скайп по центру администрирования Business** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер **. Для получения номера службы видеть [Приступая к службе номера телефонов для Скайп для бизнеса и группами Майкрософт](getting-service-phone-numbers.md) или существующий номер службы и передача, см [передачи телефонных номеров в Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Если вы находитесь за пределами США, Скайп по центру администрирования бизнес нельзя использовать для получения номера службы. Перейдите на [Управление телефонные номера для вашей организации](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.

Чтобы создать новую очередь звонка в **Скайп по центру администрирования бизнес**, щелкните **Маршрутизация звонков** > **вызова очередей**, нажмите кнопку **Добавить новый**, а затем следуйте инструкциям, представленным в **шаге 3** - [Создание очереди вызовов с телефонной системой]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**Для получения дополнительных сведений об очередях вызова видеть [Создание очереди вызовов с телефонной системой](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Шаг 8: Если вы хотите настроить телефонной системой, принимаемые автосекретарем

Автосекретари, позволяет людям, вызов для вашей организации и выберите меню системы, чтобы получить их в правом отдел, вызвать очереди, лицо или оператор. Можно создать автосекретарь для вашей организации с помощью Скайп по центру администрирования бизнеса. 

Чтобы создать автосекретарь, Скайп по центру администрирования бизнеса, щелкните **Маршрутизация звонков** > **автосекретари**, нажмите кнопку **Добавить**и затем следуйте инструкциям для каждой страницы в **шаге 2** [Set up auto телефонной системой Автосекретарь](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**Для получения дополнительных сведений о телефонной системой автосекретари видеть [настроить автосекретарь телефонной системой](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Шаг 9: Назначение телефонных номеров (аудиоконференций, очереди вызовов, автосекретари)

После получения номеров службы из **шага 4 над**им необходимо назначить их для каждого типа службы, который будет. Например, если требуется номер телефона выделенной (международную или бесплатная), необходимо назначить номер конференц-канала.

- Для аудиоконференции, можно назначить выделенный номер конференц-канал, перейдя на **центра администрирования Office 365** > **центры администрирования** > **Скайп для бизнеса** > **аудио конференц-связь** и щелкните мост конференции или, достаточно [Изменение международную и обслуживание бесплатных номеров для вашей моста аудиоконференции](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Для автосекретарей, можно назначить выделенного номер автосекретаря, перейдя на **центра администрирования Office 365** > **центры администрирования** > **Скайп для бизнеса** > **Перенаправление звонков** > **Auto автосекретари **и выберите команду автосекретаря. На странице " **Общие** " номер службы, у вас уже есть будет отображаться в поле **номер телефона** раскрывающегося списка. Дополнительные сведения см [настроить автосекретарь телефонной системы](set-up-a-phone-system-auto-attendant.md).

- Для вызова очередей можно назначить выделенный номер очереди вызовов, перейдя на **центра администрирования Office 365** > **центры администрирования** > **Скайп для бизнеса** > **Перенаправление звонков** > **вызвать очереди** и щелкните здесь очередь звонок. На странице " **Общие** " номер службы, у вас уже есть будет отображаться в поле **номер телефона** раскрывающегося списка. Дополнительные сведения см [Создание очереди вызовов с телефонной системой](create-a-phone-system-call-queue.md).

**Подробные сведения о получении нового номера службы и перенос существующих номеров службы разделе [Приступая к службе телефонных номеров](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Шаг 10: Настройка кредитов коммуникаций для вашей организации

Необходимо будет настроить кредитов коммуникаций, если вы хотите использовать бесплатные номера с Скайп для бизнеса и группами Майкрософт. Кроме того рекомендуется настроить кредитов коммуникаций для вызова планы (Россия или международный) и аудиоконференции пользователей, которым требуется возможность выполнять звонки в **любое место назначения**. Подписки на планы звонков и аудиоконференции охватывают множество стран и регионов, но некоторые точки могут быть недоступны. При не Настройка кредитов Communications выставления счетов и назначение лицензии **Кредитов коммуникации** для пользователей и выполнения масштабирование минут для вашей организации (в зависимости от вызова план или аудиоконференции плана в Страна или регион), этих пользователей не будут иметь возможность выполнения звонков или звонков из собрания конференц-связи звука. Можно получить дополнительные сведения, включая рекомендуемые финансирования сумм, прочитав статью [Каковы кредитов коммуникации?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Для получения сведений о стоимости [ознакомьтесь с тарифами здесь](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 

### <a name="to-set-up-communications-credits"></a>Настройка коммуникаций кредитов 

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. В центре администрирования Office 365 на панели навигации слева выберите **Выставление счетов** > **Подписки** > **Надстройки** > **Buy add-ons (Купить надстройки)**, а затем **Кредиты на связь** > **Купить**.
    
3. На странице подписки **Кредитов Communications** заполните данные и нажмите кнопку **Далее**.
        
4. Введите платежные данные и выберите команду **Заказать**.
    >[!IMPORTANT]
    >Если вы являетесь клиентом корпоративного лицензирования, можно выбрать номер соглашение enterprise для платежа. Если у вас есть несколько номеров соглашение enterprise, вы сможете выбрать соглашение enterprise вы хотите использовать для оплаты. Вы также получит возможность указать номер заказа на покупку для связи с номером соглашение enterprise (если применимо).
    
**Более подробные сведения о настройке кредитов Communications см [кредитов коммуникаций для вашей организации](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Назначение лицензии кредитов коммуникации для пользователей

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. В центре администрирования Office 365 на панели навигации слева выберите **Пользователи** > **Активные пользователи**, затем укажите одного или нескольких пользователей.
    
3. На панели действий в разделе **Лицензии на продукты** нажмите **Изменить**.
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > Это рекомендуется делать даже в том случае, если у вас есть пользователи с назначенными лицензиями на выпуск **Корпоративный E5**.

**Дополнительные сведения о назначении лицензий кредитов Communications см [кредитов коммуникаций для вашей организации](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>See also
[Преимущества телефонной системы в Office 365](here-s-what-you-get-with-phone-system.md)

[Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams](getting-service-phone-numbers.md)

[Страны и регионы, для которых доступны аудиоконференции и планы звонков](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 