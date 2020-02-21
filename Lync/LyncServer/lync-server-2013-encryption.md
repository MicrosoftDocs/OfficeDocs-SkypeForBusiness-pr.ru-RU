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

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="31927-102">Шифрование для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31927-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31927-103">_**Последнее изменение темы:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="31927-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="31927-104">Microsoft Lync Server 2013 использует протоколы TLS и MTLS для шифрования мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="31927-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="31927-105">Весь трафик между серверами требует MTLS, независимо от того, насколько трафик ограничен внутренней сетью или он пересекает периметр внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="31927-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="31927-106">Протокол TLS является необязательным, но настоятельно рекомендуется между сервером-посредником и шлюзом мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="31927-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="31927-107">Если для этой ссылки настроен протокол TLS, необходимо указать MTLS.</span><span class="sxs-lookup"><span data-stu-id="31927-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="31927-108">Поэтому шлюз должен быть настроен с помощью сертификата из центра сертификации, который является доверенным для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="31927-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31927-109">Рекомендации по безопасности, связанные с SSL 3,0, были опубликованы в 2014.</span><span class="sxs-lookup"><span data-stu-id="31927-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="31927-110">Отключение SSL 3,0 в Lync Server 2013 является поддерживаемым вариантом.</span><span class="sxs-lookup"><span data-stu-id="31927-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="31927-111">Дополнительные сведения о рекомендациях по обеспечению безопасности <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>приведены в разделе.</span><span class="sxs-lookup"><span data-stu-id="31927-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="31927-113">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="31927-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="31927-114">Чтобы обеспечить использование наиболее надежного протокола шифрования, Lync Server 2013 предоставит протоколы TLS-шифрования в следующем порядке для клиентов: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="31927-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="31927-115">Протокол TLS является важнейшим аспектом Lync Server 2013, поэтому он необходим для поддержки поддерживаемой среды.</span><span class="sxs-lookup"><span data-stu-id="31927-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="31927-116">Требования для клиентского трафика зависят от того, пересекает ли этот трафик внутренний корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="31927-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="31927-117">Строго внутренний трафик может использовать TLS, в этом случае обмен мгновенными сообщениями будет шифроваться или TCP, в этом случае это не так.</span><span class="sxs-lookup"><span data-stu-id="31927-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="31927-118">В следующей таблице приведены требования к протоколам для каждого типа трафика.</span><span class="sxs-lookup"><span data-stu-id="31927-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="31927-119">Защита трафика</span><span class="sxs-lookup"><span data-stu-id="31927-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31927-120">Тип трафика</span><span class="sxs-lookup"><span data-stu-id="31927-120">Traffic type</span></span></th>
<th><span data-ttu-id="31927-121">Защищено</span><span class="sxs-lookup"><span data-stu-id="31927-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31927-122">Между серверами</span><span class="sxs-lookup"><span data-stu-id="31927-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="31927-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="31927-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31927-124">Между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="31927-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="31927-125">TLS;</span><span class="sxs-lookup"><span data-stu-id="31927-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31927-126">Обмен мгновенными сообщениями и сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="31927-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="31927-127">TLS (если настроено для TLS)</span><span class="sxs-lookup"><span data-stu-id="31927-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31927-128">Доступ к мультимедиа и аудио, видео и рабочему столу</span><span class="sxs-lookup"><span data-stu-id="31927-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="31927-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="31927-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31927-130">Общий доступ к рабочему столу (передача сигналов)</span><span class="sxs-lookup"><span data-stu-id="31927-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="31927-131">TLS;</span><span class="sxs-lookup"><span data-stu-id="31927-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31927-132">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="31927-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="31927-133">TLS;</span><span class="sxs-lookup"><span data-stu-id="31927-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31927-134">Скачивание контента собраний, Загрузка адресной книги, расширение группы рассылки</span><span class="sxs-lookup"><span data-stu-id="31927-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="31927-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="31927-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="31927-136">Шифрование мультимедиа</span><span class="sxs-lookup"><span data-stu-id="31927-136">Media Encryption</span></span>

<span data-ttu-id="31927-137">Трафик мультимедиа шифруется с помощью Secure RTP (SRTP), профиля транспортного протокола (RTP), который обеспечивает конфиденциальность, проверку подлинности и защиту от атак с повторением для трафика RTP.</span><span class="sxs-lookup"><span data-stu-id="31927-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="31927-138">Кроме того, поток мультимедиа в обоих направлениях между сервером-посредником и внутренним следующим прыжком также шифруется с помощью SRTP.</span><span class="sxs-lookup"><span data-stu-id="31927-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="31927-139">Поток мультимедиа в обоих направлениях между сервером-посредником и шлюзом мультимедиа по умолчанию не шифруется.</span><span class="sxs-lookup"><span data-stu-id="31927-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="31927-140">Сервер-посредник может поддерживать шифрование на шлюзе мультимедиа, но шлюз должен поддерживать MTLS и хранилище сертификата.</span><span class="sxs-lookup"><span data-stu-id="31927-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31927-141">Аудио и видео (A/V) поддерживаются в новой версии Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="31927-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="31927-142">Если вы реализуете Федерацию/V с помощью Windows Live Messenger, необходимо также изменить уровень шифрования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31927-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="31927-143">По умолчанию уровень шифрования обязателен.</span><span class="sxs-lookup"><span data-stu-id="31927-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="31927-144">Этот параметр необходимо изменить для поддержки с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31927-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="31927-145">Для получения дополнительных сведений обратитесь <A href="lync-server-2013-deploying-external-user-access.md">к разделу развертывание доступа внешних пользователей в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="31927-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="31927-146">Трафик аудио-и видеофайла не шифруется между клиентами Microsoft Lync 2013 и Windows Live.</span><span class="sxs-lookup"><span data-stu-id="31927-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="31927-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="31927-147">FIPS</span></span>

<span data-ttu-id="31927-148">Lync Server 2013 и Microsoft Exchange Server 2013 работают с поддержкой алгоритмов федерального стандарта обработки информации (FIPS) 140-2, если операционные системы Windows Server настроены на использование алгоритмов FIPS 140-2 для системной криптографии.</span><span class="sxs-lookup"><span data-stu-id="31927-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="31927-149">Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, для его поддержки.</span><span class="sxs-lookup"><span data-stu-id="31927-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="31927-150">Для получения дополнительных сведений об использовании алгоритмов, совместимых с FIPS и реализации поддержки FIPS, обратитесь к статье 811833 базы знаний Майкрософт, в которой приводится влияние включения параметра безопасности "Системная криптография: использование FIPS-совместимых алгоритмов для шифрования, хеширования и подписания" в Windows [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP и последующих версиях Windows по адресу.</span><span class="sxs-lookup"><span data-stu-id="31927-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="31927-151">Подробные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 приведены в статье Exchange 2010 SP1 и поддержка алгоритмов, [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)совместимых с FIPS, по адресу.</span><span class="sxs-lookup"><span data-stu-id="31927-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

