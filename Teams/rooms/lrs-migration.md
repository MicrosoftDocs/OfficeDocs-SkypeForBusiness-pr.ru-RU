---
title: Перенос устройств Lync Room System в Комнаты Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Из этой темы вы узнаете, как перенести устройства Lync Room System для использования Комнаты Microsoft Teams программного обеспечения.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aae146767f66327e5678956a14dfe72d957a8164
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503516"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Перенос устройств Lync Room System (LRS) в Комнаты Microsoft Teams

Поддержка устройств Lync Room System (LRS) с программным обеспечением Skype Room System версии 1 (SRS версии 1) заканчивается [9 октября 2018 г](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018). Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления. Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".

Комнаты Microsoft Teams программное обеспечение работает с Microsoft Teams в дополнение к Skype для бизнеса Server и онлайн-службам для собраний и звонков на все поддерживаемые устройства Комнаты Microsoft Teams устройств.

Существующие устройства **могут продолжать** работать после окончания поддержки программного обеспечения Skype Room System 1. Однако если это программное обеспечение попадает в ошибку программного обеспечения, которая требует от корпорации Майкрософт исправления, она не будет поддерживаться. SRS v1 использует TLS 1.0/1.1, который в будущем будет отсутшен корпорацией Майкрософт. Подробнее о подготовке [к отсеву TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). 

## <a name="which-devices-are-affected"></a>На каких устройствах это влияет?

Вот список устройств, на которые влияет это изменение:

- Rl, 12
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Системы комнат SMART](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Параметры обновления

Существует несколько вариантов обновления систем комнат Lync до следующего поколения Комнаты Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Программа trade-in для аппаратного оборудования

Он будет предоставлять обновление до системы [Сротрон SR](https://www.crestron.com/products/featured-solutions/crestron-sr) или эквивалент для всех клиентов, не внося в систему комнат Lync (например, Smart или Polycom LRS). Подробные сведения об этой программе см[. здесь или](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[Отправить по электронной почте](mailto:lrsupgrade@crestron.com) Поддержка LRS Вэлемента.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Обновление до Комнаты Microsoft Teams

Существующие клиенты, использующие RL2 (или Егорон RL200), могут приобрести набор обновлений для обновления текущего набора RL2 до RL3 с минимальными затратами на устройство. Подробные сведения об этой программе см. [здесь](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Обновление систем комнат SMART

Для клиентов, работающих с смарт-LRS, помимо программы для торговли оборудованием в Скайроне, smart также работает над предоставлением решения для обновления до Комнаты Microsoft Teams. Это обновление будет предоставлено службой smart Technologies Inc. клиентам в рамках поддержки продуктов. Подробнее об этом см. [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Что делать?

Мы рекомендуем обновить устройства Lync Room System до Комнаты Microsoft Teams до того, как TLS 1.0/1.1 будет отсутскироваться с помощью указанных выше параметров обновления. Кроме того, вы также можете заменить существующие устройства новыми устройствами, сертифицированными для Комнаты Microsoft Teams. [Подробные сведения см](https://aka.ms/roomdevices). в Комнаты Microsoft Teams [устройствах комнаты](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> Комнаты Microsoft Teams программное обеспечение поддерживает протокол TLS 1.2 от 14 декабря 2018 г. с версией приложения 4.0.64.0. Для локального клиента для включения связи через TLS 1.2 для Комнаты Microsoft Teams требуется накопительное обновление Skype для бизнеса Server 2015 г. (НАКОПИТЕЛЬНЫЙ обновление 9) или накопительный Skype для бизнеса Server 2019 г. Это изменение не должно влиять Skype для бизнеса клиентах Online, так как они соответствуют требованиям клиентов вперед и назад.