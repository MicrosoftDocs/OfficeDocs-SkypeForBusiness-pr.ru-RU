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
ms.openlocfilehash: 2b87e395f56c7dfdbd03bf35c5c1c8cf37795652
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Шифрование для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-09-14_

Microsoft Lync Server 2013 использует протоколы TLS и MTLS для шифрования мгновенных сообщений. Весь трафик между серверами требует MTLS, независимо от того, насколько трафик ограничен внутренней сетью или он пересекает периметр внутренней сети. Протокол TLS является необязательным, но настоятельно рекомендуется между сервером-посредником и шлюзом мультимедиа. Если для этой ссылки настроен протокол TLS, необходимо указать MTLS. Поэтому шлюз должен быть настроен с помощью сертификата из центра сертификации, который является доверенным для сервера-посредника.

<div>


> [!NOTE]  
> Рекомендации по безопасности, связанные с SSL 3,0, были опубликованы в 2014. Отключение SSL 3,0 в Lync Server 2013 является поддерживаемым вариантом. Дополнительные сведения о рекомендациях по обеспечению безопасности <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>приведены в разделе.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" />Примечание о безопасности:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Чтобы обеспечить использование наиболее надежного протокола шифрования, Lync Server 2013 предоставит протоколы TLS-шифрования в следующем порядке для клиентов: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. Протокол TLS является важнейшим аспектом Lync Server 2013, поэтому он необходим для поддержки поддерживаемой среды.</td>
</tr>
</tbody>
</table>


</div>

Требования для клиентского трафика зависят от того, пересекает ли этот трафик внутренний корпоративный брандмауэр. Строго внутренний трафик может использовать TLS, в этом случае обмен мгновенными сообщениями будет шифроваться или TCP, в этом случае это не так.

В следующей таблице приведены требования к протоколам для каждого типа трафика.

### <a name="traffic-protection"></a>Защита трафика

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип трафика</th>
<th>Защищено</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Между серверами</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Между клиентом и сервером</p></td>
<td><p>TLS;</p></td>
</tr>
<tr class="odd">
<td><p>Обмен мгновенными сообщениями и сведения о присутствии</p></td>
<td><p>TLS (если настроено для TLS)</p></td>
</tr>
<tr class="even">
<td><p>Доступ к мультимедиа и аудио, видео и рабочему столу</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Общий доступ к рабочему столу (передача сигналов)</p></td>
<td><p>TLS;</p></td>
</tr>
<tr class="even">
<td><p>Веб-конференции</p></td>
<td><p>TLS;</p></td>
</tr>
<tr class="odd">
<td><p>Скачивание контента собраний, Загрузка адресной книги, расширение группы рассылки</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Шифрование мультимедиа

Трафик мультимедиа шифруется с помощью Secure RTP (SRTP), профиля транспортного протокола (RTP), который обеспечивает конфиденциальность, проверку подлинности и защиту от атак с повторением для трафика RTP. Кроме того, поток мультимедиа в обоих направлениях между сервером-посредником и внутренним следующим прыжком также шифруется с помощью SRTP. Поток мультимедиа в обоих направлениях между сервером-посредником и шлюзом мультимедиа по умолчанию не шифруется. Сервер-посредник может поддерживать шифрование на шлюзе мультимедиа, но шлюз должен поддерживать MTLS и хранилище сертификата.

<div>


> [!NOTE]  
> Аудио и видео (A/V) поддерживаются в новой версии Windows Live Messenger. Если вы реализуете Федерацию/V с помощью Windows Live Messenger, необходимо также изменить уровень шифрования Lync Server. По умолчанию уровень шифрования обязателен. Этот параметр необходимо изменить для поддержки с помощью командной консоли Lync Server. Для получения дополнительных сведений обратитесь <A href="lync-server-2013-deploying-external-user-access.md">к разделу развертывание доступа внешних пользователей в Lync Server 2013</A> в документации по развертыванию.



</div>

Трафик аудио-и видеофайла не шифруется между клиентами Microsoft Lync 2013 и Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 и Microsoft Exchange Server 2013 работают с поддержкой алгоритмов федерального стандарта обработки информации (FIPS) 140-2, если операционные системы Windows Server настроены на использование алгоритмов FIPS 140-2 для системной криптографии. Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, для его поддержки. Для получения дополнительных сведений об использовании алгоритмов, совместимых с FIPS и реализации поддержки FIPS, обратитесь к статье 811833 базы знаний Майкрософт, в которой приводится влияние включения параметра безопасности "Системная криптография: использование FIPS-совместимых алгоритмов для шифрования, хеширования и подписания" в Windows [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP и последующих версиях Windows по адресу. Подробные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 приведены в статье Exchange 2010 SP1 и поддержка алгоритмов, [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)совместимых с FIPS, по адресу.

</div>

</div>

<span> </span>

</div>

</div>

</div>

