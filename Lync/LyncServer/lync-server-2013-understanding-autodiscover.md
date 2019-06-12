---
title: 'Lync Server 2013: Общие сведения о автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8a4965674952cfa5822c24e887ed4d5a02b798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Общие сведения о автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-06-03_

Служба автообнаружения Lync Server 2013 — это функция, которая первоначально появилась в Microsoft Lync Server 2010 в рамках накопительного обновления для Lync Server 2010: Ноябрь 2011 г. Помимо исправлений, это накопительное обновление доставлено поддержку клиентам Lync Mobile и Lync 2013.

В Lync Server 2013 служба автообнаружения является неотъемлемой частью функционирования внешних и внутренних мобильных клиентов, а также расширяет возможности автообнаружения для новых клиентов, например недавно появившегося приложения Lync из Магазина Windows для Windows 8. Автообнаружение также используется клиентами Lync 2013 для настольных компьютеров. Служба автообнаружения распознается в Lync Server требуемыми записями DNS (Domain Name System) **lyncdiscover.\< Domain\> ** и **линкдисковеринтернал.\< Domain\>(домен**). Кроме того, более новые версии Lync 2010 и Lync 2013 для настольных компьютеров предпочитают автообнаружения на SRV-записях DNS (Domain Name System), используя DNS SRV-записи только в том случае, если lyncdiscover. \<Domain\> (домен) или линкдисковеринтернал. \<домен\> не отвечает на запросы и не разрешается. Приложение Lync из Магазина Windows для Windows 8 и Lync Mobile использует функцию автообнаружения исключительно и не будет ссылаться на традиционные DNS SRV-записи.

В Lync Server 2013 функция автообнаружения расширяется для связи с клиентом, какие элементы, функции и методы связи доступны для клиента. Информация передается через запрос, отправленный клиентом, и веб-службы Lync Server отвечают на явно определенный ответ, который называет сведения о доступности клиента, и о том, как обращаться к этим функциям в формате автообнаружения. Документ ответа.

Лучший способ понять документ ответа автообнаружения, в том числе о том, как веб-службы обмениваются функциями с клиентами через этот документ, — это диссект и определять каждую строку в типичном ответе от документа ответа автообнаружения веб-службы Lync.

<div class="">


> [!NOTE]  
> В приведенных ниже сведениях пользователь уже прошел проверку подлинности на основном сервере, отвечая на запрос проверки подлинности.



</div>

<div class="">


> [!NOTE]  
> Веб-служба автообнаружения Lync определена в <STRONG>протоколах Microsoft Office</STRONG> в разделе " <STRONG>открытые спецификации</STRONG> " библиотеки <STRONG>Microsoft Developer Network</STRONG> (MSDN). Подробнее смотрите документ полную спецификацию "протокол веб-службы автообнаружения Lync" по адресу: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>. Подробные сведения о проверке подлинности можно найти в <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>разделе "протокол веб-службы проверки подлинности OC".



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Ответ автообнаружения веб-службы Lync Server

Ответ, возвращенный при отправке запроса автообнаружения, одинаков для внутреннего или внешнего клиента. Некоторые параметры, которые являются положениями, могут меняться. Если запрос на получение клиента получен, но реальный пул отличается от того, с которым был установлен связь, для этого пользователя будет задан главный пул пользователей. Коллега с учетной записью пользователя в другом пуле, но вход из него может слегка отличаться от того, который входит в состав одного и того же офиса. Ответ указывает на правильный сервер переднего плана или пул переднего плана для этого пользователя.

Пример документа ответа автообнаружения:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>Сведения о документе для ответа автообнаружения

Документ ответа автообнаружения может иметь один из двух форматов. Формат по умолчанию — нотация объекта JavaScript (JSON). Другой формат — документ в формате Extensible Markup Language (XML). В этом примере используется XML. Запрос и ответ предсказуемы, так как в документе определена схема, определяющая формат. Строка в документе, описывающая используемую схему, является первой строкой запроса или ответа.

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Определение **акцесслокатион = "External"** указывает на то, что запрос выполнен от внешнего пользователя.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Сипсерверинтерналакцесс и Сипсерверекстерналакцесс в настоящее время не используются. Эти записи зарезервированы для использования в будущем.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

Сипклиентинтерналакцесс и Сипклиентекстерналакцесс описывают полные доменные имена и порты, которые будет использовать внутренний или внешний клиент для доступа к определенному серверу SIP. Клиент Lync для настольных компьютеров и приложение Lync из Магазина Windows используют эти записи, основываясь на их расположении (внутреннем или внешнем), чтобы найти сервер директоров или интерфейсов.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover` Ссылки содержат точки входа в службу автообнаружения. Атрибут Token содержит имя службы, а href — URL-адрес, который определяет клиента, на котором может быть найдена служба. Клиенты во внешней сети используют `External/Autodiscover`. Служба автообнаружения устанавливается как часть процесса развертывания. `Internal/Autodiscover`в настоящее время не используется и зарезервирован для будущего использования.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker` Ссылки содержат точки входа службы для внутренней и внешней службы посредника проверки подлинности, в данном случае SIP. svc. Атрибут Token содержит имя службы, а href — URL-адрес, который определяет клиента, на котором может быть найдена служба. Клиенты во внутренней сети с использованием `Internal/AuthBroker`. Клиенты во внешней сети используют `External/AuthBroker`. Служба Аусброкер устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Этот `WebScheduler` маркер ссылается на URL-адреса для доступа клиента к Интернет-календарному планированию для конференций на Lync Server. В настоящее время используется `External/WebScheduler` только элемент. Служба веб-планировщика устанавливается как часть процесса развертывания внутренней версии сервера Lync Server 2013 для развертывания.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`и `External/Mcx` находятся расположения служб Mobility Service, представленные в накопительном обновлении для Lync Server 2010: Ноябрь 2011. Эти ссылки будут продолжать использоваться в Lync 2010 Mobile на всех поддерживаемых устройствах. Служба МККС устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

ФУНКЦИИ **internal/Уква**, **External/Уква** и **Уква** предоставляют клиентам доступ к интерфейсу прикладного программирования (API для Уква или просто Уква) для веб-приложений единой системы обмена сообщениями. `Internal/Ucwa``External/Ucwa` виртуальные каталоги — это точки доступа, которые зарезервированы для будущего улучшения функций и не используются. `Ucwa` Виртуальный каталог используется для Microsoft Lync Mobile (представленный в lync Server 2013) на всех поддерживаемых устройствах. Служба УКВА устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/ксфраме** и **ксфраме** предоставляют доступ к серверным приложениям на базе Уква. Ксфраме устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self` Маркер ссылается на сведения, специфичные для клиента (тип ответа пользователя), который создает запрос. Клиент, который сделал этот запрос внешним, и этот указатель автообнаружения относится к пользовательской части службы автообнаружения.

</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Системные требования для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Планирование автообнаружения в Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

