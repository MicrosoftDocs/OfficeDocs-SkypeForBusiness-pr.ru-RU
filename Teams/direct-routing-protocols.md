---
title: Прямая маршрутизация телефонной системы
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
description: Протоколы прямой маршрутии
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835029"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Прямая маршрутия : определения и стандарты RFC

В этой статье описывается, как microsoft Phone System Direct Routing реализует стандартные протоколы RFC. Эта статья предназначена для голосовых администраторов, отвечающих за настройку подключения между локальной службой граничного контроллера сеанса (SBC) и прокси-службой SIP.

Клиентский интерфейс SBC со следующими компонентами в microsoft Teams backend: 

- **Прокси-сервер SIP** для сигнального сигнала. Это интернет-компонент прямой маршрутики, который обрабатывает подключения SIP (TLS) между SBCs и Direct Routing.

- **Процессоры мультимедиа для** мультимедиа. Это интернет-компонент прямой маршрутки, обрабатывающий трафик мультимедиа. Этот компонент использует протоколы SRTP и SRTCP.


Дополнительные сведения о прямой маршрутике см. в прямой [маршрутинге телефонной системы.](direct-routing-landing-page.md)

Дополнительные сведения о внедрении протокола SIP Direct Routing см. в протоколе [SIP Direct Routing.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Стандарты RFC

Прямая маршрутная маршрутия соответствует стандартам RFC.  SBC, подключенный к direct Routing, также должен соответствовать следующим запросам (или их последователям). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Стандарты, применимые к устройствам, которые поддерживают режим обхода мультимедиа 

Следующие стандарты применимы к устройствам, которые поддерживают только режим обхода мультимедиа:

- [SIP RFC 3261:](https://tools.ietf.org/html/rfc3261)протокол session Initiation Protocol
- [RFC 3325.](https://www.ietf.org/rfc/rfc3325) Частное расширение к протоколу session Initiation Protocol для утверждения удостоверений в надежных сетях— разделы об обработке заглавного раздела "P-Кутюро-удостоверение". Direct Routing отправляет P-Заявка с заглавными идентификаторами конфиденциальности. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Расширение протокола SIP для необходимых сведений об истории. Дополнительные сведения см. в описании протокола SIP маршрутинга.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Механизм управления протоколом Referred-By сеансов
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Замещает заглавный протокол (SIP) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Использование модели предложений и ответов протоколом SIP.
  См. раздел "Отклонения от RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) и [RFC 4771.](https://tools.ietf.org/html/rfc4771) Защитите трафик RTP с помощью SRTP. У SBC должна быть возможность установить ключи с помощью SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Уточнения предложений и ответов по RTP/RTCP-протоколу (SDP)

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Стандарты, применимые к устройствам, поддерживаютам режима обхода мультимедиа

Помимо стандартов, которые перечислены в режиме обхода мультимедиа, используются следующие стандарты:

- [Установка интерактивных подключений RFC 5245 (ICE) для обхода мультимедиа.](https://tools.ietf.org/html/rfc5245)  SBC должен поддерживать следующие:
  - ICE Lite — клиенты Teams являются полными клиентами ICE
  - [Перезапуски ICE.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) Дополнительные статью о перезапусках ICE с использованием case и примеры при перезапуске ICE: звонок "Обход мультимедиа" передается на конечную точку, которая не поддерживает обход мультимедиа   
- [Управление звонками SIP через RFC RFC 5589— передача.](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [Утилиты RFC 5389 Session Traversal Utilities для NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Стандарты, применимые к поддержке передачи сведений о расположении поставщикам E911

- [RFC 6442, расположение для протокола session Initiation Protocol](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Отклонения от RFC

В следующей таблице перечислены разделы RFC, в которых внедрение SIP или стека мультимедиа корпорацией Майкрософт отклоняется от стандартного:

| RFC и разделы | Описание | Отклонение |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, раздел 5.3 Удержания и резюме мультимедиа](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC позволяет использовать "a=inactive", "a=sendonly", a=rec управляемый" для удержания звонка. |Прокси-сервер SIP поддерживает только "a=inactive" и не понимает, отправляется ли SBC "a=sendonly" или "a=rec устои".
| [RFC 6337, раздел 5.4 "Поведение при получении SDP с c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [Для RFC3264](https://tools.ietf.org/html/rfc3264) требуется, чтобы агент мог получать SDP с адресом подключения 0.0.0.0. В этом случае ни RTP, ни RTCP не должны быть отправлены на одноранговую связь. | Прокси-сервер SIP не поддерживает этот параметр. |

## <a name="operational-modes"></a>Рабочие режимы

Существует два рабочих режима прямой маршрутации:

- **Без обхода мультимедиа,** при котором весь трафик RTP передается между клиентом Teams, процессорами мультимедиа и SBC.  

- **С обходом мультимедиа,** при котором все потоки мультимедиа RTP между конечными точками Teams и SBC. 

Обратите внимание, что трафик SIP всегда проходит через прокси-сервер SIP.   
