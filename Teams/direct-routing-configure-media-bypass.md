---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить обход мультимедиа с помощью телефонная система прямой маршрутии для Microsoft Teams путем одновременного переключения всех пользователей или поэтапной реализации (рекомендуется).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0f0ad9d25157058c048b0f12cf72b3755e65e11
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728688"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Настройка обхода сервера-посредника с прямой маршрутизацией

Перед настройкой обхода мультимедиа при прямой маршрутике убедитесь, что у вас есть прочитать статью Планирование обхода мультимедиа [с прямой маршрутией.](direct-routing-plan-media-bypass.md)

Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:

1.    Убедитесь, что поставщик SBC поддерживает обход мультимедиа и предоставляет инструкции по настройке обхода на SBC. На странице сертификации вы узнаете, какие из них поддерживают обход мультимедиа, и инструкции.

2.    Чтобы включить обход мультимедиа на линии, следуйте следующей команде: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Убедитесь, что открыты необходимые порты. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Переход с невключаемой туловища на обойденные.

Вы можете переключить всех пользователей одновременно или реализовать поэтапный подход (рекомендуется).

- **Одновременное переключение всех пользователей.** Если выполнены все условия, вы можете включить режим обхода. Однако все ваши пользователи будут переключаться одновременно. Так как первоначально при настройке связи и портов могут возникнуть некоторые проблемы, это может повлиять на пользовательский интерфейс вашей компании. 

- **Поэтапный подход. (Рекомендуется)**.  Создайте новую магистраль для того же SBC (с другим портом), протестировать ее и измените политику маршрутинга голосовой связи в Интернете, чтобы пользователи навести указатель на новую туловище. 

  Это рекомендуемый подход, так как он обеспечивает более плавный переход и непрерывный пользовательский интерфейс. Для этого подхода требуется конфигурация SBC, новое имя FQDN и конфигурация брандмауэра. Обратите внимание, что сертификат должен поддерживать обе стороны. В САН у вас должны быть два имени **(sbc1.contoso.com** **и sbc2.contoso.com**) или поддиск.

![Переход с неинтегрирования на обойденные магистрали.](media/direct-routing-media-bypass-8.png)

Инструкции по настройке магистральных телефонов и выполнению миграции см. в документации поставщика SBC:

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию коммуникаций на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Список контроллеров границ сеанса( SBCs), сертифицированных для прямой маршрутики, см. в списке контроллеров", сертифицированных для прямой [маршрутики.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Статьи по теме

[Планирование обхода мультимедиа с помощью прямой маршрутии](direct-routing-plan-media-bypass.md)



