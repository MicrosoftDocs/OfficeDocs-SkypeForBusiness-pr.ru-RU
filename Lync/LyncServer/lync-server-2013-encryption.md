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

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="5bb53-102">Шифрование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bb53-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bb53-103">_**Тема последнего изменения:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="5bb53-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="5bb53-104">Microsoft Lync Server 2013 использует TLS и MTLS для шифрования мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="5bb53-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="5bb53-105">Для трафика от сервера к серверу требуется MTLS, независимо от того, ограничивается ли трафик внутренней сетью или пересекает внутренний периметр сети.</span><span class="sxs-lookup"><span data-stu-id="5bb53-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="5bb53-106">TLS является необязательным, но настоятельно рекомендуется между сервером и шлюзом мультимедийных обновлений.</span><span class="sxs-lookup"><span data-stu-id="5bb53-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="5bb53-107">If TLS is configured on this link, MTLS is required.</span><span class="sxs-lookup"><span data-stu-id="5bb53-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="5bb53-108">Таким образом, шлюз должен быть настроен на сертификат от центра сертификации, которому доверяет сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="5bb53-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bb53-109">Советы по безопасности в отношении SSL 3.0 были опубликованы в 2014 г.</span><span class="sxs-lookup"><span data-stu-id="5bb53-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="5bb53-110">Отключение SSL 3,0 в Lync Server 2013 является поддерживаемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="5bb53-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="5bb53-111">Дополнительные сведения о рекомендациях по безопасности можно найти <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>в разделе.</span><span class="sxs-lookup"><span data-stu-id="5bb53-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="5bb53-113">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="5bb53-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5bb53-114">Для обеспечения использования наиболее надежного криптографических протоколов Lync Server 2013 предлагает клиентам протоколы TLS Encryption в следующем порядке: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="5bb53-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="5bb53-115">Протокол TLS является важнейшим аспектом Lync Server 2013, поэтому он необходим для поддержки поддерживаемой среды.</span><span class="sxs-lookup"><span data-stu-id="5bb53-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="5bb53-116">Требования к трафику "клиент-клиент" зависят от того, пересекает ли этот трафик внутренний корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="5bb53-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="5bb53-117">Строго внутренний трафик может использовать TLS, и в этом случае обмен мгновенными сообщениями будет шифроваться или TCP, в этом случае это не так.</span><span class="sxs-lookup"><span data-stu-id="5bb53-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="5bb53-118">В следующей таблице представлена сводка требований протокола для каждого типа трафика.</span><span class="sxs-lookup"><span data-stu-id="5bb53-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="5bb53-119">Защита трафика</span><span class="sxs-lookup"><span data-stu-id="5bb53-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bb53-120">Тип трафика</span><span class="sxs-lookup"><span data-stu-id="5bb53-120">Traffic type</span></span></th>
<th><span data-ttu-id="5bb53-121">Защита</span><span class="sxs-lookup"><span data-stu-id="5bb53-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bb53-122">Сервер-сервер</span><span class="sxs-lookup"><span data-stu-id="5bb53-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="5bb53-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="5bb53-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb53-124">Клиент-сервер</span><span class="sxs-lookup"><span data-stu-id="5bb53-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="5bb53-125">Протокол TLS</span><span class="sxs-lookup"><span data-stu-id="5bb53-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb53-126">Мгновенные сообщения и присутствие</span><span class="sxs-lookup"><span data-stu-id="5bb53-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="5bb53-127">TLS (если настроено для TLS)</span><span class="sxs-lookup"><span data-stu-id="5bb53-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb53-128">Аудио/видео и рабочий стол для общего доступа к мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5bb53-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="5bb53-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="5bb53-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb53-130">Общий доступ к рабочему столу (передача сигналов)</span><span class="sxs-lookup"><span data-stu-id="5bb53-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="5bb53-131">Протокол TLS</span><span class="sxs-lookup"><span data-stu-id="5bb53-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb53-132">веб-конференции</span><span class="sxs-lookup"><span data-stu-id="5bb53-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="5bb53-133">Протокол TLS</span><span class="sxs-lookup"><span data-stu-id="5bb53-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb53-134">Загрузка содержимого собрания, загрузка адресной книги, расширение группы рассылки</span><span class="sxs-lookup"><span data-stu-id="5bb53-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="5bb53-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="5bb53-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="5bb53-136">Шифрование мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5bb53-136">Media Encryption</span></span>

<span data-ttu-id="5bb53-137">Трафик мультимедиа шифруется по протоколу SRTP, профилю протокола RTP, который обеспечивает конфиденциальность, проверку подлинности и защиту от атак с повторением пакетов для трафика RTP.</span><span class="sxs-lookup"><span data-stu-id="5bb53-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="5bb53-138">Кроме того, потоки мультимедиа в обоих направлениях между сервером-посредником и его внутренним узлом следующего прыжка также шифруются с помощью SRTP.</span><span class="sxs-lookup"><span data-stu-id="5bb53-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="5bb53-139">Поток мультимедиа в обоих направлениях между сервером-посредником и шлюзом мультимедиа по умолчанию не шифруется.</span><span class="sxs-lookup"><span data-stu-id="5bb53-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="5bb53-140">Сервер-посредник может обеспечивать шифрование на медиашлюзе, однако шлюз должен поддерживать MTLS и хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5bb53-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bb53-141">Аудио/видео (A/V) поддерживается новой версией Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="5bb53-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="5bb53-142">Если вы реализуете Федерацию/V с Windows Live Messenger, необходимо также изменить уровень шифрования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bb53-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="5bb53-143">By default, the encryption level is Required.</span><span class="sxs-lookup"><span data-stu-id="5bb53-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="5bb53-144">Вы должны изменить этот параметр так, чтобы он поддерживался с помощью командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5bb53-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="5bb53-145">Дополнительные сведения можно найти <A href="lync-server-2013-deploying-external-user-access.md">в разделе Развертывание внешних пользователей Access в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5bb53-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="5bb53-146">Трафик аудио и видеофайла не шифруется между клиентами Microsoft Lync 2013 и Windows Live.</span><span class="sxs-lookup"><span data-stu-id="5bb53-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="5bb53-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="5bb53-147">FIPS</span></span>

<span data-ttu-id="5bb53-148">Lync Server 2013 и Microsoft Exchange Server 2013 работают с поддержкой алгоритмов стандартизации стандарта обработки информации (FIPS) 140-2, если серверные операционные системы Windows настроены на использование алгоритмов FIPS 140-2 для системы криптографии.</span><span class="sxs-lookup"><span data-stu-id="5bb53-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="5bb53-149">Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, чтобы его поддерживать.</span><span class="sxs-lookup"><span data-stu-id="5bb53-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="5bb53-150">Подробнее об использовании алгоритмов, совместимых с FIPS, и о том, как реализовать поддержку FIPS, можно найти в статье 811833 базы знаний Майкрософт, которая влияет на параметры безопасности "Системная криптография: использование алгоритмов, совместимых с FIPS для шифрования, хеширования и подписи" в Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="5bb53-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="5bb53-151">Дополнительные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 можно найти в [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)статьях Exchange 2010 SP1 и поддержка алгоритмов, совместимых с FIPS.</span><span class="sxs-lookup"><span data-stu-id="5bb53-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

