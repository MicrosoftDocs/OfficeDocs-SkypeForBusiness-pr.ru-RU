---
title: 'Teams: управление уведомлениями о звонках'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Уведомление о прямом маршрутинге звонка
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b251040f9433d9ac51b388d12fa530b7c982e0773580d6ac69d41825fbba1ae6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848324"
---
# <a name="manage-call-notifications"></a>Управление уведомлениями о звонках

В этой статье описано, как управлять уведомлениями о звонках для пользователей. Конечные точки звонка можно настроить как для Teams, так и для сторонней частной ветви Exchange (PBX) или контроллера границы сеанса (SBC).  Эта настройка удобна, например, если вы хотите одновременно отправить звонок на мобильные и настольные телефоны пользователя.   

На следующей схеме У Ирены есть две конечные точки:

- A Teams конечной точки
- Телефон SIP, подключенный к стороне SBC

При поступает звонок, SBC forks the call between телефонная система Direct Routing and the third-party SBC.


![Диаграмма, на которой показаны Teams конечные точки](media/direct-routing-call-notification-1.png)

Если звонок принимается на fork 2 (сторонним SBC), Teams создает уведомление о пропущенных звонках.  

Вы можете отключить уведомление "Пропущенный звонок", настроив SBC для отправки отмены в fork 1 следующим образом:

ПРИЧИНА: SIP; cause=200;text"Звонок завершен в другом месте" 

Звонок не будет зарегистрирован в записях о звонках Телефон (Майкрософт) система в качестве успешного звонка. Звонок будет зарегистрирован как "Попытка" с итоговым кодом SIP "487", итоговым подкодомом Майкрософт "540200" и фразой кода SIP "Звонок выполнен в другом месте".  (Чтобы просмотреть записи о звонках, перейдите на портал администрирования Teams, аналитику и отчеты, отчеты об использовании, а затем выберите Использование ОКП.)


На приведенной ниже схеме показано, как выглядит SIP для Fork 1, объясняется поток зова и ожидаемая ПРИЧИНА в сообщении об отмене. 

![На схеме показаны висячая Teams конечных точек](media/direct-routing-call-notification-2.png)
