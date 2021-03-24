---
title: Определение новой линии связи
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: Вы можете определить новый канал связи по протоколу SIP, указав следующие сведения.
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093277"
---
# <a name="define-a-new-trunk"></a>Определение новой линии связи

Вы можете определить новый канал связи по протоколу SIP, указав следующие сведения.

- **Имя канала связи**. Уникальное имя в топологии, используемое для идентификации данного канала связи.

- **Связанный шлюз ТСОП**. Выберите развернутый и настроенный шлюз ТСОП в списке.

- **Порт прослушивания для шлюза IP/ТСОП**. Порт, который будет прослушиваться шлюзом IP-УАТС или ТСОП. Должен отличаться от всех остальных портов прослушивания каналов связи, настроенных в данном развертывании.

- **Транспортный протокол SIP**. Выберите в списке TCP или TLS.

- **Связанный сервер-посредник:** выберите из списка сервер-посредник, развернутый и настроенный в развертывании.

- **Связанный порт** сервера-посредника: установите значение порта, равное значению порта TCP или TLS сервера-посредника, которое будет использовать этот магистраль SIP

## <a name="see-also"></a>См. также

[Магистраль M:N в Skype для бизнеса Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Как реализовать магистральные SIP?.](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)