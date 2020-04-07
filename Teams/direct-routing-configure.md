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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Сведения о том, как настроить прямую маршрутизацию Microsoft Phone System.
ms.openlocfilehash: b596e5acb0002ad90f5c0298b56973f2490ad2e6
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170587"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

Прямая маршрутизация Microsoft Phone System позволяет подключать локальную инфраструктуру телефонной связи с Microsoft Teams. В этой статье перечислены общие действия, которые необходимо выполнить, чтобы подключить поддерживаемый локальный контроллер рабочего места (SBC) для прямой маршрутизации и настроить пользователей Teams прямо на использование прямой маршрутизации для подключения к коммутируемой телефонной сети с открытым коммутируемым подключением (КТСОП). В этой статье приведены ссылки на статьи с подробными сведениями о ней.  

Сведения о том, является ли прямая маршрутизация подходящего решения для вашей организации, можно найти в разделе [Прямая маршрутизация телефонной системы](direct-routing-landing-page.md). Сведения о предварительных требованиях и планировании развертывания можно найти в разделе [Планирование прямого маршрутизации](direct-routing-plan.md).

> [!Tip]
> Вы также можете узнать о преимуществах прямой маршрутизации, о том, как ее планировать и развертывать в следующем сеансе: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing).

Чтобы выполнить шаги, описанные в этой статье, администраторы должны ознакомиться с командлетами PowerShell. Дополнительные сведения об использовании PowerShell можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Перед выполнением действий, описанных в этой статье, корпорация Microsoft рекомендует подтвердить, что ваш SBC уже настроен в соответствии с рекомендациями вашего поставщика SBC. 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию связи с лентой](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию системы TE (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Документация по развертыванию Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Полный список поддерживаемых SBCs можно найти в разделе [список контроллеров границ сеансов, сертифицированных для прямого маршрутизации](direct-routing-border-controllers.md).

Чтобы настроить телефонную систему Microsoft и разрешить пользователям использовать прямую маршрутизацию, выполните указанные ниже действия. 

- **Шаг 1.** [Соединение SBC с телефонной системой Microsoft и проверка соединения](direct-routing-connect-the-sbc.md)
- **Шаг 2.** [Предоставление пользователям прямой маршрутизации, голоса и голосовой почты](direct-routing-enable-users.md)
- **Шаг 3.** [Настройка голосовой маршрутизации](direct-routing-voice-routing.md)
- **Шаг 4.** [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Если вы настраиваете SBC для нескольких клиентов, вы также захотите прочитать [настройку SBC для нескольких клиентов](direct-routing-sbc-multiple-tenants.md).


## <a name="see-also"></a>См. также

[Прямая маршрутизация телефонной системы](direct-routing-landing-page.md)

[Планирование прямой маршрутизации](direct-routing-plan.md)

