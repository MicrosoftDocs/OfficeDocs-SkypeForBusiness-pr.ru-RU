---
title: Настройка автосекретаря телефонной системы
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Узнайте, как настроить и тестирование автосекретари телефонной системой (облако УАТС) для обработки для вашей организации эффективным звонков. '
ms.openlocfilehash: 41a4f7d3536e3a92104c98eaee057a47a21aeb9e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373574"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Настройка автосекретаря телефонной системы

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.

Если вы хотите узнать больше о автосекретари, [Каковы телефонной системой автосекретари?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Шаг 1. Начало работы

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service numbers, they will show up on the **Skype for Business admin center** > **Voice** > **Phone numbers** page. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md), or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. If you are outside the United States, you can't use the Skype for Business admin center to get service numbers; go [here](/microsoftteams/manage-phone-numbers-for-your-organization) instead.

    > [!CAUTION]
    > To get and use toll-free phone numbers, you need to set up Communications Credits. To do this see [What are Communications Credits?](/microsoftteams/what-are-communications-credits) and [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for auto attendants. The numbers of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). You can also use Windows PowerShell. For example, run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Шаг 2. Создание нового автосекретаря

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**


В **Центре администрирования Skype для бизнеса** выберите **Маршрутизация вызовов** > **Автосекретари** и щелкните **Добавить**:

### <a name="edit-general-info-page"></a>Страница "Изменение общей информации"

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Номер 1](../images/sfbcallout1.png)<br/>**Name** Enter a descriptive display name for your auto attendant. The name is required and can contain up to 64 characters, including spaces. It will be listed in the **Name** column on the **Auto attendants** tab.
***

![Номер 2](../images/sfbcallout2.png)<br/>**Phone number** This setting is optional. If you like, select a phone number for your auto attendant. You can pick any available service toll or toll-free phone number that you have for your organization. If there are no phone numbers listed, you will need to get a service toll or toll-free phone number. Go [here](getting-service-phone-numbers.md) to get them. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Номер 3](../images/sfbcallout3.png)<br/>**Часовой пояс**. Укажите часовой пояс для функции автосекретаря. Он не обязательно должен совпадать с часовым поясом, соответствующим указанному для вашей организации основному адресу. Для каждого автосекретаря можно указать свой часовой пояс, на основе которого в каждом конкретном случае будут установлены соответствующие рабочие часы.
***
![14](../images/sfbcallout4.png)<br/>**Language** Select the language that you want to use for your auto attendant from any of the available languages listed. The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.
***
![Номер 5](../images/sfbcallout5.png)<br/>**Speech recognition** Speech recognition is available and if this option is selected. People that call in can use voice input in the language you set. You can disable speech recognition by clearing it if you want to only let people use their phone keypad.
***
![Номер 6](../images/sfbcallout6.png)<br/>**Operator** This is optional and doesn't need to be set for the auto attendant. However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them. <br/> <br/> Оператору автоматически назначается клавиша 0. <br/> <br/> If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page. If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option. For example, "For the Operator, press zero." <br/><br/>  Для выбора в качестве оператора доступны следующие варианты: 
*    **Сотрудник компании**, имеющий лицензию на**телефонную систему**и возможность подключения по корпоративной голосовой связи или планы звонков в Office 365. <br/>

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 isn't supported. <br/> 

*    Настроенная вами **очередь звонков**. 
*    You can set it up so the person calling will be sent to voicemail. To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail. 

### <a name="select-hours-of-operation-page"></a>Страница выбора часов работы

By default, business hours are set to 24 hours a day, 7 days a week, so all hours are considered business hours. All of the hours that aren't included in business hours are considered after business hours. If you select the **Custom** option and set your business hours, then a new page called **After hours call handling** will be added where you can configure the call handling for after business hours for the auto attendant.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Номер 1](../images/sfbcallout1.png)<br/>Выберите параметр **Другой**, чтобы задать конкретные рабочие часы в календаре. При выборе параметра **Другой** по умолчанию устанавливаются рабочие часы с 09:00 до 17:00.
***
![Номер 2](../images/sfbcallout2.png)<br/>To change business hours, highlight the business hours you want to set using the calendar. The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page. To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar. You can set multiple breaks within business hours. 

### <a name="select-business-hours-call-handling-page"></a>Страница "Обработка звонков в рабочее время"

> [!TIP]
> Если вы задаете настраиваемое рабочее расписание, также необходимо определить порядок обработки звонков в нерабочее время. Это можно сделать на странице **Обработка звонков в нерабочее время**, на которой будут представлены те же параметры, что и на странице **Обработка звонков в рабочее время**. 

Можно настроить приветствие, приглашения и меню, пользователей, которые вызова в номер телефона автосекретаря вашей организации будет воспроизводить рабочего времени.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Номер 1](../images/sfbcallout1.png)<br/>**Company greeting** Business hours greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **Нет** Никакое приветствие не будет воспроизводиться при обращении абонентов по номеру телефона автосекретаря.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Welcome to Contoso. Your call is important to us." in the **Callers will hear** box.
*    **Загрузить аудиофайл** Если выбран этот параметр, запишите приветствие и загрузите полученный звуковой файл (в формате WAV, .mp3 или WMA).
***
![Номер 2](../images/sfbcallout2.png)<br/>You can select what happens to calls that arrive during business hours. You can chose from the following options:
* **Отключить** Если выбран этот параметр, вызывающий абонент будет отключен после прослушивания приветствия в рабочее время.
* **Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:
  * **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/><br/>   
    > [!Note]
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

  *  **Очередь звонков** Функция очереди звонков позволяет добавить вызов в существующую очередь звонков, которую вы настроили.
  * Another **Auto attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.

* **Воспроизводить подсказку параметра меню** Эту функцию можно использовать, чтобы настроить подсказку для воспроизведения.
***
![Номер 3](../images/sfbcallout3.png)<br/>**Запрос меню**. Чтобы создать подсказку для основного меню, можно либо воспользоваться функцией преобразования текста в речь, либо отправить звуковой файл (WAV, MP3 или WMA). Можно ввести подсказку в поле **Будут слышать абоненты** или записать звуковой файл и сказать, например, следующее: "Для связи с отделом продаж нажмите или произнесите 1. Для связи с отделом обслуживания нажмите или произнесите 2. Для связи с отделом поддержки клиентов нажмите или произнесите 3. Для связи с оператором нажмите или произнесите 0. Чтобы прослушать доступные варианты еще раз, произнесите текст "Повторить" или нажмите клавишу со звездочкой". **Создать пользовательский запрос**. При выборе этой функции необходимо ввести текст, который должна читать система (до 1000 символов). **Отправить звуковой файл**. При выборе этой функции необходимо записать приветствие, а затем отправить звуковой файл (в формате WAV, MP3 или WMA).
***
![Номер 4](../images/sfbcallout4.png)<br/>**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search. You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page. Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.<br/><br/>  

> [!WARNING]
> Если локальный пользователь использует Lync 2010,**с ним нельзя связаться** с помощью функции "Вызов по имени".
> ***

![Номер 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. To add a menu option, press the corresponding key on the keypad. The keys in use will change in color and the corresponding row of options will appear below. To delete a menu option, simply click on the corresponding key on the keypad control to deselect this key. The key mapping row will be removed.<br/><br/>  **Совет.** При добавлении или удалении параметров вам необходимо будет обновить текст подсказок меню или повторно отдельно записать звуковой файл, так как существующие подсказки меню не будут автоматически изменены.  <br/><br/>  Any menu option can be added and removed in any order, and the key mappings don't have to be continuous. It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.<br/><br/> 

> [!NOTE]
> The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands.


Чтобы настроить параметры меню, после выбора клавиш необходимо выполнить следующее: 
- **Enter the Name of the option** This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds." If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3. 
- The next step is to select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition. The call can be sent to: 
    - **Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.<br/><br/> 

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

    - **Очередь звонков** Функция очереди звонков позволяет добавить вызов в существующую очередь звонков, которую вы настроили. 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>

        > [!Note]
        > Также будет использоваться **время работы** вложенных автосекретарей (автосекретарей второго уровня), в том числе для вызовов, переадресуемых с других настроенных автосекретарей.         

### <a name="select-holidays-page"></a>Страница "Выбор праздничных дней" 

Вы можете добавить до 20 запланированных праздников для каждого автосекретаря.

![Настройка праздников в автосекретаре](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)

***
![Номер 1](../images/sfbcallout1.png)<br/>**Добавить праздник** Введите имя нового праздников в поле**Имя праздника**.<br/><br/> Holiday names may consist of up to 64 characters and must be unique for the same auto attendant. For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.  
***
![Номер 2](../images/sfbcallout2.png)<br/>**Holiday Greeting** The Holiday Greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **Нет** Никакое приветствие не будет воспроизводиться при обращении абонентов по номеру телефона автосекретаря.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Happy New Year! Our offices are currently closed." in the **Callers will hear** box.
*    **Загрузить аудиофайл** Если выбран этот параметр, запишите приветствие в праздничные дни и загрузите полученный звуковой файл (в формате WAV, .mp3 или WMA).  
***
![Номер 3](../images/sfbcallout3.png)<br/>**What happens to the calls after the greeting?** You can select what happens to the calls that arrive during this holiday. You can chose from the following options:
* **Отключить** Вызывающий абонент будет отключен после прослушивания праздничного приветствия.
* **Переадресовать звонок** Этот параметр можно использовать для автоматической переадресации вызова, используя следующие параметры:
  * A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail. <br/><br/> 

    > [!Note] 
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported.<br/><br/>

  * **Очередь звонков**: добавление вызова в существующую очередь звонков, которую вы настроили.
  * Another **Auto attendant**, to create a second level of menu options containing a submenu. These are called nested auto attendants. <br/><br/>

    > [!Note]
    > По умолчанию все вызовы, поступающие в период праздников, после приветствия (при его наличии) переводятся в режим "Отключить", поэтому если вы хотите изменить этот режим работы, необходимо указать, кому следует переадресовать вызов.

***
![Номер 4](../images/sfbcallout4.png)<br/>**When do you want the holiday to start and end?** Enter your holiday start date in dd/mm/yyyy format, and then select a start time, end date, and end time, as prompted in the date range table.<br/><br/>You can specify up to 10 different date ranges for a holiday. For example, you could add date ranges for New Year's Eve holidays for up to 10 years. A holiday can span multiple days.<br/><br/>Чтобы добавить дополнительные диапазоны дат праздника (например, на следующий год), нажмите **Добавить**и введите новые даты начала и окончания праздника.<br/><br/>Nested holidays are also supported. For example, you could nest multiple holidays within one "holiday break" time frame: 
*    **December 24 through January 3:** "Happy Holidays! Our offices are currently closed. We will reopen on January 4th."
*    **December 25:** "Merry Christmas! Our offices are currently closed. We will reopen on January 4th."
*    **January 1:** "Happy New Year! Our offices are currently closed. We will reopen on January 4th."

После сохранения автосекретаря праздники отображаются на вкладке **Праздники**, где можно изменить, добавить или изменить настройки праздничных дней.

### <a name="select-dial-scope-page"></a>Страница "Выбор списка набора"

На этой странице можно настроить пользователей, которые в вашей организации будет перечислен в каталоге и доступных абонентских групп по имени, если пользователь, который вызывает вашей организации.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Номер 1](../images/sfbcallout1.png)<br/>При использовании функции **Включить** предлагаются два параметра:
* **All Online users** Using this option allows all of the people in your organization to be included in directory search. All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed. 
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Не будет отображаться локальных пользователей от развертывания Lync Server 2010, когда кто-то ищет в каталоге с помощью вызова по имени. 
***
![Номер 2](../images/sfbcallout2.png)<br/>С помощью параметра **исключить** , у вас есть два варианта:
* **Нет**. Использование этой функции означает, что при поиске по справочнику никакие пользователи не исключаются из списка.  
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Не будет отображаться локальных пользователей от развертывания Lync Server 2010, когда кто-то ищет в каталоге с помощью вызова по имени.          

> [!NOTE]
> Может потребоваться до 36 часов для их имена, перечисленные в каталоге с помощью вызова по имени распознавания речи нового пользователя. 

После ввода обязательных полей и настройки обработки меню и параметры звонков, нажмите кнопку **Сохранить**.

## <a name="editing-and-testing-auto-attendants"></a>Редактирование и тестирование автосекретари

After you have saved your auto attendant, it will be listed on the **Auto attendants** page. This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.

Если вы хотите внести изменения для автосекретаря, выберите тот автосекретарь и в области действий нажмите кнопку **Изменить**.

Можно также быстро выполните тестовый вызов для вашей автосекретаря с помощью кнопки **тестирования** в области действий.

## <a name="want-to-know-more"></a>Дополнительные сведения

Можно также использовать Windows PowerShell для создания и настройки автосекретарей.

### <a name="auto-attendant-cmdlets"></a>Командлеты для работы с автосекретарями

Далее перечислены командлеты, необходимые для управления автосекретарем.


|                                                                                                                                                               |                                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                    |                                [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                 |
|                                   [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                    |                              [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                               |
|                                   [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                    |    [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)    |
|                                  [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                  |                                 [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                  |
|                                         [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                         |                               [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) |                                         [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                          |
|                    [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                    |                                          [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                          |
|                           [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                           |                        [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                        |
|                           [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                           | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
|                            [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                             |                                                                                                                                                               |

### <a name="more-about-windows-powershell"></a>Дополнительные сведения о Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Возможности телефонной системы в Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Получение номеров телефонов служб для Skype для бизнеса и Microsoft Teams](getting-service-phone-numbers.md)

[Страны и регионы, для которых доступны аудиоконференции и планы звонков](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Что такое автосекретари телефонной системы?](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Пример для малого бизнеса — Настройка автосекретарю.](tutorial-org-aa.yml)  
