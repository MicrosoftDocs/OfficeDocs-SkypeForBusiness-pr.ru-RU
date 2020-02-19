---
title: Сводка по DNS — SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Сводка по DNS — SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-03-09_

Записи доменных имен (DNS), которые необходимы для определения Федерации с партнерами Office Communications Server или Lync Server, определяются вашим решением для разрешения автоматического обнаружения DNS для домена другими перспективными партнерами. Если вы публикуете \_сипфедератионтлс. \_TCP. * \<Имя\> домена SIP* Запись SRV, любой другой федеративный домен SIP будет иметь возможность "Обнаружение" Федерации. Вы можете контролировать, какие федеративные домены могут связываться с вами с помощью параметров "разрешить домены и заблокированные домены" в панели управления Lync Server, а также путем установки конфигурации разрешенных или заблокированных доменов с помощью командной консоли Lync Server и командлетов **Get**, **Set**, **New**, **reCsAllowedDomain** и **CsBlockedDomain** PowerShell. Дополнительные сведения о том, как настроить эти параметры и использование командлетов PowerShell, можно найти в разделе **связанные темы** в конце этой статьи.

В таблице Сводка записей DNS показаны необходимые записи для открытой или обнаруживаемой Федерации. Если вы не хотите внедрять обнаружение Федерации, вы можете не настроить \_сипфедератионтлс. \_TCP. *Запись имени\> домена SIP. \<*

<div>


> [!IMPORTANT]
> Существуют определенные сценарии, в которых необходим _sipfederationtls. _tcp. <EM> &lt;Имя&gt; домена SIP</EM> Запись SRV, но вы не хотите иметь обнаруживаемую Федерацию. Один из таких экземпляров заключается в том, где вы развернули мобильность для пользователей. The Clearinghouse Push push-уведомлений (PNCH) — это специальный тип Федерации, который используется для мобильных клиентов Microsoft Lync в Apple iPhone или iPad с помощью мобильного клиента Lync 2010 или Windows Phone с помощью мобильных клиентов Lync 2010 Mobile или Lync 2013. _Sipfederationtls. _tcp. <EM> &lt;Имя&gt; домена SIP</EM> Запись SRV используется в случае мобильных устройств и Push-уведомления. Чтобы устранить эту ошибку и контролировать свое обнаружение, снимите флажок <STRONG>включить обнаружение домена партнера</STRONG> , чтобы отключить обнаружение.



</div>

Чтобы настроить расширенный протокол обмена сообщениями (XMPP) для развертывания, создайте две записи службы доменных имен (DNS) на внешнем DNS-сервере, которые будут разрешать записи в пограничной службе доступа пограничного сервера или пограничного пула.

При настройке службы доменных имен (DNS) для подключения к общедоступным службам обмена мгновенными сообщениями вы обнаружите, что конфигурация, поддерживающая внешних пользователей, будет поддерживать связь общедоступных МГНОВЕНных сообщений. Если вы уже настроили пограничный сервер или пограничный пул, у вас должны быть записи DNS, необходимые для поддержки подключения к общедоступным системам обмена мгновенными сообщениями.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>Сводка по DNS — Федерация SIP, включая общедоступные службы обмена мгновенными сообщениями


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>FQDN</th>
<th>IP-адрес/запись узла полного доменного имени</th>
<th>Сопоставление/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Внешний интерфейс службы пограничного доступа, необходимый для автоматического обнаружения DNS для Федерации другим потенциальным партнерам Федерации, называется "разрешенные домены SIP" (называемые расширенной Федерацию в предыдущих выпусках). Повторять при необходимости для всех доменов SIP с пользователями с включенной поддержкой Lync</p>



> [!IMPORTANT]
> Эта SRV-запись требуется для расчетной палаты push-уведомлений и мобильности. В случаях, когда имеется несколько доменов SIP, создайте и опубликуйте запись SRV для каждого домена, у которого будут клиенты Lync Mobile. Служба push-уведомлений и Служба push-уведомлений Apple могут работать не так, как ожидалось, если отсутствует явная запись SRV для каждого домена SIP, поддерживаемого развертыванием.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Сводка по DNS — расширяемый протокол обмена сообщениями и присутствия (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>FQDN</th>
<th>IP-адрес/запись узла полного доменного имени</th>
<th>Соответствует/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний DNS/SRV/5269</p></td>
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к Пользователь с поддержкой Lync. Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP. Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Внешний DNS/A</p></td>
<td><p>xmpp.contoso.com (пример)</p></td>
<td><p>IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</p></td>
<td><p>Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP. Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Настройка Федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Настройка для push-уведомлений в Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Включение и отключение обнаружения партнеров Федерации в Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Управление федеративными доменами SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

