---
title: 'Lync Server 2013: шифрование'
description: 'Lync Server 2013: шифрование.'
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
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575655"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="8a600-103">Шифрование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a600-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a600-104">_**Последнее изменение темы:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="8a600-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="8a600-105">Microsoft Lync Server 2013 использует протоколы TLS и MTLS для шифрования мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="8a600-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="8a600-106">Весь трафик между серверами требует MTLS, независимо от того, насколько трафик ограничен внутренней сетью или он пересекает периметр внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="8a600-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="8a600-107">Протокол TLS является необязательным, но настоятельно рекомендуется между сервером-посредником и шлюзом мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8a600-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="8a600-108">Если для этой ссылки настроен протокол TLS, необходимо указать MTLS.</span><span class="sxs-lookup"><span data-stu-id="8a600-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="8a600-109">Поэтому шлюз должен быть настроен с помощью сертификата из центра сертификации, который является доверенным для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8a600-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a600-110">Рекомендации по безопасности, связанные с SSL 3,0, были опубликованы в 2014.</span><span class="sxs-lookup"><span data-stu-id="8a600-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="8a600-111">Отключение SSL 3,0 в Lync Server 2013 является поддерживаемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="8a600-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="8a600-112">Дополнительные сведения о рекомендациях по обеспечению безопасности приведены в разделе <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="8a600-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="8a600-114">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="8a600-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8a600-115">Чтобы обеспечить использование наиболее надежного протокола шифрования, Lync Server 2013 предоставит протоколы TLS-шифрования в следующем порядке для клиентов: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a600-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="8a600-116">Протокол TLS является важнейшим аспектом Lync Server 2013, поэтому он необходим для поддержки поддерживаемой среды.</span><span class="sxs-lookup"><span data-stu-id="8a600-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="8a600-117">Требования для клиентского трафика зависят от того, пересекает ли этот трафик внутренний корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="8a600-117">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="8a600-118">Строго внутренний трафик может использовать TLS, в этом случае обмен мгновенными сообщениями будет шифроваться или TCP, в этом случае это не так.</span><span class="sxs-lookup"><span data-stu-id="8a600-118">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="8a600-119">В следующей таблице приведены требования к протоколам для каждого типа трафика.</span><span class="sxs-lookup"><span data-stu-id="8a600-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="8a600-120">Защита трафика</span><span class="sxs-lookup"><span data-stu-id="8a600-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a600-121">Тип трафика</span><span class="sxs-lookup"><span data-stu-id="8a600-121">Traffic type</span></span></th>
<th><span data-ttu-id="8a600-122">Защищено</span><span class="sxs-lookup"><span data-stu-id="8a600-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a600-123">Между серверами</span><span class="sxs-lookup"><span data-stu-id="8a600-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="8a600-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="8a600-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a600-125">Между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="8a600-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="8a600-126">TLS;</span><span class="sxs-lookup"><span data-stu-id="8a600-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a600-127">Обмен мгновенными сообщениями и сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="8a600-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="8a600-128">TLS (если настроено для TLS)</span><span class="sxs-lookup"><span data-stu-id="8a600-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a600-129">Доступ к мультимедиа и аудио, видео и рабочему столу</span><span class="sxs-lookup"><span data-stu-id="8a600-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="8a600-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="8a600-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a600-131">Общий доступ к рабочему столу (передача сигналов)</span><span class="sxs-lookup"><span data-stu-id="8a600-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="8a600-132">TLS;</span><span class="sxs-lookup"><span data-stu-id="8a600-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a600-133">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="8a600-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="8a600-134">TLS;</span><span class="sxs-lookup"><span data-stu-id="8a600-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a600-135">Скачивание контента собраний, Загрузка адресной книги, расширение группы рассылки</span><span class="sxs-lookup"><span data-stu-id="8a600-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="8a600-136">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8a600-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="8a600-137">Шифрование мультимедиа</span><span class="sxs-lookup"><span data-stu-id="8a600-137">Media Encryption</span></span>

<span data-ttu-id="8a600-138">Трафик мультимедиа шифруется с помощью Secure RTP (SRTP), Real-Time профиля протокола RTP, который обеспечивает конфиденциальность, проверку подлинности и защиту от атак с повторением для трафика RTP.</span><span class="sxs-lookup"><span data-stu-id="8a600-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="8a600-139">Кроме того, носитель, проходящий в обоих направлениях между сервером-посредником и его внутренним следующим участком, также шифруется с использованием SRTP.</span><span class="sxs-lookup"><span data-stu-id="8a600-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="8a600-140">Поток мультимедиа в обоих направлениях между сервером-посредником и шлюзом мультимедиа по умолчанию не шифруется.</span><span class="sxs-lookup"><span data-stu-id="8a600-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="8a600-141">Сервер-посредник может поддерживать шифрование на шлюзе мультимедиа, но шлюз должен поддерживать MTLS и хранилище сертификата.</span><span class="sxs-lookup"><span data-stu-id="8a600-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a600-142">Аудио и видео (A/V) поддерживаются в новой версии Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="8a600-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="8a600-143">Если вы реализуете Федерацию/V с помощью Windows Live Messenger, необходимо также изменить уровень шифрования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a600-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="8a600-144">По умолчанию уровень шифрования обязателен.</span><span class="sxs-lookup"><span data-stu-id="8a600-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="8a600-145">Этот параметр необходимо изменить для поддержки с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a600-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="8a600-146">Для получения дополнительных сведений обратитесь <A href="lync-server-2013-deploying-external-user-access.md">к разделу развертывание доступа внешних пользователей в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8a600-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="8a600-147">Трафик аудио-и видеофайла не шифруется между клиентами Microsoft Lync 2013 и Windows Live.</span><span class="sxs-lookup"><span data-stu-id="8a600-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="8a600-148">FIPS</span><span class="sxs-lookup"><span data-stu-id="8a600-148">FIPS</span></span>

<span data-ttu-id="8a600-149">Lync Server 2013 и Microsoft Exchange Server 2013 работают с поддержкой алгоритмов федерального стандарта обработки информации (FIPS) 140-2, если операционные системы Windows Server настроены на использование алгоритмов FIPS 140-2 для системной криптографии.</span><span class="sxs-lookup"><span data-stu-id="8a600-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="8a600-150">Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, для его поддержки.</span><span class="sxs-lookup"><span data-stu-id="8a600-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="8a600-151">Для получения дополнительных сведений об использовании алгоритмов, совместимых с FIPS и реализации поддержки FIPS, обратитесь к статье 811833 базы знаний Майкрософт, в которой приводится влияние включения параметра безопасности "Системная криптография: использование FIPS-совместимых алгоритмов для шифрования, хеширования и подписания" в Windows XP и последующих версиях Windows по адресу [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="8a600-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="8a600-152">Подробные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 приведены в статье Exchange 2010 SP1 и поддержка алгоритмов, совместимых с FIPS, по адресу [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="8a600-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

