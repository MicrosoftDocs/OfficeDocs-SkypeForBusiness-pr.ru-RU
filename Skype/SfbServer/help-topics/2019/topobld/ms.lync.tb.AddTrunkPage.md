---
title: Определение новой линии связи
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Определите новый сеанс initiation protocol (SIP) магистрали содержат следующие сведения:'
ms.openlocfilehash: eba7dec862cf359a8670bcfbf7f0b475575a26ec
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895932"
---
# <a name="define-a-new-trunk"></a>Определение новой линии связи

Определите новый сеанс initiation protocol (SIP) магистрали содержат следующие сведения:

- **Имя линии связи**: уникальным именем в топологии, идентифицирующее этот магистрали

- **Связанный шлюз ТСОП**: выберите развертывания и настройки шлюза ТСОП в вашем развертывании из списка

- **Порт прослушивания для шлюза IP/ТСОП**: порт, который прослушивает шлюз ТСОП или IP-УАТС. Должно отличаться от всех других магистрали портов, прослушиваемых настроенных в развертывании

- **Транспортный протокол SIP**: выберите в списке TCP или TLS

- **Связанный сервер-посредник**: выберите из списка, который будет развернута и настроена в развертывании сервера-посредника

- **Порт связанного сервера-посредника**: укажите номер порта TCP или TLS значение порта сервера-посредника, которую будет использовать этот канала SIP.

## <a name="see-also"></a>См. также

[Магистраль m: n в Скайп для Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Как реализовать распределения каналов SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
