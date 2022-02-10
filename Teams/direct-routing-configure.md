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
description: Узнайте, как настроить прямую маршрутику Майкрософт для подключения локальной инфраструктуры телефонии к Teams телефонная система.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518581"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

Прямая маршрутная маршрутия позволяет подключить к своей локальной инфраструктуре телефонии Microsoft Teams. В этой статье перечислены высокоуровневые действия, необходимые для подключения поддерживаемого локального пограничного контроллера сеанса (SBC) к прямой маршрутике, а также как настроить для пользователей Teams использовать прямую маршрутику для подключения к телефонной сети общего пользования (STN). Подробные сведения в этой статье можно найти в связанных статьях.  

Сведения о том, является ли прямая маршрутия правильным решением для вашей организации, см. в параметрах подключения через [ДНР](pstn-connectivity.md). Сведения о предварительных условия и планировании развертывания см. в этой [ссылке](direct-routing-plan.md).

Для выполнения действий, которые объясняются в этой статье, администраторам требуется некоторое знакомство с помощью powerShell.) Дополнительные сведения об использовании PowerShell см. в этой [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Прежде чем выполнять действия, указанные в этих статьях, корпорация Майкрософт рекомендует подтвердить, что ваш поставщик SBC уже настроил SBC: 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию коммуникаций на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Документация по развертыванию Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Полный список поддерживаемых SBCs см. в списке Контроллеры границ сеанса, удостоверенные для [прямой маршрутики](direct-routing-border-controllers.md).

Чтобы настроить телефонная система и позволить пользователям использовать прямую маршрутику, выполните указанные здесь действия. 

- **Шаг 1.** [Подключение SBC с помощью телефонная система и проверки подключения](direct-routing-connect-the-sbc.md)
- **Шаг 2.** [Включить для пользователей прямую маршрутику, голосовую и голосовую почту](direct-routing-enable-users.md)
- **Шаг 3.** [Настройка маршрутизов  вызовов](direct-routing-voice-routing.md)
- **Шаг 4.** [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Если вы настраивали SBC для нескольких клиентов, также необходимо прочитать статью Настройка [SBC для нескольких клиентов](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Статьи по теме

[Планирование голосового решения](cloud-voice-landing-page.md)

[Параметры подключения через ДНР](pstn-connectivity.md)

[Планирование прямой маршрутизации](direct-routing-plan.md)