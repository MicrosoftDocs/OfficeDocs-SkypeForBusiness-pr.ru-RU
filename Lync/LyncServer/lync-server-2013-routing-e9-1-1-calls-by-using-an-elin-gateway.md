---
title: 'Lync Server 2013: маршрутизация звонков E9-1-1 с использованием шлюза ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Маршрутизация звонков E9-1-1 с использованием шлюза ELIN в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-05_

Некоторые партнеры по программе открытого взаимодействия для объединенных коммуникаций Майкрософт предоставляют шлюзы, поддерживающие номера ELIN, которые могут служить альтернативой магистральной линии SIP до поставщика услуг E9-1-1. Шлюзы ELIN поддерживают подключения ISDN и CAMA к службам E9-1-1 в ТСОП. Подробные сведения о партнерах, которые предоставляют Елин шлюзы и ссылки на документацию [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425), можно найти в разделе.

Как и подключения по магистралям SIP к поставщикам услуг E9-1-1, шлюзы ELIN также предоставляют способы маршрутизации экстренных вызовов в приемлемый для вызывающего абонента пункт реагирования общественной безопасности, однако эти шлюзы используют ELIN в качестве идентификатора расположения. Вы определяете Елинс для каждого местоположения реагирования на чрезвычайные ситуации (ЕРЛ) в вашей организации (подробные сведения можно найти в разделе [Управление расположениями Елин шлюзов в Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

При использовании шлюза Елин для экстренных вызовов используется та же инфраструктура Lync Server E9-1-1, которую можно использовать для подключения к магистральной магистрали SIP. Это значит, что база данных службы сведений о расположении предоставляет расположение для клиента Lync Server, а политика расположения включает функцию и определяет маршрутизацию. Тем не менее, с шлюзом Елин необходимо добавить Елинс в базу данных службы сведений о расположении и получить их в базу данных автоматического определения расположения (ALI).

Когда клиент Lync получает свое расположение из службы сведений о расположении, это расположение включает Елин. During an emergency call, the ELIN is included with the location sent to the ELIN gateway. The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN. The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number. The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database. The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup. The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks. During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.

Шлюзы ELIN поддерживают экстренные вызовы только из сети организации. Если экстренный вызов выполнен из-за пределов сети, шлюз его не поддерживает.

<div>


> [!NOTE]  
> Подробнее об использовании магистрального подключения SIP для вызова экстренной помощи можно найти <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">в разделе Маршрутизация E9-1-1 звонков с помощью магистральной МАГИСТРАЛИ SIP в Lync Server 2013</A>.



</div>

На приведенной ниже схеме показано, как с Lync Server перенаправляется вызов экстренной помощи в ПСАП при использовании шлюза Елин.

**Маршрутизация вызовов E9-1-1 с помощью шлюза ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  ПРИГЛАШЕНИЕ на SIP, содержащее расположение, номер обратного вызова вызывающего абонента и (необязательно) URL-адрес уведомления и номер обратного вызова конференции пересылается на Lync Server.

2.  Lync Server соответствует номеру для экстренного реагирования и перенаправляет звонок (на основе значения **использования PSTN** , определенного в соответствующей политике расположения) на сервер-посредник и из него на шлюзе Елин.

3.  Шлюз ELIN маршрутизирует вызов через магистраль ISDN или CAMA в ТСОП.

4.  ТСОП определяет вызов как экстренный и маршрутизирует его на селекторный маршрутизатор E9-1-1 в своей сети. Селекторный маршрутизатор E9-1-1 проверяет номер вызывающего абонента по базе данных ALI для получения географического расположения. Селекторный маршрутизатор E9-1-1 отправляет вызов на подходящий пункт реагирования на основе сведений о расположении, полученных из базы данных ALI. 

5.  Если вы настроили политику расположения для уведомлений, то один или несколько руководителей Организации отправили мгновенное сообщение Lync с помощью специального уведомления. Это сообщение всегда появляется на экране руководителей системы безопасности и включает имя вызывающего абонента, номер телефона, время и место, позволяя персоналу безопасности быстро реагировать на него с помощью мгновенного сообщения или голосового звонка.

6.  Если вызов прерывается раньше времени, пункт реагирования использует номер ELIN для прямой связи с вызывавшим абонентом. Шлюз ELIN заменяет номер ELIN на прямой входной номер абонента.

</div>

<span> </span>

</div>

</div>

</div>

