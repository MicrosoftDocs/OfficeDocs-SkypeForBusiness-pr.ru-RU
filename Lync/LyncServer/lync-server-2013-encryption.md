---
title: 'Lync Server 2013: шифрование'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Шифрование для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2017-09-14_

Microsoft Lync Server 2013 использует TLS и MTLS для шифрования мгновенных сообщений. Для трафика от сервера к серверу требуется MTLS, независимо от того, ограничивается ли трафик внутренней сетью или пересекает внутренний периметр сети. TLS является необязательным, но настоятельно рекомендуется между сервером и шлюзом мультимедийных обновлений. If TLS is configured on this link, MTLS is required. Таким образом, шлюз должен быть настроен на сертификат от центра сертификации, которому доверяет сервер-посредник.

<div>


> [!NOTE]  
> Советы по безопасности в отношении SSL 3.0 были опубликованы в 2014 г. Отключение SSL 3,0 в Lync Server 2013 является поддерживаемым вариантом. Дополнительные сведения о рекомендациях по безопасности можно найти <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>в разделе.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" />Примечание о безопасности:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Для обеспечения использования наиболее надежного криптографических протоколов Lync Server 2013 предлагает клиентам протоколы TLS Encryption в следующем порядке: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. Протокол TLS является важнейшим аспектом Lync Server 2013, поэтому он необходим для поддержки поддерживаемой среды.</td>
</tr>
</tbody>
</table>


</div>

Требования к трафику "клиент-клиент" зависят от того, пересекает ли этот трафик внутренний корпоративный брандмауэр. Строго внутренний трафик может использовать TLS, и в этом случае обмен мгновенными сообщениями будет шифроваться или TCP, в этом случае это не так.

В следующей таблице представлена сводка требований протокола для каждого типа трафика.

### <a name="traffic-protection"></a>Защита трафика

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип трафика</th>
<th>Защита</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Сервер-сервер</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Клиент-сервер</p></td>
<td><p>Протокол TLS</p></td>
</tr>
<tr class="odd">
<td><p>Мгновенные сообщения и присутствие</p></td>
<td><p>TLS (если настроено для TLS)</p></td>
</tr>
<tr class="even">
<td><p>Аудио/видео и рабочий стол для общего доступа к мультимедиа</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Общий доступ к рабочему столу (передача сигналов)</p></td>
<td><p>Протокол TLS</p></td>
</tr>
<tr class="even">
<td><p>веб-конференции</p></td>
<td><p>Протокол TLS</p></td>
</tr>
<tr class="odd">
<td><p>Загрузка содержимого собрания, загрузка адресной книги, расширение группы рассылки</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Шифрование мультимедиа

Трафик мультимедиа шифруется по протоколу SRTP, профилю протокола RTP, который обеспечивает конфиденциальность, проверку подлинности и защиту от атак с повторением пакетов для трафика RTP. Кроме того, потоки мультимедиа в обоих направлениях между сервером-посредником и его внутренним узлом следующего прыжка также шифруются с помощью SRTP. Поток мультимедиа в обоих направлениях между сервером-посредником и шлюзом мультимедиа по умолчанию не шифруется. Сервер-посредник может обеспечивать шифрование на медиашлюзе, однако шлюз должен поддерживать MTLS и хранилище сертификатов.

<div>


> [!NOTE]  
> Аудио/видео (A/V) поддерживается новой версией Windows Live Messenger. Если вы реализуете Федерацию/V с Windows Live Messenger, необходимо также изменить уровень шифрования Lync Server. By default, the encryption level is Required. Вы должны изменить этот параметр так, чтобы он поддерживался с помощью командной консоли Lync Server Management Shell. Дополнительные сведения можно найти <A href="lync-server-2013-deploying-external-user-access.md">в разделе Развертывание внешних пользователей Access в Lync Server 2013</A> в документации по развертыванию.



</div>

Трафик аудио и видеофайла не шифруется между клиентами Microsoft Lync 2013 и Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 и Microsoft Exchange Server 2013 работают с поддержкой алгоритмов стандартизации стандарта обработки информации (FIPS) 140-2, если серверные операционные системы Windows настроены на использование алгоритмов FIPS 140-2 для системы криптографии. Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, чтобы его поддерживать. Подробнее об использовании алгоритмов, совместимых с FIPS, и о том, как реализовать поддержку FIPS, можно найти в статье 811833 базы знаний Майкрософт, которая влияет на параметры безопасности "Системная криптография: использование алгоритмов, совместимых с FIPS для шифрования, хеширования и подписи" в Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP и более поздних версиях Windows. Дополнительные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 можно найти в [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)статьях Exchange 2010 SP1 и поддержка алгоритмов, совместимых с FIPS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

