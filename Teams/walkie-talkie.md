---
title: Приложение "Рация" в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Как настроить приложение "Рация" в Microsoft Teams с точки зрения ИТ-администратора.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2022
ms.locfileid: "62015019"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Приложение "Рация" в Microsoft Teams

Приложение Ральное сообщение в Teams позволяет мгновенно общаться с командой, а теперь доступно на устройствах с Android & iOS. С помощью рации пользователи в команде могут общаться друг с другом, используя те же каналы, в которых они участвуют. Только пользователи, которые подключились к рации в канале, становятся участниками разговора и могут говорить друг с другом по очереди.

С помощью рации в Teams, фронтальная работники теперь могут безопасно общаться с помощью знакомых функций PTT без необходимости использовать массовые радио, а рации работают где угодно с помощью Wi-Fi или сотового подключения к Интернету.

## <a name="getting-started"></a>Начало работы

### <a name="deploying-walkie-talkie"></a>Развертывание рации

Talkie поддерживается на устройствах с Android на устройствах Google мобильные службы (GMS) и iOS. 

В настоящее время рация не устанавливается по умолчанию. Чтобы включить эту функцию для пользователей в вашей организации, добавьте приложение "Рация" в  [политику установки приложений](teams-app-setup-policies.md) , назначенную пользователям в [Центре администрирования Teams](https://admin.teams.microsoft.com/). Включив ее, она станет доступна в приложении в течение 48 часов.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Добавление рации в список приложений

В Центре администрирования Microsoft Teams выберите **Приложение Teams** > **Политики установки** и установите для параметра **Разрешить пользователям закрепление** значение **Вкл**. Затем в разделе "Закрепленные приложения" нажмите кнопку **+Добавить приложения**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Показаны раздел "Закрепленные приложения" и нажимаемая кнопка "Добавить приложения".":::

На панели **Добавить закрепленные приложения** справа поищите приложение "Рация" в текстовом поле **Поиск**. Если она есть в результатах поиска, выберите кнопку  Добавить справа от имени, чтобы добавить ее в список.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Показаны боковая панель "Добавить закрепленные приложения" с введенным в область поиска названием "Рация", приложение "Рация" в результатах поиска и кнопка "Добавить" рядом с ним.":::

Теперь приложение "Рация" должно появиться в списке закрепленных приложений и будет доступно для использования после нажатия кнопки **Сохранить**.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Показан список закрепленных приложений с добавленным приложением "Рация" и кнопкой "Сохранить" под списком.":::

### <a name="network-documentation"></a>Сетевая документация

Для использования рации в Teams требуется подключение к Интернету, а условия сети, необходимые для оптимальной работы, приведены ниже.

|Показатель | Обязательно |
|---|---|
|Задержка (RTT) | < 300 мс |
|Дрожание |< 30 мс |
|Потеря пакетов |< 1 % |

Как указано выше, на качество мультимедиа в реальном времени по IP-сети значительно влияет качество сетевого подключения, но в особенности следующие показатели:

- **Задержка** — это время, необходимое для передачи IP-пакета из точки A в точку B в сети. Эта задержка распространения по сети, по сути, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные накладные расходы различных маршрутизаторов между ними. Задержка измеряется как период кругового обращения (RTT).
- **Дрожание между** прибытиями — это среднее изменение задержки между последовательными пакетами.
- **Потеря пакетов** — часто определяется как процент пакетов, которые теряются за определенный период времени. Потеря пакетов напрямую влияет на качество звука — отдельные потерянные пакеты почти не оказывают влияния, а сплошные последовательные потери приводят к полному исчезновению звука.

Ожидаемое использование данных в walkie Talkie составляет около 20 КБ/с при отправке или получении звука. При простое ожидаемой интенсивностью использования данных в рации можно пренебречь.

### <a name="walkie-talkie-devices"></a>Устройства для рации

Сотрудникам без компьютеров часто приходится говорить и принимать вызовы по рации, даже когда их телефоны заблокированы. Этот режим работы реализуется на специальных устройствах с кнопкой передачи.

- **Гарнитуры**
  - Беспроводные гарнитуры (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Проводные гарнитуры (только для Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Неровные телефоны с Android**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Настройка вручную. Teams, перейдите к Параметры > дополнительных > XCover/Active. Включит клавишу CONTROL XCover с приложением и выберите "Teams"
    - [Настройка MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Настройка вручную: Teams установлена специальная кнопка PTT (LEFT_TRIGGER_2) по умолчанию работает с рябчим.
    
> [!NOTE]
> Эти устройства не сертифицированы для Teams. Они прошли проверку на работу с рацией Teams.

### <a name="license-requirements"></a>Требования к лицензиям

Приложение "Рация" включено во все платные лицензии Teams в [подписках на Office 365](/office365/servicedescriptions/teams-service-description). Чтобы больше узнать о получении Teams, обратитесь к статье  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).

## <a name="further-information"></a>Дополнительные сведения

- ИТ-администраторы могут контролировать использование рации с помощью политик приложений.
- Если ваш фронтовик использует мобильные данные для связи с помощью Teams, то такой же метод будет применяться в talkie.
- Рация хорошо работает в ситуациях с малой пропускной способностью или в ситуациях, когда смартфон подключен и работает. Если подключения нет, рация не будет работать.

Дополнительно о работе конечных пользователей можно прочитать в статьях

- [Начало работы с рацией Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Связь с командой при помощи рации](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
