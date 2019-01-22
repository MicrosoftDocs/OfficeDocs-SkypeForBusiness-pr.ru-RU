---
title: Перенос системы комнаты Lync устройств системе комнаты Скайп версии 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: В данном разделе приведены в этой статье описывается перенос системы комнаты Lync устройств для использования версии 2 Скайп комнаты системного программного обеспечения.
ms.openlocfilehash: 22693913c613f87c3f11ad5b421d771b661d9b91
ms.sourcegitcommit: 502f85e7920b1a9a14f879d6211e10ad8daba69f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2019
ms.locfileid: "29382473"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2

Устройства системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1) достиг [окончания поддержки 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Это означает, что программное обеспечение v1 систем Скайп комнаты больше не будет любой обновлений продукта или исправления больше. Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).

Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.

Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки. Тем не менее если это программное обеспечение достигает ошибки программного обеспечения, которое должно Microsoft для освобождения исправление, он будет не поддерживаться. SRS v1 использует протокол TLS 1.0 / 1.1, которая в будущем является устаревшим корпорацией Майкрософт. Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Скайп помещения системы V2 Добавление поддержки TLS 1.2 и продолжат работу после 31 октября 2018. Скайп для бизнеса в локальной пользователи не должны отключить протокол TLS 1.0/1.1 до версии 2 системы комнаты Скайп объявляет поддержка TLS 1.2, независимо от того, общие рекомендации по амортизации TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Какие устройства будут затронуты?

Ниже приведен список устройств, которые затрагиваются это изменение:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Смарт-систем комнаты](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)


## <a name="upgrade-options"></a>Варианты обновления

Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Программа Trade-in Crestron оборудование

Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права. Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.  

### <a name="crestron-rl2-upgrade-to-srs-v2"></a>Crestron RL2 обновления до версии 2 SRS

Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить обновления пакета обновления текущей RL2 RL3, используя для минимальными затратами на устройство. Ознакомиться с подробными сведениями этой программы [здесь](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Обновление смарт-систем комнаты

Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы. Это обновление будет предоставлено смарт-Technologies Inc. Можно найти дополнительные сведения о этой [здесь](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).

Чтобы использовать этот параметр, клиенты Кроме того необходимо купить адаптера [Logitech экрана совместный доступ](https://www.logitech.com/en-us/product/screen-share) . Корпорация Майкрософт предоставляет инструкции о том, как использовать этот адаптер с версии 2 Скайп комнаты системное программное обеспечение.

Внешний вид инструкции по обновлению на этой странице в ближайшее время.
  
<!-- 
### Summary of upgrade options

This table lists summary of all available options for existing LRS devices:
-->

## <a name="what-should-you-do"></a>Что делать?

Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано. Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2. Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [требования к версии 2 Скайп комнаты систем](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2. Поддержка сенсорного ввода и доски в настоящее время запланированных для системы комнаты Скайп версии 2 и будет добавлен в 2019.

> [!NOTE]
> Программное обеспечение Скайп комнаты системы V2 поддерживает протокол TLS 1.2 по состоянию на 14 декабря 2018 с версией приложения 4.0.64.0. Для локальных пользователей Включение связи через TLS 1.2 для версии 2 Скайп комнаты системы требует Скайп для Business Server 2015 накопительного обновления 9 (CU9) или Скайп Business Server 2019 накопительный пакет обновления 1 (CU1). Изменение не должно затрагивать Скайп для клиентов Business Online мере клиента вперед и назад спецификации.
