---
title: 'Lync Server 2013: обзор E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Обзор E9-1-1 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-29_

Microsoft Lync Server 2013 поддерживает вызов улучшенных 9-1-1 (E9-1-1) на клиентах Lync и устройствах Lync Phone Edition. Когда вы настраиваете Lync Server для E9-1-1, экстренные вызовы, размещенные в Lync 2013 или Lync Phone Edition, включают в себя сведения о местоположении ответа на аварийную информацию (ЕРЛ) из базы данных службы расположения. ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities. Когда пользователь осуществляет вызов экстренной помощи, Lync Server перенаправляет звук звонка, а также сведения о местоположении и ответном вызове, используя сервер-посредника для поставщика услуг E9 – 1-1. The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.

Lync Server поддерживает два способа маршрутизации экстренных вызовов в поставщик услуг E9-1-1:

  - Подключение через магистраль SIP к уполномоченному поставщику услуг E9-1-1

  - Шлюз ELIN к поставщику услуг E9-1-1 на основе ТСОП

При использовании провайдера услуг магистральной магистрали по протоколу SIP E9-1-1 необходимо добавить Ерлс в базу данных службы сведений о расположении, а затем проверить расположение в соответствии с основным адресом (МСАГ), поддерживаемым поставщиком услуг E9-1-1. If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP. (Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)

В отличие от мультиплексирования деления времени (ТДМ) и VPN-телефонов, использующих ПРОТОКОЛы АТС с фиксированными расположениями, конечная точка Lync может быть на мобильном устройстве. Когда вы развертываете функцию E9-1-1, Lync Server помогает убедиться в том, что в какой-то момент, если вызывающий объект находится в сети, вызов экстренной помощи может перенаправляться в ПСАП, который обслуживает расположение вызывающего абонента. Например, если главный офис пользователя расположен в городе Рэдмонд штата Вашингтон, но пользователь совершает звонок в экстренную службу с компьютера филиала, расположенного в городе Уичито штата Канзас, то поставщик услуг E9-1-1 на основе магистрали SIP или ТСОП перенаправит звонок в пункт реагирования общественной безопасности города Уичито, а не Рэдмонда.

При использовании шлюза Елин вы также добавляете Ерлс в базу данных службы сведений о расположении, но вы также включаете номер Елин для каждого места. The ELIN number becomes the emergency calling number during the emergency call. You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.

<div>


> [!NOTE]  
> Устройства, подключенные к Lync, не могут получать сведения о расположении из службы сведений о расположении или передавать расположение поставщику услуг E9-1-1. If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options: 
> <UL>
> <LI>
> <P><STRONG>Традиционный</STRONG>&nbsp;&nbsp;способ&nbsp;PS-Ali. Если у вас есть местные шлюзы PSTN на каждом сайте, на котором развернуты аналоговые телефоны, и каждый из аналоговых телефонов сделал это, вы можете подготовить расположение аналогового устройства непосредственно с помощью закрытого коммутатора/автоматического определения расположения (PS-Ali) поставщика услуг. В этом случае вы настраиваете специально сконструированные политики голосовой связи Lync и назначаете их контактам из аналоговых объектов устройства, так что звонки E9-1-1 с этих телефонов перенаправляются напрямую по локальному шлюзу поставщику PSTN, который будет выполнять обслуживание сайта (вместо маршрутизации Звонок на телефонную магистраль поставщика услуг E9-1-1. При размещении вызова экстренной службы номер каждого аналогового телефона для прямого соединения с внутренними абонентами сопоставляется с физическим местоположением по базе данных, расположенной у поставщика PS-ALI и связанной с магистралью ТСОП, после чего информация об этом местоположении передается в пункт реагирования общественной безопасности. Эти записи должны обновляться у поставщика услуг PS-ALI при каждом перемещении телефонов в другие местоположения.</P>
> <LI>
> <P><STRONG>E9-1-1 (поставщик услуг)</STRONG>&nbsp;&nbsp;&nbsp;. Вы можете зарегистрировать аналоговые телефонные Дидс и соответствующие им Ерлс с помощью провайдера услуг E9-1-1, если он поддерживается поставщиком услуг E9-1-1. Если поставщик получает вызов с сервера Lync Server, который не содержит ПИДФ данных, поставщик может узнать, совпадает ли соответствие с базой данных на номере вызывающей стороны. С помощью сведений о местоположении чрезвычайной ситуации, полученных из своей базы данных, поставщик может автоматически маршрутизировать экстренный вызов в соответствующий пункт реагирования общественной безопасности, который в свою очередь получит номер для прямого соединения с внутренними абонентами аналогового устройства и запись ESQK, позволяющие диспетчеру найти местоположение звонящего.</P></LI></UL>Если используется вариант со шлюзом ELIN и требуется поддержка E9-1-1 с аналоговых телефонов, администратор может предоставить сведений об аналоговых устройствах напрямую с помощью поставщика PS-ALI, как описано выше в первом варианте.</div>

С точки зрения сервера Lync процесс E9-1-1 можно разделить на два этапа:

  - Этап 1: получение сведений о местоположении

  - Этап 2: маршрутизация экстренного вызова поставщику услуг E9-1-1

В данном разделе описано, как работают эти этапы.

Если планируется настроить инфраструктуру для автоматического обнаружения местоположения клиента, сначала необходимо решить, какие элементы сети будут использоваться для сопоставления расположений абонентов. Подробнее об этих параметрах можно узнать [в разделе Определение сетевых элементов, используемых для определения расположения в Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Содержание

  - [Получение сведений о местоположении в Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Маршрутизация звонков E9-1-1 с использованием магистралей SIP в Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Маршрутизация звонков E9-1-1 с использованием шлюза ELIN в Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

