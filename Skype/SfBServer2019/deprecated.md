---
title: Устаревшие возможности Skype для бизнеса Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Эти функции удалены из Skype для бизнеса Server 2019.
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125222"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Устаревшие возможности Skype для бизнеса Server 2019

Сведения о функциях и функциях, устаревших в Skype для бизнеса Server 2019. Сведения о новых возможностях Skype для бизнеса Server 2019 можно найти в статье сведения о новых возможностях [Skype для бизнеса server 2019](whats-new.md).

Для обеспечения совместимости с предыдущими версиями продукта в Skype для бизнеса Server 2019 включены некоторые функции в Skype для бизнеса Server.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Функции, устаревшие в Skype для бизнеса Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Шлюзы XMPP для Skype для бизнеса Server

Skype для бизнеса Server 2015 и его предшественники позволяли настраивать прокси-сервер Extensible Messaging and Presence Protocol (XMPP) на пограничном сервере и шлюзе XMPP на сервере переднего плана или интерфейсном пуле. Эта функциональная возможность больше недоступна в Skype для бизнеса Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Сохраняемый чат для Skype для бизнеса Server

Сервер сохраняемого чата — это необязательная роль, которая позволяет нескольким пользователям в Организации участвовать в беседах в комнате чата, сохраняемых с течением времени. Сохраняемый чат не может быть развернут в Skype для бизнеса Server 2019. Эта роль сервера удаляется из построителя топологий, а также из кода. 

В Teams доступны те же функции. Для получения дополнительных сведений обратитесь [к разделу Начало обновления Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Зеркальное отображение SQL для Skype для бизнеса Server

Зеркальное отображение SQL невозможно развернуть с помощью Skype для бизнеса Server 2019. Другие варианты обеспечения высокой доступности и аварийного восстановления поддерживаются, и вы можете выбрать один из них. Ознакомьтесь с разрешениями " [Планирование высокой доступности и аварийного восстановления" в Skype для бизнеса Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) , чтобы просмотреть варианты.

### <a name="in-place-upgrades"></a>Обновление на месте 

Обновление на месте было доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Параллельное обновление и поддержка сосуществования можно найти в статье [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) для получения дополнительных сведений.

### <a name="mobility-service-mcx"></a>Служба Mobility Service (MCX)

Поддержка службы Mobility Service, используемая устаревшими мобильными клиентами, больше недоступна в Skype для бизнеса Server 2019. Ранее оно было объявлено в Skype для бизнеса Server 2015.

Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA), чтобы поддерживать обмен мгновенными сообщениями, сведения о присутствии и контакты. Пользователям прежних версий клиентов, использующих MCX, необходимо выполнить обновление до текущего клиента.

Более подробную информацию можно узнать в статье [Plan for Mobile for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile Client, сравнение функций для Skype для бизнеса](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Средства

Следующие средства не будут доступны для использования в первоначальном выпуске Skype для бизнеса Server 2019:

- Калькулятор планирования мощности Skype для бизнеса Server
- Средства отладки Skype для бизнеса Server
- Средства набора ресурсов Skype для бизнеса Server (некоторые инструменты будут удалены)
    - Вызов Parkometer
    - Консоль поиска пользователей
    - Миграция неназначенных объявлений номеров

Следующие средства не поддерживаются в Skype для бизнеса Server 2019:

- Методология качества вызовов (но не панель мониторинга качества вызовов)
- Система показателей для методологии качества вызовов Майкрософт, версия 1.5
- Средство планирования Skype для бизнеса Server 2015
- Средство нагрузочного тестирования и производительности Skype для бизнеса Server 2015

### <a name="see-also"></a>См. также

[Новые возможности Skype для бизнеса Server 2019](whats-new.md)

[Миграция Федерации XMPP](migration/migrating-xmpp-federation.md)
