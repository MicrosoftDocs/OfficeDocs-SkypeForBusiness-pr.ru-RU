---
title: Настройка прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
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
description: Узнайте, как настроить прямую маршрутику microsoft Phone System для подключения локальной инфраструктуры телефонии к Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122243"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

Прямая маршрутия в телефонной системе Майкрософт позволяет подключить к Microsoft Teams свою локальное инфраструктуру телефонии. В этой статье перечислены высокоуровневые действия, необходимые для подключения поддерживаемого локального граничного контроллера сеанса (SBC) к прямой маршрутике, а также настройка использования прямой маршрутии для подключения к телефонной сети общего пользования (STN) пользователей Teams. Эта статья ссылок на статьи со ссылками на подробные сведения.  

Сведения о том, является ли прямая маршрутизации правильным решением для вашей организации, см. в подсистеме телефонной [системы.](direct-routing-landing-page.md) Сведения о необходимых предварительных условиях и планировании развертывания см. в плане [прямой маршрутации.](direct-routing-plan.md)

> [!Tip]
> Вы также можете посмотреть этот сеанс, чтобы узнать о преимуществах прямой маршрутинга, планировании и развертывании: [Direct Routing в Microsoft Teams.](https://aka.ms/teams-direct-routing)

Для выполнения действий, которые объясняются в этой статье, администраторам необходимо ознакомиться с помощью cmdlets PowerShell. Дополнительные сведения об использовании PowerShell см. в [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Прежде чем выполнять действия, указанные в этих статьях, корпорация Майкрософт рекомендует подтвердить, что ваш поставщик SBC уже настроил SBC: 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию информационного сообщения на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Документация по развертыванию Metasw deployment](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Полный список поддерживаемых SBCs см. в списке граничных контроллеров сеанса, сертифицированных для [прямой маршрутики.](direct-routing-border-controllers.md)

Чтобы настроить телефонную систему Майкрософт и позволить пользователям использовать прямую маршрутику, выполните следующие действия: 

- **Шаг 1.** [Подключение SBC к телефонной системе Майкрософт и проверка подключения](direct-routing-connect-the-sbc.md)
- **Шаг 2.** [Включить для пользователей прямую маршрутику, голосовую и голосовую почту](direct-routing-enable-users.md)
- **Шаг 3.** [Настройка голосовой маршрутии](direct-routing-voice-routing.md)
- **Шаг 4.** [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Если вы настраивает SBC для нескольких клиентов, также необходимо прочитать статью "Настройка [SBC для нескольких клиентов".](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Статьи по теме

[Прямая маршрутизация телефонной системы](direct-routing-landing-page.md)

[Планирование прямой маршрутизации](direct-routing-plan.md)