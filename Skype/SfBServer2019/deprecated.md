---
title: Что, удаленные из Скайп для Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Эти возможности были удалены из Скайп для Business Server 2019.'
ms.openlocfilehash: 0dd7edda344ec41cc37e5013d18755c29d16c9a9
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835176"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Что, удаленные из Скайп для Business Server 2019

Сведения о возможностях и функциях, которые не поддерживаются в Скайп для Business Server 2019. Сведения о новых возможностях в Скайп Business Server 2019 [возможности Скайп для Business Server 2019](whats-new.md)см.

Некоторые возможности рекомендуется включены в Скайп Business Server 2019 для совместимости с предыдущими версиями продукта.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Функции не поддерживаются в Скайп для Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Шлюзы XMPP для Скайп для Business Server

Скайп Business Server 2015 и ее предшественников позволяет настроить прокси-сервер расширяемая системы обмена сообщениями и присутствия протокола XMPP на пограничном сервере и шлюз XMPP на сервере переднего плана или интерфейсный пул. Эта функция больше не доступен в Скайп для Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Сохраняемый чат для Скайп для Business Server

Persistent Chat Server является дополнительной ролью, которая позволяет нескольким пользователям в вашей организации участвовать в беседах комнаты чата, сохраняющиеся во времени. Сохраняемый чат нельзя развернуть, с Скайп для Business Server 2019. Эта роль сервера удалена построителя топологий, а также из кода. 

Те же функциональные возможности доступны в группах. Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Зеркальное отображение SQL для Скайп для Business Server

Зеркальное отображение SQL нельзя развернуть, с Скайп для Business Server 2019. Другие параметры для обеспечения высокой доступности и аварийного восстановления, по-прежнему поддерживаются и должен выбрать один из них. В разделе [Планирование высокой доступности и аварийного восстановления в Скайп для Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) для просмотра параметров.

### <a name="in-place-upgrades"></a>Обновления на месте 

Обновления на месте были доступны в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019. Параллельное поддерживается обновления и сосуществования, [перехода на Скайп для Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) более подробные сведения.

### <a name="mobility-service-mcx"></a>Служба мобильной связи (Mcx)

Мобильной работы службы поддержки для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019. Это был ранее объявлена в Скайп Business Server 2015.

Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты. Пользователи с прежних версий клиентов, использующих Mcx потребуется обновить до текущего клиента.

Для получения дополнительных сведений см. [Планирование мобильной связи для Скайп для Business Server](../SfbServer/plan-your-deployment/mobility.md) и [сравнение возможностей мобильного клиента для Скайп для бизнеса](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Инструменты

Не будут доступны для использования в первоначальном выпуске Скайп Business Server 2019 следующие средства:

- Калькулятор планирования мощности Skype для бизнеса Server
- Скайп для Business Server средства отладки
- Скайп для Business Server Resource Kit Tools (будут удалены некоторые средства)
    - Счетчик парковки вызовов
    - Поиск пользователя консоли
    - Неназначенный номер объявлений миграции

Для Business Server 2019 с Скайп не поддерживаются следующие средства:

- Вызов качества методика (но не вызывайте панели мониторинга качества)
- Система показателей методика качества звонков Microsoft, версии 1.5
- Средство планирования Skype для бизнеса Server 2015
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>См. также

[Новые возможности Скайп для Business Server 2019](whats-new.md)

[Перенос федерации XMPP](migration/migrating-xmpp-federation.md)
