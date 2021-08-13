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
ms.openlocfilehash: 8326a9eb1f7a6ad9fb13c622c4f03d0f9af40af8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233044"
---
# <a name="manage-call-notifications"></a>Управление уведомлениями о звонках

В этой статье описано, как управлять уведомлениями о звонках для пользователей. Конечные точки звонка можно настроить как для Teams, так и для сторонней частной ветви Exchange (PBX) или контроллера границы сеанса (SBC).  Эта настройка удобна, например, если вы хотите одновременно отправить звонок на мобильные и настольные телефоны пользователя.   

На следующей схеме Ирена имеет две конечные точки:

- A Teams конечной точки
- Телефон SIP, подключенный к стороне SBC

Когда поступает звонок, SBC forks the call between телефонная система Direct Routing and the third-party SBC.


![Диаграмма, на которой показаны Teams с разноназначными конечными точками](media/direct-routing-call-notification-1.png)

Если звонок принимается на fork 2 (сторонним SBC), Teams создает уведомление о пропущенных звонках.  

Вы можете отключить уведомление "Пропущенный звонок", настроив SBC для отправки отмены в fork 1 следующим образом:

ПРИЧИНА: SIP; cause=200;text"Звонок завершен в другом месте" 

Звонок не будет зарегистрирован в записях о звонках Телефон (Майкрософт) система в качестве успешного звонка. Звонок будет зарегистрирован как "Попытка" с итоговым кодом SIP "487", итоговым подкодомом Майкрософт "540200" и фразой кода SIP "Звонок выполнен в другом месте".  (Чтобы просмотреть записи о звонках, перейдите на портал администрирования Teams, аналитику и отчеты, отчеты об использовании и выберите Использование ОКП.)


На приведенной ниже схеме показано, каков SIP-график для Fork 1, объясняется поток зова и ожидаемая ПРИЧИНА в сообщении "Отмена". 

![На схеме показаны висячая Teams конечных точек](media/direct-routing-call-notification-2.png)
