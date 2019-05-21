---
title: Что не рекомендуется использовать в Skype для бизнеса Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: эти функции удалены из Skype для бизнеса Server 2019.'
ms.openlocfilehash: a342f98d1a3191064d1678190a0d4b743b40a37f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278114"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Что не рекомендуется использовать в Skype для бизнеса Server 2019

Узнайте о функциях и функциях, которые не рекомендуются в Skype для бизнеса Server 2019. Сведения о новых возможностях Skype для бизнеса Server 2019 можно найти [в разделе что это такое в Skype для бизнеса server 2019](whats-new.md).

Некоторые из выкрывающихся функций включены в Skype для бизнеса Server 2019 для обеспечения совместимости с предыдущими версиями продукта.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Возможности, устаревшие в Skype для бизнеса Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Шлюзы КСМПП для Skype для бизнеса Server

Skype для бизнеса Server 2015 и его предшественники могут настроить на пограничном сервере прокси-сервер с расширенными сообщениями и протоколом доступности КСМПП и шлюз КСМПП на сервере переднего плана или пуле внешних интерфейсов. Эта функция больше не доступна в Skype для бизнеса Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Сохраняемый чат для Skype для бизнеса Server

Сервер сохраняемого чата — это необязательная роль, которая позволяет нескольким пользователям в Организации принимать участие в беседах в чате, которые сохраняются с течением времени. В Skype для бизнеса Server 2019 нельзя разворачивать сохраняемый чат. Эта роль сервера удаляется из построителя топологии и из кода. 

Эта функция доступна в Teams. Дополнительные сведения можно найти в разделе [путешествие из Skype для бизнеса в Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Зеркальное отображение SQL для сервера Skype для бизнеса Server

Зеркальное отображение SQL не может быть развернуто в Skype для бизнеса Server 2019. Другие варианты обеспечения высокой доступности и аварийного восстановления по-прежнему поддерживаются, и вы можете выбрать один из них. Ознакомьтесь со сведениями о том, как [в Skype для бизнеса Server вы можете ознакомиться с высокой надежностью и восстановлением после аварии](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .

### <a name="in-place-upgrades"></a>Обновления на месте 

Обновления на месте были выпущены в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019. Для получения дополнительных сведений обратитесь к разделу [Переход в Skype для бизнеса Server 2019, который](migration/migration-to-skype-for-business-server-2019.md) поддерживается параллельным обновлением.

### <a name="mobility-service-mcx"></a>Служба Mobility Service (МККС)

Поддержка службы Mobility Service, используемая существующими мобильными клиентами, больше не поддерживается в Skype для бизнеса Server 2019. Ранее это было объявлено в Skype для бизнеса Server 2015.

На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов. Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.

Дополнительные сведения можно найти в разделе [планирование мобильных устройств в Skype для бизнеса Server](../SfbServer/plan-your-deployment/mobility.md) и [мобильных клиентах для Skype для бизнеса](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Инструменты

Перечисленные ниже инструменты не будут доступны для использования в первоначальном выпуске Skype для бизнеса Server 2019:

- Калькулятор планирования мощности Skype для бизнеса Server
- Средства отладки в Skype для бизнеса Server
- Средства пакета ресурсов в Skype для бизнеса Server (некоторые инструменты будут удалены)
    - Счетчик парковки вызовов
    - Пользовательская консоль поиска
    - Миграция неназначенного числа объявлений

Следующие средства не поддерживаются в Skype для бизнеса Server 2019:

- Методология качества связи (но не для панели мониторинга качества звонков)
- Система показателей качества звонков (Майкрософт), версия 1.5
- Средство планирования Skype для бизнеса Server 2015
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>См. также

[Новые возможности Skype для бизнеса Server 2019](whats-new.md)

[Перенос федерации XMPP](migration/migrating-xmpp-federation.md)
