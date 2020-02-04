---
title: Определение новой линии связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:'
ms.openlocfilehash: 9de4808bc7a53aae79c2373116e74be98c7ae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684842"
---
# <a name="define-a-new-trunk"></a>Определение новой линии связи

Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:

- **Имя канала**связи: уникальное имя в топологии, которое будет определять эту магистраль.

- **Связанный шлюз PSTN**: Выберите развернутый и сконфигурированный шлюз PSTN в развертывании из списка.

- **Порт для прослушивания шлюза IP/КТСОП**: порт, прослушиваемый IP-УАТС или PSTN-шлюзом. Должны быть уникальными на всех остальных портах, настроенных в развертывании

- **Транспортный протокол SIP**: выберите из списка один из протоколов TCP или TLS.

- **Сервер связанных исправлений**: выберите из списка сервер-посредник, развернутый и настроенный в развертывании

- **Порт сервера связанных исправлений**: установите для порта значение, равное значению порта TCP или TLS сервера, который будет использоваться этой магистральной службой SIP.

## <a name="see-also"></a>См. также

[Магистраль M:N в Skype для бизнеса Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Как реализовать магистральные линии SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
