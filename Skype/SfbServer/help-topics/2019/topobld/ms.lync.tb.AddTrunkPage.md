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
ms.openlocfilehash: db98c6d6f6aacf31b4e0b228dbe499f40ea01bdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800899"
---
# <a name="define-a-new-trunk"></a>Определение новой линии связи

Вы можете определить новый канал связи по протоколу SIP, указав следующие сведения.

- **Имя канала связи**. Уникальное имя в топологии, используемое для идентификации данного канала связи.

- **Связанный шлюз ТСОП**. Выберите развернутый и настроенный шлюз ТСОП в списке.

- **Порт прослушивания для шлюза IP/ТСОП**. Порт, который будет прослушиваться шлюзом IP-УАТС или ТСОП. Должен отличаться от всех остальных портов прослушивания каналов связи, настроенных в данном развертывании.

- **Транспортный протокол SIP**. Выберите в списке TCP или TLS.

- **Связанный сервер-посредник**: выберите в списке сервер-посредник, развернутый и настроенный в развертывании

- **Связанный порт сервера-посредника:** установите значение порта, равное порту TCP или TLS сервера-посредника, который будет использовать эта магистраль SIP

## <a name="see-also"></a>См. также

[Магистраль M:N в Skype для бизнеса Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Как реализовать магистрали SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
