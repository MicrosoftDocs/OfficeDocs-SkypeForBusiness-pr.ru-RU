---
title: Прямая маршрутизация телефонной системы
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
description: Уведомление о прямой маршрутике звонка
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341808"
---
# <a name="manage-call-notifications"></a>Управление уведомлениями о звонках

В этой статье описано, как управлять уведомлениями о звонках для пользователей. Вы можете настроить конечные точки зовов как для Teams, так и для сторонней закрытой ветвной службы Exchange (УАЦ) или контроллера границы сеанса (SBC).  Это полезно, например, если вы хотите одновременно отправить звонок на мобильные и настольные телефоны пользователя.   

На следующей схеме у пользователя Irena есть две конечные точки:

- Конечная точка Teams
- Телефон SIP, подключенный к стороне SBC

При звонке SBC размыкает связь между маршрутизовом телефонной системы и сторонним SBC.


![Схема, показывающая неявные конечные точки Teams](media/direct-routing-call-notification-1.png)

Если звонок принят в Fork 2 (сторонним SBC), Teams создает уведомление о пропущенных звонках.  

Вы можете отключить уведомление "Пропущенный звонок", настроив СКА для отправки отмены в fork 1 следующим образом:

ПРИЧИНА: SIP; cause=200;text"Call completed elsewhere" 

Обратите внимание, что звонок не будет зарегистрирован в записях сведений о звонках телефонной системы Майкрософт как успешный. Этот звонок будет зарегистрирован как "Attempt" с итоговым кодом SIP "487", окончательным подкодомом Майкрософт "540200" и последней фразой кода SIP "Call completed elsewhere".  (Чтобы просмотреть записи подробных данных о звонках, перейдите на портал администрирования Teams, аналитику и отчеты, отчеты об использовании и выберите "Использование ННР".)


На схеме ниже проиллюстрирована схема SIP для Fork 1, объясняется поток зов и ожидаемая ПРИЧИНА в сообщении "Отмена". 

![Схема, показывающая неявные конечные точки Teams](media/direct-routing-call-notification-2.png)
