---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
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
description: Узнайте, как настроить обход мультимедиа с помощью прямой маршрутии телефонной системы для Microsoft Teams, выключив всех пользователей одновременно или реализуя поэтапный подход (рекомендуется).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416899"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Настройка обхода сервера-посредника с прямой маршрутизацией

Перед настройкой обхода мультимедиа с помощью прямой маршрутирования убедитесь, что вы прочитали "План обхода мультимедиа" [при прямой маршрутии.](direct-routing-plan-media-bypass.md)

Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:

1.    Убедитесь, что поставщик граничного контроллера сеанса (SBC) поддерживает обход мультимедиа и предоставляет инструкции по настройке обхода в SBC. На странице сертификации вы узнаете о SBCs, которые поддерживают обход мультимедиа, и инструкции.

2.    Необходимо включить обход мультимедиа на линии с помощью следующей команды: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Откройте необходимые порты. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Переход с неисключаемой магистрали на обойденные

Вы можете переключить всех пользователей одновременно или внедрить поэтапный подход (рекомендуется).

- **Одновременное переключение всех пользователей.** Если все условия выполнены, можно включить режим обхода. Однако все производственные пользователи будут одновременно переключения. Поскольку первоначально при настройке магистральных и портов могут возникнуть некоторые проблемы, это может повлиять на пользовательский процесс в вашей компании. 

- **Поэтапный подход. (Рекомендуется).**  Создайте новую магистраль для того же SBC (с другим портом), протестйте ее и измените политику маршрутинга голосовой связи, чтобы пользователи навести указатель на новую. 

  Это рекомендуемый подход, так как он обеспечивает более плавный переход и непрерывный пользовательский интерфейс. Для этого подхода требуется конфигурация SBC, новое имя FQDN и конфигурация брандмауэра. Обратите внимание, что ваш сертификат должен поддерживать обе службы. В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com)** или поддиавный сертификат.

![Переход с неисключаемой магистрали на обойденные](media/direct-routing-media-bypass-8.png)

Инструкции по настройке и переносу см. в документации поставщика SBC:

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию информационного сообщения на ленте](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Список граничных геймпадов сеансов, сертифицированных для прямой маршрутики, см. в списке контроллеров [Broder Session Broder,](direct-routing-border-controllers.md)сертифицированных для прямой маршрутики.



## <a name="related-topics"></a>Статьи по теме

[Обход мультимедиа с прямой маршрутией](direct-routing-plan-media-bypass.md)



