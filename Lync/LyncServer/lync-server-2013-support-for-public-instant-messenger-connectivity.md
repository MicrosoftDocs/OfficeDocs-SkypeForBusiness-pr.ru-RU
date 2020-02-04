---
title: Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="8a54c-102">Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a54c-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a54c-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8a54c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="8a54c-104">Поддержка общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8a54c-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="8a54c-105">В этой статье приводятся сведения о поддержке общедоступной службы обмена мгновенными сообщениями (PIC).</span><span class="sxs-lookup"><span data-stu-id="8a54c-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="8a54c-106">PIC — компонент Microsoft Lync, с помощью которого пользователи Lync могут общаться с пользователями некоторых общедоступных служб обмена мгновенными сообщениями (IM) с клиентами и удостоверениями Lync.</span><span class="sxs-lookup"><span data-stu-id="8a54c-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="8a54c-107">Конечные пользователи получат возможность подключаться с клиентами, партнерами и поставщиками в соответствии с их условиями.</span><span class="sxs-lookup"><span data-stu-id="8a54c-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="8a54c-108">Это выгодно благодаря поддержке единого коммуникационного клиента в реальном времени при поддержке функций управления, соответствия требованиям и архивации в Lync.</span><span class="sxs-lookup"><span data-stu-id="8a54c-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="8a54c-109">Lync – подключение к Skype, [доступное в 2013 мая](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), основывается на устаревшей версии, которая впервые установлена на Lync/Office Communications Server (OCS)/Ливе Communications Server (LCS) для подключения к сети MSN/Windows Live, AOL и Yahoo.</span><span class="sxs-lookup"><span data-stu-id="8a54c-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="8a54c-110">Дополнительные сведения о подключении к Lync — Skype можно найти в разделе [Lync – подключение к Skype](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a54c-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="8a54c-111">Интеграция с Windows Live, AOL и Yahoo – каждый из них по пути к концу жизни.</span><span class="sxs-lookup"><span data-stu-id="8a54c-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="8a54c-112">На этой странице документируется состояние каждой службы.</span><span class="sxs-lookup"><span data-stu-id="8a54c-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="8a54c-113">Для использования PIC пользователям требовалось активировать службу для каждого поставщика услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8a54c-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="8a54c-114">Требования и подробные сведения о том, как это сделать, зависят от поставщика услуг обмена мгновенными сообщениями и базовой программы лицензирования клиента.</span><span class="sxs-lookup"><span data-stu-id="8a54c-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="8a54c-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8a54c-115">Windows Live Messenger</span></span>

<span data-ttu-id="8a54c-116">Microsoft Live Messenger и Skype для Windows.</span><span class="sxs-lookup"><span data-stu-id="8a54c-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="8a54c-117">В апреле 2013 Пользователи Messenger были перенесены в Skype при входе.</span><span class="sxs-lookup"><span data-stu-id="8a54c-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="8a54c-118">Пользователи Lync, которые полагаются на Федерацию с помощью Messenger, смогут общаться с контактами Messenger даже после того, как эти контакты появятся в Skype.</span><span class="sxs-lookup"><span data-stu-id="8a54c-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="8a54c-119">Нет ничего, что администраторы Lync и конечные пользователи Lync должны сделать это для обеспечения бесперебойности обслуживания, и управление этой возможностью в Lync остается таким же, как и для обмена сообщениями с Messenger.</span><span class="sxs-lookup"><span data-stu-id="8a54c-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="8a54c-120">Когда пользователи Messenger входят в Skype с помощью учетных записей Майкрософт (например, тех же учетных данных, которые используются для Messenger), все контакты из Messenger, в том числе Федеративные контакты Lync, поддерживайтесь Skype.</span><span class="sxs-lookup"><span data-stu-id="8a54c-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="8a54c-121">Вы можете обмениваться мгновенными сообщениями между Skype и Lync для этих контактов.</span><span class="sxs-lookup"><span data-stu-id="8a54c-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="8a54c-122">Lync – подключение к Skype — Добавление и обмен мгновенными сообщениями и голосовая связь между Lync и пользователями Skype теперь также доступна для всех пользователей Lync.</span><span class="sxs-lookup"><span data-stu-id="8a54c-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="8a54c-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8a54c-123">Yahoo\!</span></span> <span data-ttu-id="8a54c-124">и AOL для обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8a54c-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="8a54c-125">Интеграция с Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8a54c-125">Federation with Yahoo\!</span></span> <span data-ttu-id="8a54c-126">и AOL на пути к окончанию жизненного цикла пользователей Lync (и Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="8a54c-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="8a54c-127">Возможность предоставления каждой из этих услуг от корпорации Майкрософт зависит от поддержки от Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8a54c-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="8a54c-128">и AOL, а основные соглашения для них — это обмотка.</span><span class="sxs-lookup"><span data-stu-id="8a54c-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="8a54c-129">Как для Yahoo, так и для\!</span><span class="sxs-lookup"><span data-stu-id="8a54c-129">For both Yahoo\!</span></span> <span data-ttu-id="8a54c-130">и AOL, обслуживание будет продолжено до 2014 июня.</span><span class="sxs-lookup"><span data-stu-id="8a54c-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="8a54c-131">Служба **Yahoo** -Service пройдет через июнь 2014, и клиенты должны иметь лицензию на подписку Microsoft Lync Public reconnectivity (PIC усл).</span><span class="sxs-lookup"><span data-stu-id="8a54c-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="8a54c-132">По состоянию на 1 сентября 2012 г., усл PIC, больше не будет доступен для приобретения новых и обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="8a54c-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="8a54c-133">Клиенты с лицензиями, приобретенными до этой даты, смогут продолжать использовать федерацию с помощью Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8a54c-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="8a54c-134">до истечения срока действия службы, а не с момента ее окончания.</span><span class="sxs-lookup"><span data-stu-id="8a54c-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="8a54c-135">Прочтите [объявление](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) в блоге группы разработчиков Lync.</span><span class="sxs-lookup"><span data-stu-id="8a54c-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="8a54c-136">Пользователи, у которых есть лицензии на версии PIC на соглашениях, продленных до 30 июня, 2014 получит сумму пропорционально сумме выплат за период времени, заданный в течение 30 июня 2014 г.</span><span class="sxs-lookup"><span data-stu-id="8a54c-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="8a54c-137">**AOL** – это 30 июня 2014, но служба связи с помощью обмена мгновенными сообщениями LYNC (PIC) больше не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="8a54c-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="8a54c-138">Чтобы ограничить перерывы в работе пользователей при завершении работы службы, мы продолжим подготовку дополнительных доменов клиентов.</span><span class="sxs-lookup"><span data-stu-id="8a54c-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="8a54c-139">До 30 июня 2014 г. пользователи не обязаны выполнять никаких действий, чтобы продолжать поддерживать Федеративные коммуникации с целью.</span><span class="sxs-lookup"><span data-stu-id="8a54c-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="8a54c-140">За пределами этой даты (или для пользователей, которые хотели бы предоставлять дополнительные домены), служба подстановки доступна прямо из AOL.</span><span class="sxs-lookup"><span data-stu-id="8a54c-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="8a54c-141">Дополнительные сведения о новой службе AOL можно найти в разделе [Установка прямой Федерации с помощью AIM](http://aimenterprise.aol.com/pic.php)  (открывает новую страницу на AOL.com).</span><span class="sxs-lookup"><span data-stu-id="8a54c-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="8a54c-142">Общие сведения о поставщике мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="8a54c-142">Public IM Provider Summary</span></span>

<span data-ttu-id="8a54c-143">В следующей таблице представлены общие сведения о поставщиках услуг обмена мгновенными сообщениями, возможности Федерации с Lync и требования к лицензированию.</span><span class="sxs-lookup"><span data-stu-id="8a54c-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a54c-144">Поставщик общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8a54c-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="8a54c-145">Федеративные возможности</span><span class="sxs-lookup"><span data-stu-id="8a54c-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="8a54c-146">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="8a54c-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a54c-147">Skype</span><span class="sxs-lookup"><span data-stu-id="8a54c-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="8a54c-148">Обмен мгновенными сообщениями, присутствие, звук</span><span class="sxs-lookup"><span data-stu-id="8a54c-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="8a54c-149">Клиентские лицензии на доступ к Lync Server, Lync Online (план 1/2/3)</span><span class="sxs-lookup"><span data-stu-id="8a54c-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a54c-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8a54c-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="8a54c-151">Обмен мгновенными сообщениями, звук и видео</span><span class="sxs-lookup"><span data-stu-id="8a54c-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="8a54c-152">Клиентские лицензии на Lync Server (поддерживаются, пока ВЛМ находятся на рынке)</span><span class="sxs-lookup"><span data-stu-id="8a54c-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a54c-153">AOL</span><span class="sxs-lookup"><span data-stu-id="8a54c-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="8a54c-154">СООБЩЕНИЕ о присутствии</span><span class="sxs-lookup"><span data-stu-id="8a54c-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="8a54c-155">Клиентские лицензии на доступ к Lync Server; поддерживается в июне 2014 для существующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="8a54c-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a54c-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8a54c-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="8a54c-157">СООБЩЕНИЕ о присутствии</span><span class="sxs-lookup"><span data-stu-id="8a54c-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="8a54c-158">Требуется дополнительная лицензия на подписку общедоступной службы обмена мгновенными сообщениями Microsoft Lync (PIC усл) в дополнение к лицензиям клиентского доступа к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a54c-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="8a54c-159">В списке цен за Сентябрь 2012 усл PIC больше не доступен для приобретения.</span><span class="sxs-lookup"><span data-stu-id="8a54c-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="8a54c-160">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8a54c-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8a54c-161">Messenger, пока служба не отключается от 30 июня 2014 г.</span><span class="sxs-lookup"><span data-stu-id="8a54c-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

