---
title: 'Teams прямой маршрутии телефонной системы: определения и стандарты RFC'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Как Телефон (Майкрософт) System Direct Routing реализует стандартные протоколы RFC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26178fa52105f43ce9f7f18c0058a2ead3ef1c02
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235344"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Прямая маршрутия — определения и стандарты RFC

В этой статье описано Телефон (Майкрософт) как в системе Direct Routing реализованы стандартные протоколы RFC. Эта статья предназначена для администраторов голосовой связи, которые отвечают за настройку подключения между локальной службой пограничного контроллера сеанса (SBC) и прокси-службой SIP.

Интерфейс sBC клиента со следующими компонентами в Microsoft Teams интерфейса: 

- **Прокси-сервер SIP** для сигнального сигнала. Это интернет-компонент прямой маршрутики, обрабатывающий подключения SIP (TLS) между SBCs и Direct Routing.

- **Процессоры мультимедиа** для мультимедиа. Это интернет-компонент прямой маршрутии, обрабатывающий трафик мультимедиа. Этот компонент использует протоколы SRTP и SRTCP.


Дополнительные сведения о прямой маршрутике см. в телефонная система [Прямой маршрут.](direct-routing-landing-page.md)

Дополнительные сведения о внедрении протокола SIP direct Routing см. в этой [ссылке.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Стандарты RFC

Прямая маршрутная маршрутия соответствует стандартам RFC.  SBC, подключенный к прямой маршрутике, также должен соответствовать следующим запросам (или их последователям). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Стандарты, применимые к устройствам, поддерживаюным режим обхода мультимедиа 

Следующие стандарты применимы к устройствам, которые поддерживают только режим обхода мультимедиа:

- [SIP RFC 3261:](https://tools.ietf.org/html/rfc3261)протокол session initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Частное расширение протокола инициирования сеанса для утверждения удостоверений в доверенных сетях— разделы об обработке заглавного заглавного раздела P-Утвердилось-identity. Прямая маршрутная маршрутия отправляет P-Изядле-удостоверение с заглавными идентификаторами конфиденциальности. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Расширение протокола SIP для необходимых сведений об истории. Дополнительные сведения см. в описании протокола SIP.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Механизм управления протоколом Referred-By сеанса
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Заглавный заглавный протокол SIP заменяет 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Использование модели предложений и ответов протоколом SIP.
  См. раздел "Отклонения от RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) и [RFC 4771](https://tools.ietf.org/html/rfc4771). Защитите трафик RTP с помощью SRTP. SBC должен иметь возможность устанавливать ключи с помощью SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Уточнения предложений и ответов по протоколу SDP для многократного сеанса RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Стандарты, применимые к устройствам, поддерживаюным режим обхода мультимедиа

В дополнение к стандартам, которые перечислены как применимые к режиму обхода, для режима обхода мультимедиа используются следующие стандарты:

- [RFC 5245 Interactive Connectivity Connectivity Ветвь (ICE) для обхода мультимедиа](https://tools.ietf.org/html/rfc5245).  SBC должен поддерживать следующие следующую поддержку:
  - ICE Lite — клиенты Teams являются полными клиентами ICE
  - [Ice Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Дополнительные статью об использовании допусков ICE с использованием досье и примеры см. в статьи Перезапуск ICE: звонок об обходе мультимедиа перенесен на конечную точку, которая не поддерживает обход мультимедиа   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), см. разделы 3.1, Forking и 3.2, "Генерация сигнала звонка" 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Стандарты, применимые к поддержке передачи сведений о расположении поставщикам E911

- [RFC 6442, передает расположение для протокола session initiation Protocol](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Отклонения от RFC

В следующей таблице перечислены разделы RFC, в которых внедрение SIP или стека мультимедиа отклоняется от стандарта:

| RFC и разделы | Описание | Отклонение |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, раздел 5.3 Удержание и возобновление работы мультимедиа](https://tools.ietf.org/html/rfc6337#section-5.3) | С помощью RFC можно использовать "a=inactive", "a=sendonly", a=reclyly" для удержания звонка. |Прокси-сервер SIP поддерживает только "a=inactive" и не понимает, отправляет ли SBC "a=sendonly" или "a=reclyly".
| [RFC 6337, раздел 5.4 "Поведение при получении SDP с c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [Для RFC3264](https://tools.ietf.org/html/rfc3264) требуется, чтобы агент мог принимать SDP с адресом подключения 0.0.0.0. В этом случае ни RTP, ни RTCP не должны быть отправлены на одноранговую связь. | Прокси-сервер SIP не поддерживает этот параметр. |

## <a name="operational-modes"></a>Рабочие режимы

Существует два режима прямой маршрутации:

- **Без обхода мультимедиа,** при котором весь трафик RTP Teams клиент, процессоры мультимедиа и SBC.  

- **С обходом мультимедиа,** при котором все потоки мультимедиа RTP Teams конечными точками и SBC. 

Обратите внимание, что трафик SIP всегда проходит через прокси-сервер SIP. 

## <a name="dtmf"></a>Dtmf
In-band DTMF is not supported by media stack.
