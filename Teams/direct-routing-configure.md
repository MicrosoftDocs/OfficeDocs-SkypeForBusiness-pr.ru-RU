---
title: Настройка прямой маршрутизации
ms.reviewer: ''
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
description: Узнайте, как настроить Телефон (Майкрософт) прямой маршрутии Системы для подключения к локальной инфраструктуре телефонии Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3152c13b0cf6559964d3926d7c66e7cf376e8
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634898"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

Телефон (Майкрософт) С помощью system Direct Routing вы можете подключить к своей локальной инфраструктуре телефонии Microsoft Teams. В этой статье перечислены высокоуровневые действия, необходимые для подключения поддерживаемого локального пограничного контроллера сеанса (SBC) к прямой маршрутике, а также как настроить для пользователей Teams использовать прямую маршрутику для подключения к телефонной сети общего пользования (STN). Подробные сведения в этой статье можно найти в связанных статьях.  

Сведения о том, является ли direct Routing правильным решением для вашей организации, см. в телефонная система [Direct Routing](direct-routing-landing-page.md). Сведения о предварительных условия и планировании развертывания см. в этой [ссылке.](direct-routing-plan.md)

> [!Tip]
> Вы также можете посмотреть следующий сеанс, чтобы узнать о преимуществах прямой маршрутии, планировании и развертывании: Прямая маршрутная маршрутия [в](https://aka.ms/teams-direct-routing)Microsoft Teams.

Для выполнения действий, которые объясняются в этой статье, администраторам требуется некоторое знакомство с помощью powerShell.) Дополнительные сведения об использовании PowerShell см. в этой [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Прежде чем выполнять действия, указанные в этих статьях, корпорация Майкрософт рекомендует подтвердить, что ваш поставщик SBC уже настроил SBC: 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию коммуникаций на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Документация по развертыванию Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Полный список поддерживаемых SBCs см. в списке контроллеров границ сеанса, сертифицированных для [прямой маршрутики.](direct-routing-border-controllers.md)

Чтобы настроить Телефон (Майкрософт) и позволить пользователям использовать прямую маршрутику, выполните следующие действия: 

- **Шаг 1.** [Подключение SBC с Телефон (Майкрософт) и проверьте подключение](direct-routing-connect-the-sbc.md)
- **Шаг 2.** [Включить для пользователей прямую маршрутику, голосовую и голосовую почту](direct-routing-enable-users.md)
- **Шаг 3.** [Настройка маршрутизов вызовов](direct-routing-voice-routing.md)
- **Шаг 4.** [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Если вы настраивает SBC для нескольких клиентов, также необходимо прочитать статью Настройка [SBC для нескольких клиентов.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Статьи по теме

[Прямая маршрутизация телефонной системы](direct-routing-landing-page.md)

[Планирование прямой маршрутизации](direct-routing-plan.md)