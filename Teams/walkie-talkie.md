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
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0475fd161d3b53a8fc60d3a1419d20e3de2bfada
ms.sourcegitcommit: bb428cd5805151736f0a6786d737f67f2b3fc918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2022
ms.locfileid: "68557482"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Приложение "Рация" в Microsoft Teams

Приложение Walkie Talkie в Teams обеспечивает мгновенное взаимодействие с пользователем (PTT) и доступно в Android и iOS. С помощью рации пользователи в команде могут общаться друг с другом, используя те же каналы, в которых они участвуют. Только пользователи, которые подключаются к рации в канале, становятся участниками и могут взаимодействовать друг с другом по одному.

С помощью рации в Teams сотрудники переднего плана могут безопасно взаимодействовать с привычным интерфейсом PTT, не перенося массовые радио, а рация работает в любом месте с подключением через Wi-Fi или мобильный Интернет.

> [!NOTE]
> Рация в настоящее время недоступна в Китае.

## <a name="license-requirements"></a>Требования к лицензиям

Рация включается во все платные лицензии Teams в [Microsoft 365 и Office 365 подписки](/office365/servicedescriptions/teams-service-description). Дополнительные сведения о получении Teams см. Разделы справки [доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="deploying-walkie-talkie"></a>Развертывание рации

Рация поддерживается на устройствах Android с мобильными службами Google (GMS) и устройствами iOS.

> [!NOTE]
> Если пользователи используют аксессуары Bluetooth, убедитесь, что решение для управления мобильными устройствами (MDM) не блокирует устройства Bluetooth.

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>Включение или отключение рации в организации

Рация включена по умолчанию для всех пользователей Teams в вашей организации. Вы можете отключить или включить приложение на уровне организации на странице [Управление приложениями](manage-apps.md) в Центре администрирования Microsoft Teams.

1. В левой панели навигации Центра администрирования Microsoft Teams выберите **Приложения Teams** > **Управление приложениями**.
2. В списке приложений найдите приложение Walkie Talkie, выберите его, а затем переключите переключатель "Состояние" на **"Заблокировано**" или "**Разрешено"**.

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>Включение или отключение рации для определенных пользователей в организации

Чтобы разрешить или заблокировать использование Walkie Talkie для определенных пользователей в вашей организации, убедитесь, что для вашей организации включена функция Walkie Talkie на странице "Управление [приложениями](manage-apps.md) ". Затем создайте настраиваемую политику разрешений приложения, добавьте ее в политику установки приложения и назначьте ее этим пользователям. Дополнительные сведения см. в статье "Управление политиками [разрешений приложений в Teams](teams-app-permission-policies.md) и управление политиками установки приложений [в Microsoft Teams"](teams-app-setup-policies.md).

### <a name="pin-walkie-talkie-to-teams"></a>Закрепление рации в Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Использование специализированного интерфейсного приложения для закрепления рации и других приложений в Teams

Специализированное интерфейсное приложение в Teams закрепляет наиболее релевантные приложения в Teams для пользователей с [лицензией F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Закрепленные приложения включают рация, смены, задачи и утверждения. По умолчанию эта функция включена, предоставляя сотрудникам без компьютеров встроенный интерфейс, соответствующий их потребностям.

Приложения закрепляются на панели приложений ( на панели сбоку от настольного клиента Teams и в нижней части мобильных клиентов Teams), где пользователи могут быстро и легко получить к ним доступ.

Дополнительные сведения, в том числе о работе с задаваемых политиками приложений, см. в статье "Настройка приложений [Teams для сотрудников без компьютеров"](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Использование политики настройки приложения для закрепления рации в Teams

Политики установки приложений позволяют настроить Teams для закрепления приложений, которые наиболее важны для пользователей в ваших пользователях.

Чтобы закрепить приложение Walkie Talkie для пользователей, можно изменить глобальную политику (по умолчанию для всей организации) или создать и назначить настраиваемую политику установки приложения. Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Снимок экрана: добавление рации в список закрепленных приложений на панели &quot;Добавление закрепленных приложений&quot;." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Сетевая документация

Для использования рации в Teams требуется подключение к Интернету. Для оптимального взаимодействия требуются следующие сетевые условия.

|Показатель | Обязательно |
|---|---|
|Задержка (RTT) | < 300 мс |
|Дрожание |< 30 мс |
|Потеря пакетов |< 1 % |

Как указано выше, на качество мультимедиа в реальном времени по IP-сети значительно влияет качество сетевого подключения, но в особенности следующие показатели:

- **Задержка —** время, необходимое для получения IP-пакета от точки A до точки B в сети. Эта задержка распространения сети, по сути, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные издержки, связанные с различными маршрутизаторами между ними. Задержка измеряется как период кругового обращения (RTT).
- **Дрожание между поступлениями —** среднее изменение задержки между последовательными пакетами.
- **Потеря пакетов** — потеря пакетов часто определяется как процент пакетов, которые теряются в заданный период времени. Потеря пакетов напрямую влияет на качество звука — от небольших отдельных потерянных пакетов, которые почти не влияют, до потери пакетов с обратной нагрузкой, которые приводят к завершению отключения звука.

Ожидаемое использование данных рации составляет около 20 КБ/с при отправке или получении звука. При простое ожидаемой интенсивностью использования данных в рации можно пренебречь.

## <a name="walkie-talkie-devices"></a>Устройства для рации

Сотрудникам без компьютеров часто приходится говорить и принимать вызовы по рации, даже когда их телефоны заблокированы. Этот режим работы реализуется на специальных устройствах с кнопкой передачи.

#### <a name="headsets"></a>Гарнитуры

- Беспроводные гарнитуры (iOS и Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Проводные гарнитуры (только для Android)
  - [Электронная почта](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Защищенные телефоны Android

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) и [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Настройка вручную. После установки Teams перейдите к **кнопкам "Параметры** > **"**. На выделенной кнопке (1 или 2) нажмите клавишу **Long** и выберите **приложение PTT**. Щелкните синее колесико рядом с **пунктом "Пользовательский**" и выберите **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) и [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Настройка вручную. После установки Teams перейдите к **разделу "Параметры** > **программируемых ключей"**. Выберите **клавишу PTT или** **нажмите и удерживайте** (в зависимости от устройства) и выберите **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Настройка вручную. При установке Teams выделенная кнопка PTT по умолчанию работает с рациями.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Настройка вручную. После установки Teams перейдите  >  к разделу "**Параметры расширенных функций** > **" XCover/Active Key**. Включите **ключ control XCover с приложением и** выберите **Teams**.
  - [Настройка MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Настройка вручную. После установки Teams перейдите к **разделу "Параметры** > **программируемых ключей"**. Выберите **приложение "Выбор ключа PTT**" и выберите **Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Настройка вручную. При установке Teams выделенная кнопка PTT (LEFT_TRIGGER_2) по умолчанию работает с рациями.

> [!NOTE]
> Эти устройства не сертифицированы для Teams. Они прошли проверку на работу с рацией Teams.

## <a name="more-information"></a>Дополнительные сведения

- Если ваш сотрудник переднего плана использует мобильные данные для обмена данными через Teams, Walkie Talkie будет использовать тот же метод.
- Рация хорошо работает в ситуациях с малой пропускной способностью или в ситуациях, когда смартфон подключен и работает. Рация не будет работать, если нет подключения.

Дополнительные сведения о пользовательском интерфейсе см. в следующих статьях:

- [Начало работы с рацией Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Связь с командой при помощи рации](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
