---
title: Перенос системы комнаты Lync устройств комнат группами Майкрософт
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: В данном разделе приведены в этой статье описывается перенос устройств Lync комнаты системы на использование программного обеспечения Microsoft группами комнат.
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013017"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Перенос системы Lync комнаты (LRS) устройств для комнат группами Майкрософт

Устройства системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1) достиг [окончания поддержки 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Это означает, что программное обеспечение v1 систем Скайп комнаты больше не будет любой обновлений продукта или исправления больше. Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства Microsoft группами комнат.

Комнат группы Microsoft works программного обеспечения с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех комнатах группы Microsoft поддерживаемых устройств.

Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки. Тем не менее если это программное обеспечение достигает ошибки программного обеспечения, которое должно Microsoft для освобождения исправление, он будет не поддерживаться. SRS v1 использует протокол TLS 1.0 / 1.1, которая в будущем является устаревшим корпорацией Майкрософт. Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Комнат группами Майкрософт Добавление поддержки TLS 1.2 и продолжат работу после 31 октября 2018. Скайп для бизнеса в локальной клиенты не следует отключить TLS 1.0/1.1, пока не комнат группами Майкрософт объявляет поддержка TLS 1.2, независимо от того, общие рекомендации по амортизации TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Какие устройства будут затронуты?

Ниже приведен список устройств, которые затрагиваются это изменение:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Смарт-систем комнаты](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Варианты обновления

Существует несколько вариантов обновления Lync комнаты систем следующего поколения комнат группами Майкрософт.

### <a name="crestron-hardware-trade-in-program"></a>Программа Trade-in Crestron оборудование

Crestron будет предоставлять обновления для [системы Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права для всех клиентов системы комнаты Lync не Crestron (например разумная или Polycom LRS). Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, -->[электронной почты](mailto:lrsupgrade@crestron.com) Поддержка Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Обновление Crestron RL2 комнат группами Майкрософт

Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить обновления пакета обновления текущей RL2 RL3, используя для минимальными затратами на устройство. Ознакомиться с подробными сведениями этой программы [здесь](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Обновление смарт-систем комнаты

Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования СМАРТ также работает на предоставление решений для обновления до Microsoft группами комнат. Это обновление предоставлено смарт-Inc. технологии для клиентов в группе технической поддержки. Можно найти дополнительные сведения о этой [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Что делать?

Мы рекомендуем вам для обновления устройств системы комнаты Lync комнат группами Майкрософт перед амортизации TLS 1.0/1.1, с помощью варианты обновления, перечисленных выше. Кроме того также можно замена существующего устройства на новых устройств, сертифицированных для комнат группами Майкрософт. Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [requirements комнат группами Майкрософт](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Функциональные возможности сенсорного ввода и доску еще не поддерживается в комнат группами Майкрософт. Поддержка сенсорного ввода и доски в данный момент запланировано для комнат группами Майкрософт и добавляются в 2019.

> [!NOTE]
> Программное обеспечение комнат группами Майкрософт поддерживает протокол TLS 1.2 по состоянию на 14 декабря 2018 с версией приложения 4.0.64.0. Для локальных пользователей обеспечение взаимодействия через TLS 1.2 для комнат группы Microsoft требует Скайп Business Server 2015 накопительного обновления 9 (CU9) или Скайп Business Server 2019 накопительный пакет обновления 1 (CU1). Изменение не должно затрагивать Скайп для клиентов Business Online мере клиента вперед и назад спецификации.
