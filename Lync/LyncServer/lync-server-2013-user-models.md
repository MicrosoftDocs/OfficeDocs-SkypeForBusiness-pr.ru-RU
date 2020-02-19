---
title: 'Lync Server 2013: пользовательские модели'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca76a6b6bbe8f2cf028f063c9c1bd9d37b35b5bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="4b5f8-102">Пользовательские модели в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b5f8-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b5f8-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="4b5f8-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="4b5f8-104">Описанные здесь пользовательские модели предоставляют основу для измерений и рекомендаций по планированию мощности, описанные в статье [Планирование загрузки для Lync Server 2013 с использованием пользовательских моделей](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="4b5f8-105">Пользовательские модели Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b5f8-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="4b5f8-106">В следующей таблице описывается пользовательская модель для регистрации, контактов, обмена мгновенными сообщениями и сведений о присутствии для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="4b5f8-107">Пользовательская модель среды и регистрации</span><span class="sxs-lookup"><span data-stu-id="4b5f8-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-108">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-108">Category</span></span></th>
<th><span data-ttu-id="4b5f8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-110">Размер и распределение развертывания</span><span class="sxs-lookup"><span data-stu-id="4b5f8-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-111">Мы моделируем большое развертывание с тремя центральными сайтами и с одним интерфейсным пулом на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-112">Процент пользователей Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b5f8-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-113">Мы предполагаем, что 70% всех пользователей Active Directory в организации включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="4b5f8-114">80% от этих включенных пользователей каждый день входа в Lync Server (80% параллелизма).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="4b5f8-115">На основе количества параллельных пользователей рассчитываются числа в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-116">Изменения Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b5f8-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-117">Мы предполагаем, что 0,5% от общего числа пользователей создаются и включены для Lync в Active Directory каждую неделю, и что 0,5% от общего числа пользователей отключены в Active Directory и Lync каждую неделю.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="4b5f8-118">Для 5% пользователей каждую неделю изменяется по крайней мере один атрибут Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-119">Группы рассылки Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b5f8-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p103">Мы предполагаем, что число групп рассылки Active Directory в организации втрое больше количества всех пользователей в Active Directory. Эти группы рассылки имеют следующие размеры:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-122">64% имеют от 2 до 30 пользователей;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-123">13% имеют от 31 до 50 пользователей;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-124">10% имеют от 51 до 100 пользователей;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-125">13% имеют от 101 до 500 пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-126">Пользователи протокола VoIP</span><span class="sxs-lookup"><span data-stu-id="4b5f8-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-127">60% пользователей Lync Server включены для объединенных коммуникаций (UC) (то есть их номера телефонов принадлежат Lync Server).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-128">Распределение зарегистрированных клиентов</span><span class="sxs-lookup"><span data-stu-id="4b5f8-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-129">65% клиентов запустите программное обеспечение Lync 2013, включая Lync и Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="4b5f8-130">30% клиентов с клиентским программным обеспечением из предыдущей версии Lync.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="4b5f8-131">5% клиентов, использующих Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="4b5f8-132">Если мобильность включена, то мы предполагаем, что 40% пользователей одновременно используют мобильную систему с другими вышеупомянутыми зарегистрированными параметрами клиента.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="4b5f8-133">В этом случае процентное отношение числа клиентов для нескольких точек присутствия (МПОП) составляет 1:1,9.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="4b5f8-134">Если мобильность отключена, то коэффициент MPOP составляет 1:1,5.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-135">Распределение удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="4b5f8-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-136">70% пользователей подключается внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="4b5f8-137">30% пользователей подключается через пограничный сервер и Директор.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-138">Распределение контактов</span><span class="sxs-lookup"><span data-stu-id="4b5f8-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p105">Пользователь имеет не более 1000 контактов. Менее 1% пользователей имеет 1000 контактов. Менее 25% пользователей имеет как минимум 100 контактов.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="4b5f8-p106">Пользователи с подключением к общедоступному облаку в среднем имеют по 80 контактов. Для этих пользователей:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-p107">50% контактов находятся внутри организации; 10% пользователей являются удаленными, подключающимися извне через брандмауэр;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-146">40% контактов являются пользователями общедоступного облака (например, пользователями AOL, Yahoo!, MSN или Google Talk);</span><span class="sxs-lookup"><span data-stu-id="4b5f8-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-147">10% контактов приходятся на федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4b5f8-148">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4b5f8-149">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4b5f8-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4b5f8-150">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="4b5f8-151">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4b5f8-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4b5f8-152">объявлено.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-152">has been announced.</span></span> <span data-ttu-id="4b5f8-153">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="4b5f8-154">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4b5f8-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4b5f8-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-155">Messenger.</span></span> <span data-ttu-id="4b5f8-156">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="4b5f8-157">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4b5f8-158">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4b5f8-159">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="4b5f8-p111">Пользователи без возможности подключения к общедоступному облаку в среднем имеют по 50 контактов. Для этих пользователей:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-p112">80% контактов находятся внутри организации; 10% пользователей являются удаленными, подключающимися извне через брандмауэр;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-164">20% контактов приходятся на федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="4b5f8-p113">Каждый пользователь имеет одну группу рассылки в своем списке контактов. Для тестирования производительности мы предполагаем, что группы рассылки всегда расширенные.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="4b5f8-167">25% контактов пользователей используют XMPP.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-168">Время сеанса</span><span class="sxs-lookup"><span data-stu-id="4b5f8-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p114">Среднее время сеанса входа пользователя в систему составляет 12 часов. Все пользователи выполняют вход в течение 120 минут после начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="4b5f8-171">Пользовательская модель обмена мгновенными сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="4b5f8-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-172">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-172">Category</span></span></th>
<th><span data-ttu-id="4b5f8-173">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-174">Одноранговые сеансы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="4b5f8-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-175">Каждый пользователь в среднем имеет по шесть одноранговых сеансов обмена мгновенными сообщениями в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="4b5f8-176">10 мгновенных сообщений на сеанс.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="4b5f8-177">Каждое сообщение сравнивается с двумя ИНФОРМАЦИОНными сообщениями SIP и 2 сообщениями SIP 200 ОК (для индикаторов состояния,&lt;таких&gt; как "имя вводит")</span><span class="sxs-lookup"><span data-stu-id="4b5f8-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-178">Опрос присутствия</span><span class="sxs-lookup"><span data-stu-id="4b5f8-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p115">В основном для опроса присутствия мы предполагаем по 60 опросов на каждого пользователя в час. Для каждого пользователя предполагаются следующие средние значения.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-p116">Один опрос в день присутствия пользователей со вкладки "Организация" пользователя (но не из списка контактов). В среднем на вкладке "Организация" пользователя имеется 15 пользователей, не являющихся контактами. В день выполняется две операции просмотра карточки контакта.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-184">Оценивается, что один опрос присутствия каждый раз, когда пользователь щелкает другого пользователя для начала беседы, выполняется раз в час.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-p117">Выполняется по шесть поисков пользователей в час. При каждом выполнении поиска пакетный опрос отправляется каждому в списке результатов поиска. Мы предполагаем, что средний размер результатов поиска — 20. Если результаты поиска остаются на экране, то пакетный опрос обновляется каждые 5 минут; мы предполагаем, что будет два таких обновления в час.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-189">Когда пользователь открывает или предварительно просматривает электронное письмо в Outlook, выполняется опрос присутствия пользователей, указанных в полях "Кому" и "Копия". Оценивается, что просматривается по пять электронных писем в час, и в каждом письме указывается по пять пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-190">Подписки на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="4b5f8-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p118">Когда пользователь добавляет другого пользователя в качестве контакта, он <em>подписывается</em> на пять категорий сведений об этом пользователе. Обновления этих категорий сведений автоматически отправляются первому пользователю.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="4b5f8-193">Для каждого клиента отправляется один пакетный запрос подписки, чтобы получить сведения о присутствии в среднем 40 контактов, с дополнительными 40 диалогами, чтобы получить сведения о присутствии для федеративных контактов.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="4b5f8-194">Сведения о присутствии для членов расширенной группы рассылки извлекаются с помощью постоянных подписок на сведения о присутствии, а не опросов, и моделируются как 1 расширение на пользователя каждые 2 часа.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="4b5f8-p119"><em>Краткие подписки</em> происходят, когда пользователь входит, выполняется пакетная подписка для всех контактов этого пользователя, и вскоре он выходит. Мы предполагаем 6 кратких подписок на пользователя в час, при этом каждая подписка продолжается 10 минут.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-197">Публикация сведений о присутствии</span><span class="sxs-lookup"><span data-stu-id="4b5f8-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-198">Состояние присутствия публикуется в среднем 4 раза на пользователя в час, максимально 6 раз на пользователя в час.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-199">Размер документа сведений о присутствии</span><span class="sxs-lookup"><span data-stu-id="4b5f8-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-200">Средний размер полного документа сведений о присутствии оценивается в 4 КБ, максимальный размер — 25 КБ.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-201">В следующей таблице описывается пользовательская модель для использования адресной книги.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="4b5f8-202">Пользовательская модель использования адресной книги</span><span class="sxs-lookup"><span data-stu-id="4b5f8-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-203">Режим поиска в адресной книге</span><span class="sxs-lookup"><span data-stu-id="4b5f8-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="4b5f8-204">Применение</span><span class="sxs-lookup"><span data-stu-id="4b5f8-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-205">Только веб-запрос к адресной книге (все запросы выполняются службой веб-запросов к адресной книге)</span><span class="sxs-lookup"><span data-stu-id="4b5f8-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-206">Четыре запроса префикса на пользователя в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="4b5f8-p120">60 запросов точного поиска на пользователя в день. 40% этих запросов являются пакетными, имеющими в среднем по 20 контактов на запрос. Остальные 60% запросов имеют по одному контакту.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="4b5f8-p121">25 запросов фотографий на пользователя в день. 24 являются запросами одной фотографии, один является пакетным запросом, в среднем имеющим 20 контактов.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="4b5f8-212">Один запрос поиска по всей организации на пользователя в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-p122">Смешанный режим, в котором используются как файл адресной книги, так и веб-запросы. Это режим по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-215">В сеть приходят только два типа запросов: запрос фотографий и запрос поиска по всей организации.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="4b5f8-p123">25 запросов фотографий на пользователя в день. 24 являются запросами одной фотографии, один является пакетным запросом, в среднем имеющим 20 контактов.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="4b5f8-218">Один запрос поиска по всей организации на пользователя в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-219">В следующей таблице описывается модель конференций.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="4b5f8-220">Модель конференций</span><span class="sxs-lookup"><span data-stu-id="4b5f8-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-221">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-221">Category</span></span></th>
<th><span data-ttu-id="4b5f8-222">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-223">Запланированные собрания &quot;по сравнению с собранием в настоящее время&quot;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-224">60% запланированных, 40% незапланированных.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="4b5f8-225">Мы предполагаем, что среди запланированных собраний 80% составляют назначенные конференции, которые являются случаями повторяющихся конференций; 10% составляют однократные открытые собрания, 8% составляют однократные анонимные собрания и 2% составляют однократные закрытые собрания.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-226">Распределение клиентов конференций</span><span class="sxs-lookup"><span data-stu-id="4b5f8-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-227">Для запланированных собраний:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-228">65% пользователей конференц-связи используют Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-229">5% пользователей конференций используют Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-230">30% пользователей конференц-связи используют более ранние клиенты, в том числе Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 и Microsoft Office Communicator Web Access (выпуск 2007).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="4b5f8-231">Для незапланированных собраний:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b5f8-232">70% пользователей конференц-связи используют Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-233">30% пользователей конференц-связи используют более ранние клиенты, в том числе Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 и Microsoft Office Communicator Web Access (выпуск 2007).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-234">Параллелизм собраний</span><span class="sxs-lookup"><span data-stu-id="4b5f8-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p124">5% пользователей будут принимать участие в конференциях в рабочее время. Следовательно, в пуле из 80 000 пользователей в любое время могут принимать участие в конференции 4 000 пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-237">Распределение собраний по использованию звука</span><span class="sxs-lookup"><span data-stu-id="4b5f8-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-238">40% смешанных конференций, использующих звук по протоколу VoIP и по телефонному подключению, с отношением 3:1 пользователей протокола VoIP к пользователям с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="4b5f8-239">35% конференций только со звуком по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="4b5f8-240">15% конференций только со звуком по телефонному подключению.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="4b5f8-241">10% конференций без звука (конференции только с обменом мгновенными сообщениями, в среднем по пять отправленных сообщений на пользователя).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-242">Комбинирование средств представления для конференций</span><span class="sxs-lookup"><span data-stu-id="4b5f8-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-243">75% конференций являются веб-конференциями, включающими звук и некоторые другие способы совместной работы.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="4b5f8-244">Для таких конференций другие способы совместной работы используются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4b5f8-245">Эти значения добавляют более 100%, поскольку в одной конференции может использоваться несколько способов совместной работы.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="4b5f8-p125">50% добавляет общий доступ к приложениям. Мы предполагаем, что один пользователь отправляет данные с максимальной скоростью 1,1 МБ в секунду.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-248">50% вносит обмен мгновенными сообщениями (в среднем по 2 сообщения на пользователя).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-p126">20% добавляет совместная работа с данными, включая использование PowerPoint или доски. Мы предполагаем, что в каждой конференции представляется 2 файла PowerPoint со средним размером в 10 МБ (без внедренного видео) или 30 МБ (с внедренным видео). В среднем используется 20 заметок на доску.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-p127">20% добавляет видео. Для 70% из этих пользователей включена поддержка видео MultiView, и каждый пользователь получает 2-3 видеопотока.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="4b5f8-253">15% добавляют общие заметки.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-254">Распределение участников собраний</span><span class="sxs-lookup"><span data-stu-id="4b5f8-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-255">50% внутренних, прошедших проверку пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="4b5f8-256">25% удаленных, прошедших проверку пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="4b5f8-257">15% анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="4b5f8-258">10% федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-259">Распределение присоединений к собраниям</span><span class="sxs-lookup"><span data-stu-id="4b5f8-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-260">Моделируется присоединение пользователей к собраниям в течение первых 5 минут.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-261">В обычных интерфейсных пулах Lync Server 2013 имеет максимальный поддерживаемый размер собрания 250 пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="4b5f8-262">В каждом пуле в каждый момент времени может быть размещено одно собрание в 250 пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="4b5f8-263">Во время проведения такого большого собрания в пуле также могут размещаться другие небольшие конференции.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="4b5f8-264">Кроме того, можно поддерживать собрания до 1000 пользователей, настраивая выделенный пул для размещения таких собраний.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="4b5f8-265">Дополнительные сведения см [в разделе Поддержка больших собраний в Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="4b5f8-266">Конференции моделировались следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="4b5f8-267">85% конференций имели четырех участников;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="4b5f8-268">10% конференций имели шесть участников;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="4b5f8-269">5% конференций имели одиннадцать участников;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="4b5f8-270">одна большая конференция с 250 участниками.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-270">One large conference of 250 users.</span></span>

<span data-ttu-id="4b5f8-271">В следующей таблице приводятся подробные сведения о пользовательской модели конференций, в которых участвовали пользователи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="4b5f8-272">Пользовательская модель конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="4b5f8-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-273">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-273">Category</span></span></th>
<th><span data-ttu-id="4b5f8-274">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-275">Прошедший проверку подлинности и анонимный доступ</span><span class="sxs-lookup"><span data-stu-id="4b5f8-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p129">70% участников присоединяются как анонимные, и им предлагается указать записанное имя. 30% присоединяются как прошедшие проверку пользователи.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-278">Продолжительность вызова и музыка при удержании</span><span class="sxs-lookup"><span data-stu-id="4b5f8-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-279">Средняя продолжительность вызова без воспроизведения музыки при удержании: 50 секунд.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="4b5f8-280">50% звонящих пользователей прослушивают музыку при удержании в среднем 5 минут.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-281">Двухтональный многочастотный набор (DTMF)</span><span class="sxs-lookup"><span data-stu-id="4b5f8-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p130">15% конференций с подключением по телефону имеют ведущих по телефону. 10% смешанных конференций, включающих пользователей с телефонным подключением, также имеют ведущих по телефону.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="4b5f8-284">20% ведущих по телефону используют по 2 команды DTMF на конференцию.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-285">Языки оповещений</span><span class="sxs-lookup"><span data-stu-id="4b5f8-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-286">При моделировании в качестве языка оповещений использовался английский.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-287">В следующей таблице предоставляются сведения по пользовательской модели "залов ожидания" конференций.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="4b5f8-288">Пользовательская модель "залов ожидания" конференций</span><span class="sxs-lookup"><span data-stu-id="4b5f8-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-289">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-289">Category</span></span></th>
<th><span data-ttu-id="4b5f8-290">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-291">Количество пользователей в "зале ожидания"</span><span class="sxs-lookup"><span data-stu-id="4b5f8-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-292">5% пользователей с телефонным подключением и 25% других пользователей проходят через "зал ожидания"</span><span class="sxs-lookup"><span data-stu-id="4b5f8-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-293">Приглашение из "зала ожидания"</span><span class="sxs-lookup"><span data-stu-id="4b5f8-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-294">При моделировании все пользователи приглашались выступающим до истечения времени ожидания клиента.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-295">В следующей таблице описывается пользовательская модель для прочих одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="4b5f8-296">Пользовательская модель одноранговых сеансов</span><span class="sxs-lookup"><span data-stu-id="4b5f8-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-297">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-297">Category</span></span></th>
<th><span data-ttu-id="4b5f8-298">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-299">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="4b5f8-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-300">Каждый пользователь участвует в 5 одноранговых сеансах общего доступа к приложениям в месяц, в среднем по 0,25 сеанса в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-301">Передача файлов</span><span class="sxs-lookup"><span data-stu-id="4b5f8-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-p131">Каждый пользователь участвует в 1 одноранговом сеансе передачи файлов в месяц (в качестве части сеанса обмена мгновенными сообщениями), в среднем по 0.05 сеанса в день. Средний размер передаваемого файла в сеансе составляет 1 МБ.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b5f8-304">В следующей таблице описывается пользовательская модель для политик.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="4b5f8-305">Пользовательская модель политик</span><span class="sxs-lookup"><span data-stu-id="4b5f8-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b5f8-306">Категория</span><span class="sxs-lookup"><span data-stu-id="4b5f8-306">Category</span></span></th>
<th><span data-ttu-id="4b5f8-307">Описание</span><span class="sxs-lookup"><span data-stu-id="4b5f8-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b5f8-308">Политики конференц-связи, присутствия и архивации</span><span class="sxs-lookup"><span data-stu-id="4b5f8-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-309">Мы предполагаем, что существует одна глобальная политика, 10 помеченных политик конференц-связи, 4 политики архивации и 10 помеченных политик присутствия.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b5f8-310">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4b5f8-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="4b5f8-311">Мы предполагаем, что существует одна глобальная политика и по 2 помеченные политики на сайт.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="4b5f8-312">100% сайтов имеют политику сайта, и 30% пользователей имеют назначенную политику на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="4b5f8-313">Мы предполагаем также по одной абонентской группе и по два маршрута на сайт.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="4b5f8-314">Период максимальной нагрузки</span><span class="sxs-lookup"><span data-stu-id="4b5f8-314">Busy Hour</span></span>

<span data-ttu-id="4b5f8-p133">Для одноранговых сеансов пиковая нагрузка вычисляется с помощью попыток вызовов в час наибольшей нагрузки (BHCA). Этот термин из сферы голосовой связи предполагает, что 50% всех вызовов в день будут выполняться в 20% времени. Это значение вычисляется по следующей формуле:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="4b5f8-318">При тестировании производительности период максимальной нагрузки моделируется путем запуска сеансов VoIP и других одноранговых сеансов с уровнем максимальной нагрузки по крайней мере 1,6 часов в день.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="4b5f8-p134">Пиковая нагрузка конференц-связи предполагает, что 75% всех конференций для восьмичасового дня происходит в 4 часа максимальной нагрузки. В эти часы нагрузка в полтора раза выше средней нагрузки конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="4b5f8-321">Звонки из корпоративной голосовой сети в PSTN</span><span class="sxs-lookup"><span data-stu-id="4b5f8-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="4b5f8-322">Приведенные ниже предположения применимы к голосовым вызовам предприятия.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="4b5f8-323">50% пользователей разрешено использовать корпоративную голосовую связь, а 60% этих пользователей разрешено звонить по PSTN.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="4b5f8-p135">Каждый из пользователей, которым разрешены звонки в ТСОП, выполняет 4 звонка в ТСОП в течение часов максимальной нагрузки. Каждый звонок длится 3 минуты.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="4b5f8-326">В 65% этих голосовых звонков в ТСОП используется обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="4b5f8-327">Мобильность</span><span class="sxs-lookup"><span data-stu-id="4b5f8-327">Mobility</span></span>

<span data-ttu-id="4b5f8-p136">Предполагается. что для 40% зарегистрированных пользователей включена поддержка мобильности. Для каждого из пользователей с поддержкой мобильности предполагается, что использование мобильного клиента является дополнительным к использованию других экземпляров MPOP для этого пользователя, за исключением взаимодействий в конференциях, в которых мобильный клиент является просто еще одним типом клиента, используемым для участия в конференциях.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="4b5f8-330">Сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="4b5f8-330">Persistent Chat</span></span>

<span data-ttu-id="4b5f8-331">Мы предполагаем, что 25% зарегистрированных пользователей будут принимать участие в сеансах сохраняемого чата со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="4b5f8-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="4b5f8-332">в среднем по 1,5 комнат чата на пользователя;</span><span class="sxs-lookup"><span data-stu-id="4b5f8-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="4b5f8-333">каждая комната чата приводит к выполнению 12 запросов опроса в час, и каждый из опросов в среднем выполняется для 10 пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="4b5f8-334">Группа ответа и парковка вызовов</span><span class="sxs-lookup"><span data-stu-id="4b5f8-334">Response Group and Call Park</span></span>

<span data-ttu-id="4b5f8-p137">Мы предполагаем, что 0,15% зарегистрированных пользователей входят в группы ответа. Мы также предполагаем, что в каждый момент времени 0,02% зарегистрированных пользователей имеют запаркованные вызовы.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

