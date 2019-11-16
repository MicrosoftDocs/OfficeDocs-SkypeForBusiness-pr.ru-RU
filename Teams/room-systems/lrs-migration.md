---
title: Миграция системных устройств Lync в комнаты Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: В этой статье рассказывается о том, как переносить системные устройства комнат Lync для использования программного обеспечения Microsoft Teams.
ms.openlocfilehash: 377e901446d69e0956ff981b1b45686c949cf61c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675363"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Миграция устройств из системы комнаты Lync (ЛРС) в комнаты Microsoft Teams

Система управления комнатой Lync (ЛРС) с помощью программного обеспечения системы комнат Skype версии 1 (SRS v1) закончила [поддержку до 9 октября 2018 г](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018). Это означает, что для приложения "Системы комнат Skype" версии 1 больше не будут выпускаться обновления и исправления. Пользователям устройств системы комнат Lync, использующие приложение "Системы комнат Skype" версии 1, рекомендуем установить на своих устройствах приложение "Комнаты Microsoft Teams".

Программы Microsoft Teams работают с Microsoft Teams в дополнение к Skype для бизнеса Server и Интернет-службам для собраний и звонков по всем поддерживаемым устройствам Microsoft Teams.

Существующие **устройства** продолжают работать после завершения поддержки программного обеспечения для системы комнат Skype v1. Тем не менее, если это программное обеспечение обнаружено в программной ошибке, требующей от корпорации Майкрософт устранения исправлений, она не будет поддерживаться. SRS v1 использует TLS 1.0/1,1, который будет использоваться корпорацией Майкрософт в будущем. Вы можете узнать больше о том, как [подготовиться к использованию протокола TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Комнаты Microsoft Teams — это добавление поддержки TLS 1,2 и продолжение работы после 31 октября 2018 г. Пользователи Skype для бизнеса с локальной версией не должны отключать TLS 1.0/1.1, пока в Microsoft Teams не будет объявлено о поддержке TLS 1,2, независимо от того, какие общие правила рекомендуются для использования TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Какие устройства затронуты?

Ниже приведен список устройств, на которые влияет это изменение:

- Крестрон РЛ
- [Крестрон RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Системы SMART rooming](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Варианты обновления

Существует несколько вариантов обновления систем комнат Lync до нового поколения комнат Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Программа крестрон оборудования

Крестрон предоставит обновление [системы КРЕСТРОН SR](https://www.crestron.com/products/featured-solutions/crestron-sr) или эквивалент для всех пользователей системы, не являющихся крестрон, например Smart или Polycom ЛРС. Просмотреть подробные сведения об этой [программе или](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[Электронная почта](mailto:lrsupgrade@crestron.com) Поддержка крестрон ЛРС.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Крестрон RL2 переход к комнатам Microsoft Teams

Существующие Крестрон RL2 (также называемые Крестрон RL200) пользователи могут получить комплект обновления, чтобы обновить текущую RL2 до RL3 с минимальной стоимостью на устройство. Ознакомьтесь с подробными сведениями об [этой программе.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Обновление системы SMART Room

Для пользователей SMART ЛРС, отличных от Крестрон аппаратной торговли, SMART также работает над предоставлением решения для перехода на комнаты Microsoft Teams. Это обновление будет предоставляться ИНТЕЛЛЕКТУАЛЬНым технологиям Inc. клиентам, которые поддерживаются в рамках поддержки продуктов. Подробнее об этом можно узнать [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Что нужно сделать?

Мы рекомендуем вам запланировать обновление системных устройств Lync для комнат Microsoft Teams до устаревшей версии TLS 1.0/1.1 с помощью вариантов обновления, описанных выше. Кроме того, вы можете заменить существующие устройства новыми устройствами, сертифицированными для комнат Microsoft Teams. Ознакомьтесь со сведениями о [комнатах](https://aka.ms/roomdevices) , а также ознакомьтесь с [требованиями к комнатам Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Функции сенсорного ввода и доски пока не поддерживаются в комнатах Microsoft Teams. Поддержка сенсорного ввода и доски в настоящее время запланирована для комнат Microsoft Teams и будет добавлена в 2019.

> [!NOTE]
> Программы Microsoft Teams поддерживают протокол TLS 1,2 на 14 декабря 2018 г. с версией приложения 4.0.64.0. Для локальных пользователей, обеспечивающих связь по протоколу TLS 1,2 для комнат Microsoft Teams, требуется Skype для бизнеса Server 2015 (CU9) или Skype для бизнеса Server 2019 накопительный пакет обновления 1 (CU1). Изменения не должны повлиять на пользователей Skype для бизнеса Online в отношении изменений, пересылаемых в соответствии с клиентами, в обратном направлении.
