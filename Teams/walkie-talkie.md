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
ms.openlocfilehash: 29a632efc433a14d578eff80fdeb74a6f167dfc3
ms.sourcegitcommit: a388fd72e399f6e205c34707dc92cc309997e737
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2022
ms.locfileid: "65400235"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Приложение "Рация" в Microsoft Teams

Приложение Walkie Talkie в Teams обеспечивает мгновенное взаимодействие с пользователем (PTT) и теперь доступно в Android & iOS. С помощью рации пользователи в команде могут общаться друг с другом, используя те же каналы, в которых они участвуют. Только пользователи, которые подключились к рации в канале, становятся участниками разговора и могут говорить друг с другом по очереди.

С помощью рации в Teams сотрудники переднего плана теперь могут безопасно взаимодействовать с привычным интерфейсом PTT, не перенося массовые радио, а рация работает в любом месте с подключением через Wi-Fi или мобильный Интернет.

> [!NOTE]
> Рация в настоящее время недоступна в Китае.

## <a name="getting-started"></a>Начало работы

### <a name="deploying-walkie-talkie"></a>Развертывание рации

Рация поддерживается на Android устройствах с Google мобильные службы (GMS) и iOS устройствах.

### <a name="pin-walkie-talkie-to-teams"></a>Закрепление рации в Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Использование специализированного интерфейсного приложения для закрепления рации и других приложений для Teams

Специализированное интерфейсное приложение в Teams закрепляет наиболее релевантные приложения в Teams для пользователей с [лицензией F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Закрепленные приложения включают рация, смены, задачи и Утверждения. По умолчанию эта функция включена, предоставляя сотрудникам без компьютеров встроенный интерфейс, соответствующий их потребностям.

Приложения закреплены на панели приложения — на панели в Teams клиенте и в нижней части Teams мобильных клиентов, где пользователи могут быстро и легко получить к ним доступ.

Дополнительные сведения, в том числе о том, как работает взаимодействие с задаваемой вами политиками приложений, см. в статье "Настройка Teams [приложений для сотрудников без компьютеров"](pin-teams-apps-based-on-license.md).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Использование политики установки приложения для закрепления рации в Teams

Политики установки приложений позволяют настраивать Teams для закрепления приложений, которые наиболее важны для пользователей в ваших пользователях.

Чтобы закрепить приложение Walkie Talkie для пользователей, можно изменить глобальную политику (по умолчанию для всей организации) или создать и назначить настраиваемую политику установки приложения. Дополнительные сведения см. в статье [Управление политиками и параметрами пользовательских приложений в Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Снимок экрана: добавление рации в список закрепленных приложений на панели &quot;Добавление закрепленных приложений&quot;." lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>Сетевая документация

Для использования рации в Teams требуется подключение к Интернету, а условия сети, необходимые для оптимальной работы, приведены ниже.

|Показатель | Обязательно |
|---|---|
|Задержка (RTT) | < 300 мс |
|Дрожание |< 30 мс |
|Потеря пакетов |< 1 % |

Как указано выше, на качество мультимедиа в реальном времени по IP-сети значительно влияет качество сетевого подключения, но в особенности следующие показатели:

- **Задержка** — это время, необходимое для передачи IP-пакета из точки A в точку B в сети. Эта задержка распространения сети, по сути, связана с физическим расстоянием между двумя точками и скоростью света, включая дополнительные издержки, связанные с различными маршрутизаторами между ними. Задержка измеряется как период кругового обращения (RTT).
- **Дрожание между поступлениями —** это среднее изменение задержки между последовательными пакетами.
- **Потеря пакетов** — часто определяется как процент пакетов, которые теряются за определенный период времени. Потеря пакетов напрямую влияет на качество звука — отдельные потерянные пакеты почти не оказывают влияния, а сплошные последовательные потери приводят к полному исчезновению звука.

Ожидаемое использование данных рации составляет около 20 КБ/с при отправке или получении звука. При простое ожидаемой интенсивностью использования данных в рации можно пренебречь.

### <a name="walkie-talkie-devices"></a>Устройства для рации

Сотрудникам без компьютеров часто приходится говорить и принимать вызовы по рации, даже когда их телефоны заблокированы. Этот режим работы реализуется на специальных устройствах с кнопкой передачи.

- **Гарнитуры**
  - Беспроводные гарнитуры (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Проводные гарнитуры (только Android)
    - [Электронная почта](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Защищенные Android телефонов**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Настройка вручную. Teams установлен, перейдите к разделу Параметры > advanced Features > XCover/Active Key. Включите "Control XCover key with app" (Управление ключом XCover с помощью приложения) и выберите "Teams"
    - [Настройка MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Настройка вручную. Teams установлена, выделенная кнопка PTT (LEFT_TRIGGER_2) по умолчанию работает с рациями.
    
> [!NOTE]
> Эти устройства не сертифицированы для Teams. Они прошли проверку на работу с рацией Teams.

### <a name="license-requirements"></a>Требования к лицензиям

Приложение "Рация" включено во все платные лицензии Teams в [подписках на Office 365](/office365/servicedescriptions/teams-service-description). Чтобы больше узнать о получении Teams, обратитесь к статье  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).

## <a name="further-information"></a>Дополнительные сведения

- ИТ-администраторы могут контролировать, кто использует Рация с помощью политик приложений.
- Если ваш сотрудник переднего плана использует мобильные данные для обмена данными Teams, Walkie Talkie будет использовать тот же метод.
- Рация хорошо работает в ситуациях с малой пропускной способностью или в ситуациях, когда смартфон подключен и работает. Рация не будет работать, если нет подключения.

Дополнительно о работе конечных пользователей можно прочитать в статьях

- [Начало работы с рацией Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Связь с командой при помощи рации](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
