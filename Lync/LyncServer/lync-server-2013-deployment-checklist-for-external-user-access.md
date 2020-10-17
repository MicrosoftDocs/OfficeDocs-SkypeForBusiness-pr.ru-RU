---
title: 'Lync Server 2013: контрольный список развертывания для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010d4437f2eb90d596ace15cc392690dba5544d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522776"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="8133c-102">Контрольный список развертывания для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8133c-102">Deployment checklist for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8133c-103">_**Последнее изменение темы:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="8133c-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="8133c-104">Перед развертыванием сети периметра и реализации поддержки внешних пользователей необходимо предварительно развернуть внутренние серверы Microsoft Lync Server 2013, в том числе интерфейсный пул или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8133c-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="8133c-105">Если вы планируете развернуть дополнительных директоров во внутренней сети, вам также следует развернуть их перед развертыванием пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8133c-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="8133c-106">Для получения дополнительных сведений о процессе развертывания режиссера обратитесь к разделу [сценарии для директора в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="8133c-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="8133c-107">Microsoft Lync Server 2013 содержит средства для упрощения планирования и развертывания внутренних серверов и пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8133c-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="8133c-108">После завершения работы над топологией опубликуйте полученное определение топологии в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8133c-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="8133c-109">Для этого вам следует быть членом группы **Администраторы домена** и группы **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="8133c-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="8133c-110">**Средство планирования**     Office Communications Server 2007 R2 включает средство планирования и средство пограничного планирования, которые можно использовать для руководства по проектированию топологии.</span><span class="sxs-lookup"><span data-stu-id="8133c-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="8133c-111">В Lync Server 2010 эти два средства были объединены в одно средство планирования с дополнительными функциями и функциями, такими как сбор запланированных пользователей, требования к голосовой связи, типы доступа внешних пользователей и параметры Федерации.</span><span class="sxs-lookup"><span data-stu-id="8133c-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="8133c-112">Кроме того, вы можете планировать параметры сети свой инфраструктуры, такие как IP-адреса, типы подсистемы балансировки нагрузки и другие характеристики сети периметра.</span><span class="sxs-lookup"><span data-stu-id="8133c-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="8133c-113">Построитель топологий **Topology Builder**     Lync Server 2013 Topology Builder помогает определить топологию и компоненты.</span><span class="sxs-lookup"><span data-stu-id="8133c-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="8133c-114">Построитель топологии очень важен для развертывания серверов, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8133c-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="8133c-115">Построитель топологий публикует результаты в хранилище центрального хранилища управления, которое используется для настройки всех серверов, на которых работает Lync Server 2013 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8133c-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="8133c-116">Невозможно установить Lync Server 2013 на серверах без использования построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="8133c-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="8133c-117">Если вы разработали пограничную топологию во время процесса планирования, включая запуск построителя топологий для определения пограничной топологии, вы можете использовать эти результаты для запуска развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8133c-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="8133c-118">Если вы раньше не закончили создание пограничной топологии или хотите изменить ранее указанную информацию, необходимо завершить работу построителя топологий перед выполнением других этапов развертывания.</span><span class="sxs-lookup"><span data-stu-id="8133c-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="8133c-119">Сведения о том, как создать топологию, можно найти [в статье сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8133c-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="8133c-120">Подробнее о средстве планирования и построителе топологий можно узнать в статье [Начало процесса планирования для Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="8133c-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="8133c-121">В следующей таблице приведен обзор процесса развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8133c-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="8133c-122">Чтобы просмотреть решения по планированию, которые необходимо выполнить перед развертыванием доступа внешних пользователей, ознакомьтесь со статьей [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8133c-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8133c-123">Информация в следующей таблице ориентирована на новое развертывание.</span><span class="sxs-lookup"><span data-stu-id="8133c-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="8133c-124">Если вы развернули пограничные серверы в среде Lync Server 2010, Office Communications Server 2007 R2 или Office Communications Server 2007, ознакомьтесь со статьей <A href="migration.md">миграции</A> для получения сведений о переходе на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8133c-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="8133c-125">Миграция не поддерживается в версиях, предшествующих Office Communications Server 2007 R2, в том числе Office Communications Server 2007, Live Communications Server 2005 и Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8133c-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="8133c-126">Чтобы повысить уровень производительности и безопасности пограничного сервера и упростить его развертывание, воспользуйтесь следующими рекомендациями при развертывании сети периметра и пограничных серверов:</span><span class="sxs-lookup"><span data-stu-id="8133c-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="8133c-127">Развертывайте пограничные серверы только после тестирования и проверки работы Lync Server 2013 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8133c-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="8133c-p108">Мы рекомендуем развертывать пограничные серверы в рабочей группе, а не в домене. Это упрощает установку и выносит доменные службы Active Directory (AD DS) за пределы сети периметра. Расположение служб AD DS в сети периметра может создавать серьезную угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="8133c-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="8133c-p109">Присоединение пограничного сервера к домену, полностью расположенному в сети периметра, поддерживается, но не рекомендуется. Являясь частью внутреннего домена, пограничный сервер нарушает границы доверенной сети, где Интернет имеет наименьший уровень доверия, сеть периметра имеет уровень доверия выше, чем у Интернета, а внутренняя сеть является наиболее доверенной. Пограничный сервер, являясь членом домена, автоматически становится частью наиболее доверенной сети, хотя располагается в наименее доверенной сети (сети периметра).</span><span class="sxs-lookup"><span data-stu-id="8133c-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="8133c-134">Процесс развертывания для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="8133c-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8133c-135">Этап</span><span class="sxs-lookup"><span data-stu-id="8133c-135">Phase</span></span></th>
<th><span data-ttu-id="8133c-136">Действия</span><span class="sxs-lookup"><span data-stu-id="8133c-136">Steps</span></span></th>
<th><span data-ttu-id="8133c-137">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8133c-137">Permissions</span></span></th>
<th><span data-ttu-id="8133c-138">Документация</span><span class="sxs-lookup"><span data-stu-id="8133c-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8133c-139">Создайте подходящую пограничную топологию и определите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="8133c-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8133c-140">Запустите построитель топологий, чтобы настроить параметры пограничного сервера и создать и опубликовать топологию, а затем с помощью командной консоли Lync Server экспортировать файл конфигурации топологии.</span><span class="sxs-lookup"><span data-stu-id="8133c-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8133c-141">Группа <strong>администраторов домена</strong> и группа <strong>RTCUniversalServerAdmins</strong> или <strong>ксадминс</strong></span><span class="sxs-lookup"><span data-stu-id="8133c-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8133c-142">Вы можете определить топологию с помощью учетной записи, являющейся членом группы локальных пользователей, однако для публикации топологии требуется учетная запись, которая является членом группы <STRONG>Администраторы домена</STRONG> и группы <STRONG>RTCUniversalServerAdmins</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8133c-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="8133c-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Создание топологии пограничных серверов и директоров в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8133c-144">Подготовьтесь к установке.</span><span class="sxs-lookup"><span data-stu-id="8133c-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8133c-145">Убедитесь, что для системы выполнены необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="8133c-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="8133c-146">Настройте IP-адреса для внутреннего и общедоступного сетевых интерфейсов на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8133c-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8133c-147">Настройте внутренние и внешние DNS-записи, включая задание DNS-суффикса на компьютере, развертываемом в качестве пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8133c-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8133c-p110">(Необязательно) Создайте и установите общие сертификаты. Время, требуемое на получение сертификатов, зависит от центра сертификации (ЦС), выдавшего сертификат. Если вы не выполняете этот шаг на данном этапе, вам следует выполнить его во время установки пограничного сервера. Службы пограничного сервера можно запустить только после получения и установки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8133c-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="8133c-p111">Обеспечьте поддержку возможности подключения к общим службам обмена мгновенными сообщениями, если ваше развертывание должно поддерживать коммуникации с пользователями Windows Live, AOL или Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="8133c-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8133c-154">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="8133c-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8133c-155">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8133c-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8133c-156">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="8133c-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="8133c-157">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8133c-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8133c-158">объявлено.</span><span class="sxs-lookup"><span data-stu-id="8133c-158">has been announced.</span></span> <span data-ttu-id="8133c-159">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8133c-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8133c-160">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8133c-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8133c-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8133c-161">Messenger.</span></span> <span data-ttu-id="8133c-162">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="8133c-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="8133c-163">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="8133c-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8133c-164">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="8133c-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8133c-165">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="8133c-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="8133c-166">Подготовка поддержки XMPP и Федерации для Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 партнеров, если ваше развертывание будет использовать эти</span><span class="sxs-lookup"><span data-stu-id="8133c-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="8133c-167">Настройте брандмауэры.</span><span class="sxs-lookup"><span data-stu-id="8133c-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8133c-168">Подходящим для организации образом</span><span class="sxs-lookup"><span data-stu-id="8133c-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="8133c-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в сети периметра для Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8133c-170">Настройте обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="8133c-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8133c-171">Настройка обратного прокси-сервера (например, для Microsoft Forefront Threat Management Gateway 2010 или Microsoft Internet Security and Acceleration (ISA) Server с пакетом обновления 1 (SP1)) в сети периметра, получение необходимых общедоступных сертификатов и настройка правил веб-публикации на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="8133c-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="8133c-172">Подготовьте обратный прокси-сервер для служб мобильности, если вы запланировали такие службы и развертываете их в интерфейсном пуле или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8133c-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8133c-173">Группа <strong>Администраторы</strong> или администратор обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8133c-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="8133c-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8133c-175">Настройте Директор (необязательно).</span><span class="sxs-lookup"><span data-stu-id="8133c-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8133c-176">(Необязательно) Установите и настройте один или несколько Директоров во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="8133c-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8133c-177">Группа <strong>Администраторы</strong></span><span class="sxs-lookup"><span data-stu-id="8133c-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="8133c-178"><a href="lync-server-2013-setting-up-the-director.md">Настройка директора в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8133c-179">Задайте пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="8133c-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8133c-180">Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="8133c-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="8133c-181">Перенесите экспортированный файл конфигурации топологии на каждый из пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8133c-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8133c-182">Установите программное обеспечение Lync Server 2013 на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8133c-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8133c-183">Настройте пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="8133c-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="8133c-184">Запросите и установите сертификаты на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8133c-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8133c-185">Запустите службы пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="8133c-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8133c-186">Группа <strong>Администраторы</strong></span><span class="sxs-lookup"><span data-stu-id="8133c-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="8133c-187"><a href="lync-server-2013-setting-up-edge-servers.md">Настройка пограничных серверов в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8133c-188">Настройте развертывание для внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="8133c-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8133c-189">Используйте панель управления Lync Server, чтобы настроить поддержку для каждого из следующих компонентов (при необходимости):</span><span class="sxs-lookup"><span data-stu-id="8133c-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="8133c-190">Ретрансляция мультимедиа</span><span class="sxs-lookup"><span data-stu-id="8133c-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="8133c-191">Федеративный маршрут</span><span class="sxs-lookup"><span data-stu-id="8133c-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="8133c-192">Доступ удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="8133c-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="8133c-193">Федерация с Lync Server, Office Communications Server и сервером Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="8133c-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="8133c-194">Возможность подключения к общедоступным службам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8133c-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="8133c-195">Федерация XMPP</span><span class="sxs-lookup"><span data-stu-id="8133c-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="8133c-196">Анонимные пользователи</span><span class="sxs-lookup"><span data-stu-id="8133c-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="8133c-197">Настройте учетные записи пользователей для поддержки доступа удаленных пользователей, федерации, возможности подключения к общедоступным службам обмена мгновенными сообщениями, XMPP и анонимных пользователей (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="8133c-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8133c-198">Группа <strong>RTCUniversalServerAdmins</strong> или учетная запись пользователя, назначенная роли <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="8133c-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="8133c-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки доступа внешних пользователей в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8133c-200">Проверьте конфигурацию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8133c-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8133c-201">Проверьте возможность подключения сервера и репликацию данных конфигурации с внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="8133c-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="8133c-202">Убедитесь, что внешние пользователи, включая удаленных пользователей, пользователей в федеративных доменах, пользователей общедоступных служб обмена мгновенными сообщениями и анонимных пользователей, могут установить соединение в соответствии с потребностями вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8133c-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="8133c-203">Проверка конфигурации и связи с помощью анализатора удаленных подключений Lync Server <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="8133c-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="8133c-204">Произведите диагностику проблем с конфигурацией и взаимодействием (ССЫЛКА НА РАЗДЕЛЫ, ПОСВЯЩЕННЫЕ ДИАГНОСТИКЕ)</span><span class="sxs-lookup"><span data-stu-id="8133c-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8133c-205">Для проверки репликации — группа <strong>RTCUniversalServerAdmins</strong> или учетная запись пользователя, назначенная роли <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="8133c-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="8133c-206">Для проверки взаимодействия пользователей — пользователь для каждого поддерживаемого типа доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8133c-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="8133c-207">Удаленные пользователи</span><span class="sxs-lookup"><span data-stu-id="8133c-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="8133c-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Проверка развертывания пограничного сервера в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8133c-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

