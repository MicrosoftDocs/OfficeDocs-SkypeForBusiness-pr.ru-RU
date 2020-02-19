---
title: 'Lync Server 2013: Общие сведения о службе автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 033f3a12ccbe0817f586aa7eb868679fa44541fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Общие сведения о службе автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-06-03_

Служба автообнаружения Lync Server 2013 — это функция, изначально появившаяся в Microsoft Lync Server 2010 в составе накопительного пакета обновления для Lync Server 2010: Ноябрь 2011 г. В дополнение к исправлениям это накопительное обновление доставляет поддержку для клиентов Lync Mobile и Lync 2013.

В Lync Server 2013 служба автообнаружения является неотъемлемой частью работы внешних и внутренних мобильных клиентов, а автообнаружение также расширено до новых клиентов, например недавно появившегося приложения Lync Windows Store для Windows 8. Автообнаружение также используется клиентами Lync 2013 для настольных ПК. Служба автообнаружения в Lync Server распознается требуемыми записями DNS (Domain Name System) **lyncdiscover.\< Domain\> ** и **lyncdiscoverinternal.\< Domain\>(домен**). Кроме того, в новых версиях Lync 2010 и Lync 2013 для настольных компьютеров предпочтительнее выполнять обнаружение через записи DNS SRV, используя DNS SRV-записи только в том случае, если lyncdiscover. \<Domain\> или lyncdiscoverinternal. \<домен\> не отвечает или не обрабатывается. Приложение Lync в магазине Windows для Windows 8 и Lync Mobile использует только службу автообнаружения и не будет ссылаться на традиционные DNS SRV-записи.

В Lync Server 2013 служба автообнаружения расширяется для связи с клиентом, какие элементы, функции и методы связи доступны клиенту. Информация передается через запрос, отправляемый клиентом, а веб-службы Lync Server — в ответ с четким определенным ответом, который называет доступ к клиенту и как обращаться к этим функциям в формате автообнаружения. Документ ответа.

Лучший способ получить представление о документе ответа автообнаружения, в том числе о том, как веб-службы обмениваются функциями с помощью этого документа, — это диссект и определять каждую строку в типичном ответе из документа ответа на автообнаружение веб-службы Lync.

<div class="">


> [!NOTE]  
> В приведенных ниже сведениях пользователь уже прошел проверку подлинности на основном сервере, отвечая на запрос проверки подлинности.



</div>

<div class="">


> [!NOTE]  
> Веб-служба автообнаружения Lync определена в разделе <STRONG>протоколы Microsoft Office</STRONG> в разделе <STRONG>Open спецификации</STRONG> библиотеки <STRONG>Microsoft Developer Network</STRONG> (MSDN). Подробные сведения см. в документе с полным описанием "протокол веб-службы автообнаружения Lync" по <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>адресу:. Подробные сведения о проверке подлинности можно найти в <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>разделе "протокол веб-службы OC Authentication".



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Отклик автообнаружения веб-службы Lync Server

Ответ, возвращенный при отправке запроса автообнаружения, совпадает для внутреннего или внешнего клиента. Некоторые параметры, которые относятся к расположению, могут изменяться. Если клиентский запрос получен, но реальный пул отличается от того, к которому был подключен, домашний пул пользователя будет настроен для этого пользователя. Коллега, учетная запись которого находится в другом пуле, но вход в систему с помощью того же Office получит немного иной отклик. Ответ указывает на правильный сервер переднего плана или пул переднего плана для этого пользователя.

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

## <a name="autodiscover-response-document-details"></a>Сведения о документе ответа автообнаружения

Документ ответа автообнаружения может иметь один из двух форматов. По умолчанию используется формат нотации объектов JavaScript (JSON). Другой формат — XML-документ. В этом примере используется XML. Запрос и ответ можно предсказать, так как документ имеет определенную схему, определяющую формат. Строка в документе, описывающая используемую схему, является первой строкой в запросе или ответе:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

Определение **акцесслокатион = "External"** указывает на то, что запрос был выполнен от внешнего пользователя.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

Сипсерверинтерналакцесс и Сипсерверекстерналакцесс в настоящее время не используются. Эти записи зарезервированы для последующего использования.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

Сипклиентинтерналакцесс и Сипклиентекстерналакцесс описывают полное доменное имя и порт, которые внутренний или внешний клиент будет использовать для доступа к определенному серверу SIP. Клиент Lync для настольных ПК и приложение Магазина Windows для Lync используют эти записи в зависимости от их расположения (внутреннего или внешнего) для поиска сервера директории или сервера переднего плана.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover` Ссылки содержат точки входа службы автообнаружения. Атрибут Token содержит имя службы, а href — это URL-адрес, который определяет клиента, на котором можно найти службу. Клиенты во внешней сети используют `External/Autodiscover`. Служба автообнаружения устанавливается в рамках процесса развертывания. `Internal/Autodiscover`в настоящее время не используется и зарезервировано для последующего использования.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker` Ссылки содержат точки входа службы для внутренней и внешней службы посредника проверки подлинности, в данном случае SIP. svc. Атрибут Token содержит имя службы, а href — это URL-адрес, который определяет клиента, на котором можно найти службу. Клиенты во внутренней сети с использованием `Internal/AuthBroker`. Клиенты во внешней сети используют `External/AuthBroker`. Служба Аусброкер устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler` Маркер ссылается на URL-адреса для доступа клиентов к планированию веб-сайта для конференций Lync Server. В настоящее время используется `External/WebScheduler` только параметр. Веб-планировщик устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx``External/Mcx` — это расположения служб Mobility Services, которые представлены в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011. Эти ссылки продолжатся по мере использования Lync 2010 Mobile на всех поддерживаемых устройствах. Служба MCX устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **External/Ucwa** и **Ucwa** предоставляют клиентам доступ к интерфейсному интерфейсу веб-приложений единой системы обмена сообщениями (API Ucwa или просто Ucwa). `Internal/Ucwa``External/Ucwa` виртуальные каталоги — это точки доступа, зарезервированные для будущего улучшения возможностей, и не используются. `Ucwa` Виртуальный каталог используется для Microsoft Lync Mobile (в составе lync Server 2013) на всех поддерживаемых устройствах. Служба UCWA устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **Внешние/ксфраме** и **ксфраме** предоставляют доступ к серверным приложениям на основе UCWA. Ксфраме устанавливается в рамках процесса развертывания внутренней веб-службы развертывания Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self` Маркер ссылается на сведения, характерные для клиента (тип ответа пользователя), который делает запрос. Клиент, который проводил этот запрос, является внешним, и этот справочник по автообнаружения относится к пользовательской части службы автообнаружения.

</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к системе для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Планирование автообнаружения в Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

