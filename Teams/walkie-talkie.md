---
title: Приложение "Рация" в Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Настройка приложения Walkie Talkie в Microsoft Teams с точки зрения ИТ-администратора.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: abb14f937064b394106e0cf2d58f756371a7c04e
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131278"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Приложение "Рация" в Microsoft Teams

Приложение Walkie Talkie в Teams обеспечивает мгновенный обмен данными по запросу "push-to-talk" (PTT) для вашей команды и доступно в Android и iOS. С помощью рации пользователи в команде могут общаться друг с другом, используя те же каналы, в которых они участвуют.

Только пользователи, которые подключаются к Walkie Talkie в канале, становятся участниками и могут общаться друг с другом с помощью PTT. Пользователи будут продолжать получать передачи, пока  **не коснутся** отключения.

С помощью Walkie Talkie в Teams пользователи могут безопасно общаться с привычным интерфейсом PTT без необходимости носить громоздкие радиоприемник, а Walkie Talkie работает в любом месте с Wi-Fi или сотовым подключением к Интернету.

> [!NOTE]
> Рация в настоящее время недоступна в Китае.

## <a name="license-requirements"></a>Требования к лицензиям

Walkie Talkie входит во все платные лицензии Teams в [Microsoft 365 и Office 365 подписки](/office365/servicedescriptions/teams-service-description). Дополнительные сведения о получении Teams см[. в статье Разделы справки получить Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>Развертывание рации

Walkie Talkie поддерживается на устройствах Android с Google Mobile Services (GMS) и устройствами iOS.

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>Шаг 1. Убедитесь, что в вашей организации включена рация.

По умолчанию приложение Walkie Talkie включено для всех пользователей Teams в вашей организации.

Вы управляете доступностью приложения на уровне организации на странице [Управление приложениями](manage-apps.md) в Центре администрирования Microsoft Teams. Чтобы убедиться, что приложение включено в вашей организации, выполните следующие действия:

1. В левой панели навигации Центра администрирования Microsoft Teams выберите **Приложения Teams** > **Управление приложениями**.
2. В списке приложений найдите приложение Walkie Talkie, выберите его и убедитесь, что для переключателя **Состояние** **задано значение Разрешено**.

Если вы хотите разрешить или запретить определенным пользователям в вашей организации использовать Walkie Talkie, убедитесь, что walkie Talkie включен для вашей организации на странице [Управление приложениями](manage-apps.md) . Затем создайте настраиваемую политику для разрешений приложений и назначьте ее этим пользователям. Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](teams-app-permission-policies.md).

### <a name="step-2-pin-walkie-talkie-to-teams"></a>Шаг 2. Закрепление Рации в Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Использование специализированного интерфейса приложения для закрепления Walkie Talkie и других приложений в Teams

Специализированное интерфейсное приложение в Teams закрепляет наиболее релевантные приложения в Teams для пользователей с [лицензией F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Закрепленные приложения включают Walkie Talkie, Shifts, Tasks и Approvals. По умолчанию эта функция включена, что позволяет сотрудникам, работающим с клиентами, работать в соответствии с их потребностями.

Приложения закрепляются в области приложений в нижней части мобильных клиентов Teams, где пользователи могут быстро и легко получить к ним доступ.

Дополнительные сведения, включая работу с настроенными политиками приложений, см. в статье [Адаптация приложений Teams для сотрудников, работающих с клиентами](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Использование политики настройки приложения для закрепления Walkie Talkie в Teams

Политики настройки приложений позволяют настроить Teams для закрепления приложений, наиболее важных для пользователей.

Чтобы закрепить приложение Walkie Talkie для пользователей, можно изменить глобальную политику (для всей организации по умолчанию) или создать и назначить настраиваемую политику в политике настройки приложений. Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Снимок экрана: добавление Walkie Talkie в список закрепленных приложений на панели Добавление закрепленных приложений." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Сетевая документация

Для рации в Teams требуется подключение к Интернету. Для оптимального взаимодействия требуются следующие условия сети.

|Показатель | Обязательно |
|---|---|
|Задержка (RTT) | < 300 мс |
|Дрожание |< 30 мс |
|Потеря пакетов |< 1 % |

Как указано выше, на качество мультимедиа в реальном времени по IP-сети значительно влияет качество сетевого подключения, но в особенности следующие показатели:

- **Задержка** — время, необходимое для получения IP-пакета из точки А в точку B в сети. Эта задержка распространения по сети по существу связана с физическим расстоянием между двумя точками и скоростью света, в том числе с большей нагрузкой на различные маршрутизаторы между ними. Задержка измеряется как период кругового обращения (RTT).
- **Дрожание между поступлениями** — среднее изменение задержки между последовательными пакетами.
- **Потеря пакетов** . Потеря пакетов часто определяется как процент пакетов, потерянных за определенный период времени. Потеря пакетов напрямую влияет на качество звука — от небольших, отдельных потерянных пакетов, которые почти не влияют, до потерь от "назад к спине", которые приводят к полному вырезанию звука.

Ожидаемое использование данных из Walkie Talkie составляет около 20 Кбит/с при отправке или получении звука. При простое ожидаемой интенсивностью использования данных в рации можно пренебречь.

## <a name="walkie-talkie-devices"></a>Устройства для рации

Сотрудникам без компьютеров часто приходится говорить и принимать вызовы по рации, даже когда их телефоны заблокированы. Этот режим работы реализуется на специальных устройствах с кнопкой передачи.

#### <a name="headsets"></a>Гарнитуры

- Беспроводные гарнитуры (iOS и Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Проводные гарнитуры (только Android)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Защищенные телефоны Android

- Перекрестное пересечение [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) и [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Ручная настройка. После установки Teams перейдите в **раздел Параметры Кнопки** > . На кнопке Выделенный (1 или 2) выберите **Длительное нажатие**, а затем выберите **Приложение PTT**. Выберите синее колесо рядом с **полем Пользовательский** и выберите **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) и [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Ручная настройка. После установки Teams перейдите в **раздел Параметры** > **Программируемые ключи**. Выберите **клавишу PTT** или **Нажмите и удерживайте** (в зависимости от устройства) и выберите **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Ручная настройка. При установке Teams выделенная кнопка PTT работает с Walkie Talkie по умолчанию.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Ручная настройка. После установки Teams перейдите в **раздел Параметры** > **Дополнительные функции** > **XCover/Active key**. Включите **параметр Управление ключом XCover с помощью приложения** и выберите **Teams**.
  - [Настройка MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Ручная настройка. После установки Teams перейдите в **раздел Параметры** > **Программируемые ключи**. Выберите **Выбрать приложение PTT Key** и выберите **Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Ручная настройка. После установки Teams выделенная кнопка PTT (LEFT_TRIGGER_2) по умолчанию работает с Walkie Talkie.

> [!NOTE]
> Эти устройства не сертифицированы для Teams. Они прошли проверку на работу с рацией Teams.

## <a name="bluetooth-devices"></a>Устройства Bluetooth

> [!NOTE]
> Если пользователи используют аксессуары Bluetooth, убедитесь, что решение для управления мобильными устройствами (MDM) не блокирует устройства Bluetooth.

На устройствах под управлением ОС Android версии 12 или более поздней требуются разрешения Bluetooth, а разрешения на расположение для подключения с помощью стека BLE больше не требуются. Если "ближайшие разрешения" не предоставлены на уровне Teams, пользователь получит запрос на получение разрешений Bluetooth. Этот запрос отображается независимо от того, подключен ли к их устройству аксессуар Bluetooth, например гарнитура. Если устройство Bluetooth подключено, нажмите **Кнопку Разрешить** , чтобы подключить Рации Talkie к аксессуару Bluetooth.

## <a name="more-information"></a>Дополнительные сведения

- Если пользователи используют мобильные данные для обмена данными через Teams, Walkie Talkie будет использовать тот же метод.
- Рация хорошо работает в ситуациях с малой пропускной способностью или в ситуациях, когда смартфон подключен и работает. Рация не будет работать, когда нет подключения вообще.

Дополнительные сведения о взаимодействии с конечными пользователями см. в следующих разделах:

- [Начало работы с рацией Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Связь с командой при помощи рации](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
