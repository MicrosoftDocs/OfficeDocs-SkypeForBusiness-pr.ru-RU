---
title: Перенос устройств Lync Room System в комнаты Microsoft Teams
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
description: Из этой темы вы узнаете, как перенести устройства Lync Room System для использования программного обеспечения комнат Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662624"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Перенос устройств Lync Room System (LRS) в комнаты Microsoft Teams

Поддержка устройств с системой комнат Skype версии 1 (SRS версии 1) для устройств с Lync Room System (SRS версии 1) заканчивается 9 октября [2018 г.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления. Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".

Программное обеспечение комнат Microsoft Teams работает с Microsoft Teams в дополнение к службам Skype для бизнеса Server и Online для собраний и звонков на всех поддерживаемых устройствах комнат Microsoft Teams.

Существующие устройства **могут продолжать** работать после окончания поддержки программного обеспечения Skype Room System 1. Однако если данное программное обеспечение устраняет ошибку, из-за ошибки в программном обеспечении, из-за которую корпорация Майкрософт должна выпустить исправление, оно не будет поддерживаться. SRS v1 использует TLS 1.0/1.1, который в будущем будет переупрешен корпорацией Майкрософт. Подробнее о подготовке к [деpreprecation TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>На каких устройствах это влияет?

Вот список устройств, на которые влияет это изменение:

- Ronron RL
- [12(12)](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Системы комнат SMART Room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Варианты обновления

Существует несколько вариантов обновления систем комнат Lync до нового поколения комнат Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Программа trade-in для аппаратного оборудования

Скайпрон обновит систему Lync Room System (например, Smart или Polycom LRS) до системы [Lyron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) или эквивалентна ее для всех пользователей. Подробные сведения об этой программе см. [здесь или](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[электронная почта](mailto:lrsupgrade@crestron.com) Поддержка Скайпа LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Обновление Скайпа RL2 до комнат Microsoft Teams

Существующие клиенты с использованием RL2 (Это также называется RL200) могут приобрести комплект обновления для обновления текущего набора RL2 до RL3 с минимальными затратами на устройство. Подробные сведения об этой программе см. [здесь.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Обновление системы smart Room Systems

Для клиентов, работающих с смарт-LRS, помимо программы товарооборота с оборудованием Висяка, SMART также работает над предоставлением решения для обновления до комнат Microsoft Teams. Это обновление будет предоставляться технологией SMART Technologies Inc. для клиентов в рамках поддержки продуктов. Подробнее об этом см. [здесь.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Что вам делать?

Мы рекомендуем обновить устройства Lync Room System до комнат Microsoft Teams до отзыва TLS 1.0/1.1 с помощью указанных выше параметров обновления. Кроме того, можно заменить существующие устройства новыми устройствами, сертифицированными для комнат Microsoft Teams. Подробные [сведения см.](https://aka.ms/roomdevices) в сведениях о устройствах комнат, а также требованиях к комнатам [Microsoft Teams.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Программное обеспечение комнат Microsoft Teams поддерживает протокол TLS 1.2 от 14 декабря 2018 г. с версией приложения 4.0.64.0. Для локального клиента для включения связи через TLS 1.2 для комнат Microsoft Teams требуется Skype для бизнеса Server 2015 с накопительным обновлением 9 (НАКОПИТЕЛЬ) или Skype для бизнеса Server 2019 с накопительным обновлением 1 (НАКОПИТЕЛЬ1). Это изменение не должно повлиять на клиентов Skype для бизнеса Online, так как они соответствуют требованиям клиентов вперед и назад.
