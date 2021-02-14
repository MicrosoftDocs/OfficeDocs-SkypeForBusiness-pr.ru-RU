---
title: What's deprecated from Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Эти функции удалены из Skype для бизнеса Server 2019.
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808729"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>What's deprecated from Skype for Business Server 2019

Узнайте о функциях и функциях, неподготовленных в Skype для бизнеса Server 2019. Сведения о новых функциях Skype для бизнеса Server 2019 см. в сведениях о skype для бизнеса [Server 2019.](whats-new.md)

Некоторые функции, для совместимости с предыдущими версиями продукта, включены в Skype для бизнеса Server 2019.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Функции, неподготовленные в Skype для бизнеса Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Шлюзы XMPP для Skype для бизнеса Server

Skype для бизнеса Server 2015 и его предшественники позволяли настраивать прокси-сервер XMPP на edge-сервере и шлюз XMPP на сервере переднего или переднего сервера. Эта функция больше недоступна в Skype для бизнеса Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Сохраняемая беседа для Skype для бизнеса Server

Сервер сохраняемой беседы — это необязательная роль, которая позволяет нескольким пользователям в организации участвовать в беседах комнат чата, которые сохраняются с течением времени. Persistent chat can't be deployed with Skype for Business Server 2019. Эта роль сервера удаляется из построитель топологий, а также из кода. 

Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Зеркальное отражение для Skype для бизнеса Server

SQL зеркальное отражение не может быть развернуто в Skype для бизнеса Server 2019. Другие варианты обеспечения высокой доступности и аварийного восстановления по-прежнему поддерживаются, и вам следует выбрать один из них. Чтобы [просмотреть варианты, см.](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) "Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server".

### <a name="in-place-upgrades"></a>Обновление на месте 

Обновления на месте были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019. Поддержка обновления и сосуществования поддерживается в переходе на Skype для бизнеса [Server 2019](migration/migration-to-skype-for-business-server-2019.md) для получения дополнительных сведений.

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

Поддержка mobility Service, используемая устаревшими мобильными клиентами, больше недоступна в Skype для бизнеса Server 2019. Это было ранее объявлено в Skype для бизнеса Server 2015.

Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов. Пользователям с устаревшими клиентами, использующими Mcx, потребуется обновиться до текущего клиента.

For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Инструменты

Следующие средства будут недоступны для использования в первоначальном выпуске Skype для бизнеса Server 2019:

- Калькулятор планирования мощности Skype для бизнеса Server
- Средства отладки Skype для бизнеса Server
- Средства skype для бизнеса Server Resource Kit (некоторые средства будут удалены)
    - Call Parkometer
    - Консоль пользователя подыском
    - Миграция объявлений с ненаписаным номером

В Skype для бизнеса Server 2019 не поддерживаются следующие средства:

- Методология качества вызовов (но не панель мониторинга качества звонка)
- Система показателей методологии качества вызовов Майкрософт, 1.5
- Средство планирования Skype для бизнеса Server 2015
- Skype для бизнеса Server 2015 Stress and Performance Tool

### <a name="see-also"></a>См. также

[Новые возможности Skype для бизнеса Server 2019](whats-new.md)

[Перенос федерации XMPP](migration/migrating-xmpp-federation.md)
