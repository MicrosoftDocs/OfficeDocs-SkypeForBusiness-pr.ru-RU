---
title: Настройка прямой маршрутизации
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить прямую маршрутизацию Майкрософт для подключения локальной инфраструктуры телефонной связи к телефонной системе Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291405"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

Прямая маршрутизация позволяет подключить локальную инфраструктуру телефонии к Microsoft Teams. В этой статье перечислены общие действия, необходимые для подключения поддерживаемого локального пограничного контроллера сеансов (SBC) к прямой маршрутизации, а также сведения о том, как настроить пользователей Teams для использования прямой маршрутизации для подключения к телефонной сети общего пользования (ТСОП). В этой статье приводятся ссылки на связанные статьи для получения дополнительных сведений.  

Сведения о том, является ли прямая маршрутизация правильным решением для вашей организации, см. в разделе о вариантах подключения [по ТСОП](pstn-connectivity.md). Сведения о предварительных требованиях и планировании развертывания см. в статье [Plan Direct Routing](direct-routing-plan.md).

Для выполнения действий, описанных в этой статье, администраторам требуется некоторое знание командлетов PowerShell. Дополнительные сведения об использовании PowerShell см. в разделе "Настройка компьютера [для](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell". 

Перед выполнением действий, описанных в этих статьях, корпорация Майкрософт рекомендует убедиться, что ваш SBC уже настроен, как рекомендовано поставщиком SBC: 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию связи на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Документация по развертыванию Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Полный список поддерживаемых контроллеров безопасности см. в разделе "Пограничные контроллеры сеансов", [сертифицированные для прямой маршрутизации](direct-routing-border-controllers.md).

Чтобы настроить телефонную систему и разрешить пользователям использовать прямую маршрутизацию, выполните следующие действия. 

- **Шаг 1.** [Подключение SBC с помощью телефонной системы и проверка подключения](direct-routing-connect-the-sbc.md)
- **Шаг 2.** [Включение прямой маршрутизации, голосовой и голосовой почты для пользователей](direct-routing-enable-users.md)
- **Шаг 3.** [Настройка маршрутизации вызовов](direct-routing-voice-routing.md)
- **Шаг 4.** [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Если вы настраиваете SBC для нескольких клиентов, вам также потребуется прочитать "Настройка [SBC для нескольких клиентов"](direct-routing-sbc-multiple-tenants.md).

## <a name="support-boundaries"></a>Границы поддержки
Корпорация Майкрософт поддерживает телефонную систему с прямой маршрутизацией только при использовании с сертифицированными устройствами. При возникновении проблем сначала необходимо обратиться в службу поддержки поставщика SBC. При необходимости поставщик SBC перенаправит проблему в Майкрософт по внутренним каналам. Корпорация Майкрософт оставляет за собой право отклонять запросы, направленные в службу поддержки, при подключении к телефонной системе несертифицированных устройств с прямой маршрутизацией. Если корпорация Майкрософт определяет, что проблема прямой маршрутизации клиента связана с устройством SBC поставщика, клиенту необходимо будет снова обратиться за поддержкой к поставщику SBC.

## <a name="related-topics"></a>См. также

[Планирование голосового решения](cloud-voice-landing-page.md)

[Параметры подключения ТСОП](pstn-connectivity.md)

[Планирование прямой маршрутизации](direct-routing-plan.md)
