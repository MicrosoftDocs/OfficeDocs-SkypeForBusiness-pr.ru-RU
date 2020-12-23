---
title: Приложение Walkie Talkie в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Настройка приложения Walkie Talkie в Microsoft Teams с точки зрения ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262506"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Приложение Walkie Talkie в Microsoft Teams

Приложение Walkie Talkie в Teams позволяет мгновенно общаться с командой с помощью push-to-talk (PTT), и теперь доступно для Android. Скайти Talkie позволяет пользователям связываться со своей командой, используя каналы, в которые они являются. Только пользователи, которые подключаются к Walkie Talkie в канале, становятся участниками и могут общаться друг с другом по одной.

С помощью Walkie Talkie в Teams сотрудники, работающие без компьютеров, теперь могут безопасно взаимодействовать с привычным взаимодействием с PTT, не утомив при этом массовые радиосвязи, а Лидия Talkie работает где угодно с Wi-Fi или мобильным подключением к Интернету.

## <a name="getting-started"></a>Начало работы

### <a name="deploying-walkie-talkie"></a>Развертывание Walkie Talkie

В настоящее время приложение Walkie Talkie не предварительно установлено. Чтобы включить эту функцию для пользователей в организации, необходимо [](teams-app-setup-policies.md)добавить Вадию Talkie в политику установки приложений, назначенную пользователям в Центре администрирования   [Teams.](https://admin.teams.microsoft.com/)

После включения Walkie Talkie станет доступно в приложении для Android в течение 48 часов.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Добавление в список приложений Walkie Talkie

В Центре администрирования Microsoft Teams в соответствии с политиками настройки приложений **Teams** необходимо установить для пользователя режим "Разрешить закрепление".  >     Затем в разделе "Закрепленные приложения" нажмите **кнопку +Добавить приложения.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Раздел "Закрепленные приложения" и выбранная кнопка "Добавить приложения".":::

На панели **"Добавление** закрепленных приложений", которая  появляется справа, найдите в текстовом окне "Поиск" Walkie Talkie. Если это результат поиска, нажмите  кнопку "Добавить" справа от имени, чтобы добавить его в список.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Отображает боковую панель "Добавить закрепленные приложения" с введенной в области поиска и приложением Walkie Talkie в результатах поиска с кнопкой "Добавить" рядом с ней.":::

Приложение Walkie Talkie должно появиться в списке закрепленных приложений и стать доступно для использования после нажатия кнопки **"Сохранить".**

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Список закрепленных приложений с добавленным приложением Walkie Talkie и кнопкой "Сохранить" под списком.":::

### <a name="network-documentation"></a>Сетевая документация

Для обеспечения оптимального взаимодействия требуется подключение к Интернету, а для оптимальной работы требуется подключение к Интернету.

|Показатель | Обязательный |
|---|---|
|Задержка (RTT) | < 300 мс |
|Искажение |< 30 мс |
|Packet Loss (Потеря пакетов) |< 1 % |

Как было отмечено выше, на качество мультимедиа в режиме реального времени по IP-сети в значительной мере влияет качество сетевого подключения, но особенно на количество:

- **Задержка —** это время, необходимое для получения IP-пакета из точки A в точку B сети. Эта задержка распространения сети, по существу, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные накладные расходы, которые связаны с различными маршрутизаторами между ними. Задержка измеряется как время кругового пути (RTT).
- **Packet Loss** (Потеря пакетов) — часто определяется как процент пакетов, потерянных за определенный период времени. Потеря пакетов напрямую влияет на качество звука — небольшие потерянные пакеты практически не оказывают влияния, а потери пакетов в очереди приводят к полному из-за разрыва звука.
- **Дрожание** — это среднее изменение задержки между последовательными пакетами.

Ожидаемое использование данных от Walkie Talkie составляет около 20 КБ/с при отправке или получении звука. Если данные неаемые, ожидаемый объем данных, полученный от Walkie Talkie, является неосторожным.

### <a name="walkie-talkie-devices"></a>Устройства Walkie Talkie

Сотрудникам, работающим с firstline, часто приходится общаться и принимать звонки Walkie Talkie, даже если их телефоны заблокированы. Такая возможность возможна на специализированных устройствах со специальной кнопкой PTT.

- Гарнитуры
  - Проводные гарнитуры[(Electronic Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)
  - Беспроводные гарнитуры[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Неровные телефоны
  - Samsung Galaxy XCover Pro
    - [Дополнительные сведения.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)
    - [Руководство по настройке.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Эти устройства не сертифицированы для Teams. Они были проверены для работы с Командой Walkie Talkie.

### <a name="license-requirements"></a>Требования к лицензии

Приложение Walkie Talkie включено во все платные лицензии Teams в [подписках на Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) Дополнительные сведения о получении Teams: как получить доступ [к Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Для некоторых дополнительных функций может потребоваться дополнительное лицензирование. Например, для интеграции с Samsung Galaxy XCover Pro требуется лицензия Knox.

## <a name="further-information"></a>Дополнительные сведения

- ИТ-политики могут управлять тем, кто использует Walkie Talkie.
- Если ваш сотрудник без компьютеров использует мобильные данные для связи через Teams, Walkie Talkie будет использовать тот же метод.
- Walkie Talkie должна хорошо работать в ситуациях, связанных с низкой пропускной способностью, или в ситуациях, когда смартфон подключен и работает. Если нет подключения, walkie Talkie не будет работать.

Дополнительные статью о интерфейсе пользователя см. в:

- [Начало работы с Командой Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Общение с командой с помощью Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
