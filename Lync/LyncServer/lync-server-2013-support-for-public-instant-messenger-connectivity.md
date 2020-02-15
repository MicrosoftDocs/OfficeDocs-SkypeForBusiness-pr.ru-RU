---
title: Lync Server 2013 — поддержка подключения к общедоступной службе обмена мгновенными сообщениями
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
ms.openlocfilehash: 8a6941fb5f087d667e65c178474531aa573a61b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="40b92-102">Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b92-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b92-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="40b92-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="40b92-104">Поддержка общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="40b92-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="40b92-105">В этой статье представлены сведения о поддержке общедоступной службы обмена мгновенными сообщениями (PIC).</span><span class="sxs-lookup"><span data-stu-id="40b92-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="40b92-106">PIC — это функция Microsoft Lync, позволяющая пользователям Lync подключаться к пользователям из определенных общедоступных служб обмена мгновенными сообщениями (IM) с помощью клиентов и удостоверений Lync.</span><span class="sxs-lookup"><span data-stu-id="40b92-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="40b92-107">Конечные пользователи смогут подключаться к их условиям клиентов, партнеров и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="40b92-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="40b92-108">ИТ выгодно поддерживать единый клиент связи в режиме реального времени, сохраняя функции управления, обеспечения соответствия требованиям и архивации в Lync.</span><span class="sxs-lookup"><span data-stu-id="40b92-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="40b92-109">Lync — подключение к Skype, [общедоступное в 2013 мая](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), основано на устаревшем сервере Lync/Office Communications Server (OCS)/Ливе Communications Server (LCS), который впервые установлен с PIC при подключении к MSN/Windows Live, AOL и Yahoo.</span><span class="sxs-lookup"><span data-stu-id="40b92-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="40b92-110">Для получения дополнительных сведений о подключении Lync — Skype обратитесь к разделу [Подключение Lync — Skype](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="40b92-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="40b92-111">Федерация с Windows Live, AOL и Yahoo — это по пути к концу жизни.</span><span class="sxs-lookup"><span data-stu-id="40b92-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="40b92-112">На этой странице документируется состояние каждой службы.</span><span class="sxs-lookup"><span data-stu-id="40b92-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="40b92-113">Чтобы использовать PIC, пользователям необходимо активировать службу для каждого поставщика общедоступных служб обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="40b92-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="40b92-114">Требования и сведения о том, как это сделать, зависят от поставщика услуг обмена мгновенными сообщениями и основной программы лицензирования клиента.</span><span class="sxs-lookup"><span data-stu-id="40b92-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="40b92-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="40b92-115">Windows Live Messenger</span></span>

<span data-ttu-id="40b92-116">Корпорация Майкрософт приходила к работе с Windows Live Messenger и Skype.</span><span class="sxs-lookup"><span data-stu-id="40b92-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="40b92-117">В апреле 2013 Пользователи Messenger были перенесены в Skype при входе.</span><span class="sxs-lookup"><span data-stu-id="40b92-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="40b92-118">Клиенты Lync, которые используют Федерацию с Messenger, продолжат общаться с контактами Messenger, даже после обновления контактов в Skype.</span><span class="sxs-lookup"><span data-stu-id="40b92-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="40b92-119">Нет ничего, что администраторы Lync или пользователи Lync должны сделать для поддержания непрерывности обслуживания, а управление этой возможностью в Lync остается таким же, как и для обмена сообщениями с Messenger.</span><span class="sxs-lookup"><span data-stu-id="40b92-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="40b92-120">Когда пользователи Messenger подключаются к Skype с помощью учетных записей Майкрософт (то есть те же учетные данные, которые используются для Messenger), все контакты Messenger, в том числе Федеративные контакты Lync, подписываются в Skype.</span><span class="sxs-lookup"><span data-stu-id="40b92-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="40b92-121">Доступен общий доступ к информации о присутствии и обмен мгновенными сообщениями между Skype и Lync для этих контактов.</span><span class="sxs-lookup"><span data-stu-id="40b92-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="40b92-122">Lync — подключение к Skype — Добавление контактов, общий доступ к присутствию, Обмен мгновенными сообщениями, Обмен мгновенными сообщениями между Lync и пользователями Skype теперь также доступен всем пользователям Lync.</span><span class="sxs-lookup"><span data-stu-id="40b92-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="40b92-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="40b92-123">Yahoo\!</span></span> <span data-ttu-id="40b92-124">и AOL Instant Messenger</span><span class="sxs-lookup"><span data-stu-id="40b92-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="40b92-125">Федерация с Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="40b92-125">Federation with Yahoo\!</span></span> <span data-ttu-id="40b92-126">и AOL помещаются по пути к концу жизни для клиентов Lync (и Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="40b92-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="40b92-127">Способность корпорации Майкрософт предоставлять каждую из этих служб в зависимости от поддержки в Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="40b92-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="40b92-128">и AOL, а их основные соглашения — обмотка.</span><span class="sxs-lookup"><span data-stu-id="40b92-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="40b92-129">Как для Yahoo, так и для\!</span><span class="sxs-lookup"><span data-stu-id="40b92-129">For both Yahoo\!</span></span> <span data-ttu-id="40b92-130">и AOL служба продолжит работу через июнь 2014.</span><span class="sxs-lookup"><span data-stu-id="40b92-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="40b92-131">Служба **Yahoo** -Service будет продолжаться до 2014 июня, а клиентам будет необходимо лицензироваться с лицензией на подписку общедоступной службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл").</span><span class="sxs-lookup"><span data-stu-id="40b92-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="40b92-132">С 1 сентября 2012 г. усл PIC больше недоступен для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="40b92-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="40b92-133">Клиенты с лицензиями, приобретенными до этой даты, смогут продолжать Федерацию с помощью Yahoo.\!</span><span class="sxs-lookup"><span data-stu-id="40b92-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="40b92-134">до даты завершения работы службы или до истечения срока действия лицензии.</span><span class="sxs-lookup"><span data-stu-id="40b92-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="40b92-135">Прочтите [объявление](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) в блоге группы разработчиков Lync.</span><span class="sxs-lookup"><span data-stu-id="40b92-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="40b92-136">Клиенты с лицензиями PIC, которые выходят за пределы 30 июня, 2014 будут получать кредит пропорционально сумме платежей, охватывающих 30 июня 2014 г.</span><span class="sxs-lookup"><span data-stu-id="40b92-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="40b92-137">**AOL** — 30 июня 2014, Служба подключения к службе обмена мгновенными сообщениями Lync ("Pic") больше не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="40b92-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="40b92-138">Чтобы ограничить перерывы в работе клиентов при завершении работы службы, мы не продолжим подготовку дополнительных доменов клиентов.</span><span class="sxs-lookup"><span data-stu-id="40b92-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="40b92-139">До 30 июня 2014 пользователям не нужно предпринимать никаких действий для продолжения поддержки федеративного общения с целью.</span><span class="sxs-lookup"><span data-stu-id="40b92-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="40b92-140">За пределами этой даты (или для клиентов, которые хотят подготовить дополнительные домены), доступна только служба AOL.</span><span class="sxs-lookup"><span data-stu-id="40b92-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="40b92-141">Более подробную информацию о новой службе AOL вы найдете в статье [Установка прямой Федерации с помощью AIM](http://aimenterprise.aol.com/pic.php)  (открывает новую страницу на AOL.com).</span><span class="sxs-lookup"><span data-stu-id="40b92-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="40b92-142">Сводка по поставщику общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="40b92-142">Public IM Provider Summary</span></span>

<span data-ttu-id="40b92-143">В следующей таблице приведена сводка по общедоступным поставщикам услуг обмена мгновенными сообщениями, возможностям Федерации с Lync и требованиям лицензирования.</span><span class="sxs-lookup"><span data-stu-id="40b92-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b92-144">Поставщик общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="40b92-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="40b92-145">Федеративные возможности</span><span class="sxs-lookup"><span data-stu-id="40b92-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="40b92-146">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="40b92-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b92-147">Skype</span><span class="sxs-lookup"><span data-stu-id="40b92-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="40b92-148">Обмен мгновенными сообщениями, присутствие, звук</span><span class="sxs-lookup"><span data-stu-id="40b92-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="40b92-149">Клиентские лицензии клиентского доступа Lync Server, Lync Online (план 1/2/3)</span><span class="sxs-lookup"><span data-stu-id="40b92-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b92-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="40b92-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="40b92-151">Обмен мгновенными сообщениями, присутствие, аудио и видео</span><span class="sxs-lookup"><span data-stu-id="40b92-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="40b92-152">Клиентские лицензии на Lync Server (поддерживаются, пока ВЛМ — на рынке)</span><span class="sxs-lookup"><span data-stu-id="40b92-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b92-153">ПРОГРАММУ</span><span class="sxs-lookup"><span data-stu-id="40b92-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="40b92-154">Обмен мгновенными сообщениями, присутствие</span><span class="sxs-lookup"><span data-stu-id="40b92-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="40b92-155">Клиентские лицензии клиентского доступа Lync Server; поддерживается через июнь 2014 для существующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="40b92-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b92-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="40b92-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="40b92-157">Обмен мгновенными сообщениями, присутствие</span><span class="sxs-lookup"><span data-stu-id="40b92-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="40b92-158">В дополнение к лицензиям клиентского доступа к Lync Server требуется дополнительная лицензия на подписку общедоступной службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл").</span><span class="sxs-lookup"><span data-stu-id="40b92-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="40b92-159">По прейскуранту за Сентябрь 2012 усл PIC больше не доступен для приобретения.</span><span class="sxs-lookup"><span data-stu-id="40b92-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="40b92-160">Клиенты с активными лицензиями могут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="40b92-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="40b92-161">Messenger до даты завершения работы службы до 30 июня 2014 г.</span><span class="sxs-lookup"><span data-stu-id="40b92-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
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

