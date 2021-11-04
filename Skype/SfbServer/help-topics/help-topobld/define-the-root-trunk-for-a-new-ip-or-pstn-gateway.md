---
title: Определение корневой магистральной линии для нового шлюза IP или ТСОП
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: 'Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:'
ms.openlocfilehash: 0f96574ea65fc3b7d1419deabea4cb33192500df
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747649"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a>Определение корневой магистральной линии для нового шлюза IP или ТСОП

Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:

- **Имя линии связи** — определяет полное доменное имя, связанное с магистралью;

- **Порт прослушивания для IP-адреса/шлюза ТСОП** — определяет порт, по которому выполняется прослушивание для данной магистрали

- **Транспортный протокол SIP** — выберите в списке **TCP** или **TLS** в зависимости от потребностей магистрали

- **Связанный сервер-посредник:** выберите из списка доступных серверов-посредников в развертывании

- **Связанный порт сервера-посредника:** определите порт, на который прослушивается выбранный сервер-посредник

## <a name="see-also"></a>См. также

[Настройка магистрали с обходом мультимедиа в Skype для бизнеса Server 2015 г.](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[Настройка магистрали без обхода мультимедиа в Skype для бизнеса Server 2015 г.](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[Поддержка распределения каналов SIP](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)