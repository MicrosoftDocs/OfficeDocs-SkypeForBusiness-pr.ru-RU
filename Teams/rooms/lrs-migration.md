---
title: Перенос устройств Lync Room System в Комнаты Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Из этой темы вы узнаете, как перенести устройства Lync Room System для использования Комнаты Microsoft Teams программного обеспечения.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117527"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Перенос устройств Lync Room System (LRS) в Комнаты Microsoft Teams

Поддержка устройств Lync Room System (LRS) с программным обеспечением Skype Room System версии 1 (SRS версии 1) заканчивается 9 октября [2018 г.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления. Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".

Комнаты Microsoft Teams программное обеспечение работает с Microsoft Teams в дополнение к Skype для бизнеса Server и веб-службам для собраний и звонков на Комнаты Microsoft Teams устройствах.

Существующие устройства **могут продолжать** работать после окончания поддержки программного обеспечения Skype Room System 1. Однако если это программное обеспечение попадает в ошибку программного обеспечения, которая требует от корпорации Майкрософт исправления, она не будет поддерживаться. SRS v1 использует TLS 1.0/1.1, который в будущем будет отсутшен корпорацией Майкрософт. Подробнее о подготовке [к отсеву TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>На каких устройствах это влияет?

Вот список устройств, на которые влияет данное изменение:

- Rl, 12
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Системы комнат SMART](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Параметры обновления

Существует несколько вариантов обновления систем комнат Lync до следующего поколения Комнаты Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Программа trade-in для аппаратного оборудования

Он будет предоставлять обновление до системы "Нелинейный [SR"](https://www.crestron.com/products/featured-solutions/crestron-sr) или эквивалент для всех клиентов, не внося в систему комнат Lync (например, Smart или Polycom LRS). Подробные сведения об этой программе [см. здесь или](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[электронная почта](mailto:lrsupgrade@crestron.com) Поддержка LRS Вэлемента.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Обновление до Комнаты Microsoft Teams

Существующие клиенты, использующие RL2 (или Егорон RL200), могут приобрести набор обновлений для обновления текущего набора RL2 до RL3 с минимальными затратами на устройство. Подробные сведения об этой программе см. [здесь.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Обновление систем комнат SMART

Для клиентов, работающих с смарт-LRS, помимо программы для торговли оборудованием Вайрона, smart также работает над предоставлением решения для обновления до Комнаты Microsoft Teams. Это обновление будет предоставлено службой smart Technologies Inc. клиентам в рамках поддержки продуктов. Подробнее об этом см. [здесь.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Что делать?

Мы рекомендуем обновить устройства Lync Room System до Комнаты Microsoft Teams до отзыва TLS 1.0/1.1 с помощью указанных выше параметров обновления. Кроме того, вы также можете заменить существующие устройства новыми устройствами, сертифицированными для Комнаты Microsoft Teams. Подробные [сведения см.](https://aka.ms/roomdevices) в Комнаты Microsoft Teams [устройствах комнаты.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Комнаты Microsoft Teams программное обеспечение поддерживает протокол TLS 1.2 от 14 декабря 2018 г. с версией приложения 4.0.64.0. Для локального клиента для включения связи через TLS 1.2 для Комнаты Microsoft Teams требуется накопительное обновление Skype для бизнеса Server 2015 г. (НАКОПИТЕЛЬНЫЙ обновление 9) или накопительный Skype для бизнеса Server 2019 г. Это изменение не должно влиять Skype для бизнеса клиентах Online, так как они соответствуют требованиям вперед и назад.