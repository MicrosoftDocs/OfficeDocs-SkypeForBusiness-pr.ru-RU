---
title: What's deprecated from Skype для бизнеса Server 2019
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Сводка. Эти функции были удалены из Skype для бизнеса Server 2019 г.
ms.openlocfilehash: 65229e091d903ca18fee89224e45aedef8c0ca40
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771734"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>What's deprecated from Skype для бизнеса Server 2019

Узнайте о функциях и функциях, которые не представлены в Skype для бизнеса Server 2019 г. Сведения о новых Skype для бизнеса Server 2019 г. см. в Skype для бизнеса Server [2019 г.](whats-new.md)

Некоторые функции без акцента включены в Skype для бизнеса Server 2019 г. для совместимости с предыдущими версиями продукта.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Функции, которые были Skype для бизнеса Server 2019 г. 

В 2019 г. ниже представлены следующие функции и функции, Skype для бизнеса Server 2019 г.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Шлюзы XMPP для Skype для бизнеса Server

Skype для бизнеса Server 2015 г. и его предшественники позволили настроить прокси-прокси протокола обмена сообщениями и присутствия (XMPP) на edge Server и шлюз XMPP на переднем или переднем конце пула. Эта функция больше недоступна в Skype для бизнеса Server 2019 г.

### <a name="persistent-chat-for-skype-for-business-server"></a>Постоянный чат для Skype для бизнеса Server

Постоянный сервер чата — это необязательная роль, которая позволяет нескольким пользователям в организации участвовать в беседах в чате, которые сохраняются с течением времени. Постоянный чат не может быть развернут с Skype для бизнеса Server 2019 г. Эта роль сервера удаляется из Topology Builder и из кода. 

Такая же функциональность доступна в Teams. Дополнительные сведения см. в ссылке Начало работы [с обновлением Microsoft Teams обновления.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Зеркальное Skype для бизнеса Server

SQL Зеркальное отражение не может быть развернуто с Skype для бизнеса Server 2019 г. Другие варианты обеспечения высокой доступности и аварийного восстановления по-прежнему поддерживаются, и вы должны выбрать один из них. См. в обзоре Plan [for high availability and disaster recovery in Skype для бизнеса Server,](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) чтобы просмотреть параметры.

### <a name="in-place-upgrades"></a>Обновление на месте 

Обновления на месте были доступны в Skype для бизнеса Server 2015 г., но больше не поддерживаются Skype для бизнеса Server 2019 г. Поддерживается одностороннее обновление и сосуществование. Дополнительные сведения см. в [Skype для бизнеса Server Migration to Skype для бизнеса Server 2019 г.](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Служба мобильности (Mcx)

Все современные Skype для бизнеса мобильные клиенты уже используют веб-API единой связи (UCWA) для поддержки обмена мгновенными сообщениями,присутствия и контактов. Пользователям с устаревшими клиентами с помощью Mcx потребуется обновиться до текущего клиента.

Дополнительные сведения см. в материале [Plan for Mobility for Skype для бизнеса Server](../SfbServer/plan-your-deployment/mobility.md) и Mobile client feature comparison for [Skype для бизнеса.](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="tools"></a>Инструменты

Следующие средства не будут доступны для использования в начальном выпуске Skype для бизнеса Server 2019 г.:

- Калькулятор планирования мощности Skype для бизнеса Server
- Skype для бизнеса Server Средства отладки
- Skype для бизнеса Server Средства набора ресурсов (некоторые средства будут удалены)
    - Call Parkometer
    - Консоль пользователя Lookup
    - Миграция без присвоения номера

Следующие средства не поддерживаются с Skype для бизнеса Server 2019 г.:

- Методология качества вызовов (но не панель мониторинга качества вызовов)
- Система показателей качества вызовов Microsoft Call, v1.5
- Skype для бизнеса Server 2015 г.
- Skype для бизнеса Server 2015 г. Средство стресса и производительности

### <a name="see-also"></a>См. также

[Новые возможности в Skype для бизнеса Server 2019 г.](whats-new.md)

[Перенос федерации XMPP](migration/migrating-xmpp-federation.md)
