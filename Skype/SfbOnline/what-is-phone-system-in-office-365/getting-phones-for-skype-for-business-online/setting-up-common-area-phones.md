---
title: Настройка телефонов общего пользования
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
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
- Phone System
description: Ознакомьтесь с инструкциями по развертыванию, чтобы получить подходящую версию встроенного по, при необходимости обновите ее, назначьте лицензии и настройте параметры для стационарных телефонов с областями.
ms.openlocfilehash: a245db1a2033f08d50e9a3c1a32f27981a3eb702
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924900"
---
# <a name="set-up-common-area-phones"></a>Настройка телефонов общего пользования
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Предварительные требования для телефонов общего пользования

В первую очередь необходимо выполнить следующее:

- Приобрести лицензию на телефон общего пользования и тарифный план.
- Найти и приобрести одобренные телефоны (вы можете просмотреть их список[здесь](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Polycom VVX phones**: перейдите в раздел **Параметры** > **** > **** > **приложения** > Platform**Main**.
  - **Yealinkные телефоны**: переход к **состоянию** на главном экране телефона.
  - **AudioCodes телефоны**: переход в **меню** > "**состояние** > устройства **" на** начальном экране.
  - **Lync Phone Edition (LPE)**: выберите **пункт** > "**сведения о системе** " на начальном экране.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Настройка телефона общего пользования
Вам потребуется выполнить следующие шаги:

### <a name="step-1---buy-the-licenses"></a>Шаг 1. Приобретение лицензий
1. В центре администрирования перейдите в раздел**услуги**по **выставлению счетов** > и добавьте **другие планы**.

    ![CAP-license.png](../../images/cap-license.png)
2. Нажмите на **Телефон общего пользования** > **Купить**, на странице **Оформление заказа** нажмите кнопку **Купить**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Дополнительные сведения о лицензиях можно найти в [статье Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Шаг 2. Создание новой учетной записи пользователя для телефона и назначение лицензии
1. В центре администрирования перейдите в раздел **Пользователи** > , которые являются**активными** > , чтобы**Добавить пользователя**.
2. В поле **Имя пользователя** укажите, например, "Основная", а в графе для фамилии — "Приемная".
3. В поле **Отображаемое имя**, если оно не заполнилось автоматически, укажите, например, "Главная Приемная".
4. В поле**Имя пользователя** укажите, например, "MainReception" или "Mainlobby".
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.
6. Если вы все еще на этой странице, назначьте лицензии этому пользователю. На этой же странице щелкните мышью и разверните **Лицензии продуктов**. Включите следующие опции:
   - Телефон общего пользования
   - Общего Пользования sedGlossaryTerm">Телефон********

     Назначение лицензий будет выглядеть следующим образом:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Приводим к вашему сведению, что в лицензию **Телефона общего пользования** включен План 2 Skype для бизнеса.

Узнайте больше в статье [Добавление пользователей](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Шаг 3 - Назначьте номер телефона учетной записи пользователя телефона общего пользования

![Значок, показывающий логотип](../../images/sfb-logo-30x30.png) Skype для бизнеса, назначает пользователю телефонный номер с помощью **центра администрирования Skype для бизнеса** .

1. В центре администрирования > >  **"центр администрирования"** в**Skype для бизнеса**.
2. Далее: **Центр администрирования Skype для бизнеса** >  **Голосовая связь** > **Номера телефонов**.
3. Выберите номер телефона из списка и нажмите **Назначить**.
4. На странице **Назначить** в поле **Пользователь голосовой связи** введите имя пользователя телефона, а затем выберите пользователя в выпадающем списке **Выбор пользователя голосовой связи**.
5. Пока вы находитесь на этой странице, необходимо добавить адрес для обращения в экстренных случаях. Во время поиска выберите нужный адрес под пунктом **Выбор адреса для обращения в экстренных случаях**.
6. Нажмите **Сохранить**. Ваш пользователь должен выглядеть следующим образом:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Пользователи будут отображаться, только если на них распространяется лицензия **Телефонная система**. Если вы только что выполнили эти действия, может потребоваться некоторое время, чтобы пользователь отобразился в списке.

Узнайте больше в статье [Получение телефонных номеров для ваших пользователей](/microsoftteams/getting-phone-numbers-for-your-users).

При необходимости номера телефонов других операторов можно "*портировать*" или передать в Office 365. Посмотрите, [перенесите номера телефонов в Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

### <a name="step-4---setting-up-your-phone"></a>Шаг 4. Настройка телефона

**Настройка режима в телефоне**

В вашем телефоне необходимо включить **Режим телефона общего пользования**. Убедитесь, есть ли в нем такой режим.

**Ниже приведен пример настройки телефона Polycom VVX**

- Включите режим телефона общего пользования для Polycom VVX, выполнив следующие шаги:
    1. Подключитесь к веб-интерфейсу через веб-обозреватель, чтобы включить режим CAP.
    2. Затем откройте меню **Параметры** и в пункте **Параметры Skype для бизнеса** выберите **Телефон общего пользования**.
    3. Нажмите **Да** для сохранения параметров.

- Теперь режим CAP включен, и вы можете настроить телефон, используя его дисплей. Дисплей должен показывать **CAP включен**. Выполните следующие действия:

    1. Выберите **Параметры**.
    2. Нажмите кнопку **Дополнительно**.
    3. Введите пароль.
    4. В пункте **Параметры администрирования** выберите **Параметры телефона общего пользования**.
    5. Включите **CAP** и **Режим администратора CAP**.
    6. Нажмите **Сохранить конфигурацию**.

- Теперь телефон готов, и вы можете выполнить вход на начальном экране.

    1. Войдите, выбрав **Параметры** > **Функции** > **Skype для бизнеса**.
    2. Выберите **Учетные данные пользователя**, а затем — **Интернет-вход (CAP)**, чтобы генерировать код.
    3. Перейдите на [портал подготовки](https://aka.ms/skypecap) и войдите в систему как **администратор**.
    4. Введите отображаемое имя (например, Главная Приемная).

       > [!Note]
       > Если отмечена опция **Искать только телефоны общего пользования**, снимите флажок и выполните поиск повторно.

    5. В окне кода сопряжения введите код, который отображается на телефоне, и нажмите **Подготовка**.

        После этого действия телефон должен автоматически войти в систему.


> [!NOTE]
> Сайт подготовки CAP заявляет о сбросе пароля учетной записи CAP на случайный пароль. Обратите внимание, что учетная запись, на которую ссылается CAP, представляет собой учетную запись Azure Active Directory (AAD). Если вы создали учетную запись только в AAD, процесс не будет сложным. Если вы синхронизируете локальную службу Active Directory с AAD и используете сторонние IDP или ADFS, инициализация закрепления завершается сбоем. В этом случае необходимо использовать учетную запись Office 365 или Azure Active Directory только (например, учетную запись с доменом **onmicrosoft.com** ), чтобы подготовиться к работе.


### <a name="related-topics"></a>См. также

- Узнайте больше о доступных телефонах в статье [Развертывание телефонов Skype для бизнеса Online](deploying-skype-for-business-online-phones.md).
- [Телефоны, поддерживаемые в Skype для бизнеса Online](getting-phones-for-skype-for-business-online.md)


