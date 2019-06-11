---
title: 'Lync Server 2013: контрольный список развертывания для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5d1af-102">Контрольный список развертывания для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d1af-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d1af-103">_**Тема последнего изменения:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="5d1af-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="5d1af-104">Перед развертыванием демилитаризованной зоны и реализации поддержки внешних пользователей необходимо предварительно развернуть внутренние серверы Microsoft Lync Server 2013, включая пул переднего плана или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5d1af-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="5d1af-105">Если вы планируете развернуть дополнительные режиссеры во внутренней сети, вы также должны развернуть их перед развертыванием пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5d1af-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="5d1af-106">Подробные сведения о процессе развертывания можно найти в разделе [сценарии для режиссера в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5d1af-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="5d1af-107">Microsoft Lync Server 2013 содержит инструменты для упрощения планирования и развертывания внутренних серверов и пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5d1af-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="5d1af-108">После завершения топологии опубликуйте результирующее Определение топологии в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="5d1af-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="5d1af-109">Для этого необходимо быть членом группы **администраторов домена** и **рткуниверсалсерверадминс** .</span><span class="sxs-lookup"><span data-stu-id="5d1af-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="5d1af-110">**Средство планирования для**   Office Communications Server 2007 R2 входит средство планирования и средство планирования EDGE, с помощью которого вы сможете облегчить проектирование топологии.</span><span class="sxs-lookup"><span data-stu-id="5d1af-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="5d1af-111">В Lync Server 2010 эти два средства были объединены в единое средство планирования с дополнительными функциями и функциями, например сбор количества запланированных пользователей, требований к голосовой связи, внешних типов доступа пользователей и параметров Федерации.</span><span class="sxs-lookup"><span data-stu-id="5d1af-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="5d1af-112">Кроме того, вы можете планировать сетевые параметры инфраструктуры, такие как IP-адреса, типы подсистемы балансировки нагрузки и другие аспекты сети периметра.</span><span class="sxs-lookup"><span data-stu-id="5d1af-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="5d1af-113">\*\*\*\*   Построитель топологии Lync Server 2013 Topology Builder поможет вам определить топологию и компоненты.</span><span class="sxs-lookup"><span data-stu-id="5d1af-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="5d1af-114">Построитель топологии очень важен для развертывания серверов с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d1af-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="5d1af-115">В построителе топологии результаты публикуются в хранилище Центрального управления, которое используется для настройки всех серверов, использующих Lync Server 2013 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d1af-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="5d1af-116">Вы не можете установить Lync Server 2013 на серверы, не используя Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="5d1af-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="5d1af-117">Если вы разработали топологию пограничного сервера во время процесса планирования, в том числе запуск построителя топологии для определения пограничного топологии, вы можете использовать эти результаты, чтобы начать развертывание Edge Server.</span><span class="sxs-lookup"><span data-stu-id="5d1af-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="5d1af-118">Если вы раньше не закончите создание топологии пограничного сервера или хотите изменить ранее указанную информацию, перед продолжением процедуры развертывания необходимо завершить выполнение построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="5d1af-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="5d1af-119">Сведения о том, как создать топологию, можно найти в статьях [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5d1af-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="5d1af-120">Подробные сведения о средстве планирования и построителе топологии можно найти в разделе [Начало процесса планирования для Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5d1af-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="5d1af-121">В приведенной ниже таблице представлен обзор процесса развертывания пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="5d1af-122">Чтобы просмотреть решения для планирования, которые должны быть выполнены перед развертыванием внешнего доступа пользователей, ознакомьтесь со статьей [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5d1af-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5d1af-123">Сведения в следующей таблице посвящены новой развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5d1af-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="5d1af-124">Если вы развернули пограничные серверы в среде Lync Server 2010, Office Communications Server 2007 R2 или Office Communications Server 2007, ознакомьтесь <A href="migration.md"></A> со статьей сведения о переходе на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d1af-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="5d1af-125">Миграция не поддерживается в версиях, предшествующих Office Communications Server 2007 R2, включая Office Communications Server 2007, сервер Live Communications Server 2005 и Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="5d1af-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="5d1af-126">Для повышения производительности и безопасности пограничного сервера и для упрощения развертывания применяйте следующие рекомендации при развертывании сети периметра и пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="5d1af-127">Развертывайте пограничные серверы только после тестирования и проверки работы Lync Server 2013 внутри вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d1af-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="5d1af-128">Рекомендуется развертывать пограничные серверы в Рабочей группе, а не в домене.</span><span class="sxs-lookup"><span data-stu-id="5d1af-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="5d1af-129">Это упрощает установку и сохраняет доменные службы Active Directory (AD DS) за пределами сети периметра.</span><span class="sxs-lookup"><span data-stu-id="5d1af-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="5d1af-130">Обнаружение доменных служб Active Directory в демилитаризованной зоне может вызвать значительный риск для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5d1af-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="5d1af-131">Присоединение к пограничного сервера к домену, расположенному полностью в демилитаризованной зоне, поддерживается, но не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5d1af-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="5d1af-132">Пограничный сервер не входит в состав внутреннего домена, нарушая надежность сети, где Интернет не является надежным, сеть периметра имеет больше доверия, чем Интернет, и внутренняя сеть является наиболее надежной.</span><span class="sxs-lookup"><span data-stu-id="5d1af-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="5d1af-133">Пограничный сервер в качестве участника домена автоматически становится частью самой надежной сети, но находится в менее надежной сети (периметре).</span><span class="sxs-lookup"><span data-stu-id="5d1af-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="5d1af-134">Процесс развертывания пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="5d1af-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d1af-135">Этап</span><span class="sxs-lookup"><span data-stu-id="5d1af-135">Phase</span></span></th>
<th><span data-ttu-id="5d1af-136">Шаги</span><span class="sxs-lookup"><span data-stu-id="5d1af-136">Steps</span></span></th>
<th><span data-ttu-id="5d1af-137">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5d1af-137">Permissions</span></span></th>
<th><span data-ttu-id="5d1af-138">Документация</span><span class="sxs-lookup"><span data-stu-id="5d1af-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d1af-139">Создайте соответствующую топологию пограничного сервера и определите соответствующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="5d1af-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d1af-140">Запустите построитель топологии, чтобы настроить параметры пограничного сервера и создать и опубликовать топологию, а затем используйте командную консоль управления Lync Server для экспорта файла конфигурации топологии.</span><span class="sxs-lookup"><span data-stu-id="5d1af-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d1af-141">Группа <strong>"Администраторы домена"</strong> и группа " <strong>Рткуниверсалсерверадминс</strong> " или " <strong>ксадминс</strong> "</span><span class="sxs-lookup"><span data-stu-id="5d1af-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5d1af-142">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии требуется учетная запись, которая входит в группу <STRONG>"Администраторы домена"</STRONG> и в группу " <STRONG>рткуниверсалсерверадминс</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="5d1af-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="5d1af-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Создание топологии EDGE и Director в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d1af-144">Подготовка к установке.</span><span class="sxs-lookup"><span data-stu-id="5d1af-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5d1af-145">Убедитесь в том, что соблюдены требования к системе.</span><span class="sxs-lookup"><span data-stu-id="5d1af-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-146">Настройте IP-адреса (IPv4 и IPv6, если они используются) как для внутренних, так и для общедоступных сетевых интерфейсов на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="5d1af-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-147">Настройте внутренние и внешние записи DNS (HOST A и AAAA для IPv4 и IPv6), включая настройку DNS-суффикса на компьютере, который будет развертываться в качестве пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-148">Необязательно Создание и установка общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5d1af-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="5d1af-149">Время, необходимое для получения сертификатов, зависит от того, какой центр сертификации (ЦС) выдаст сертификат.</span><span class="sxs-lookup"><span data-stu-id="5d1af-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="5d1af-150">Если вы не выполнили этот этап на этом этапе, необходимо сделать это во время установки пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="5d1af-151">Службы пограничного сервера не могут быть запущены, пока сертификаты не будут получены и установлены.</span><span class="sxs-lookup"><span data-stu-id="5d1af-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-152">Предоставление поддержки общедоступной службы обмена мгновенными сообщениями, если развертывание предназначено для поддержки взаимодействия с Windows Live, AOL или Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5d1af-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="5d1af-153">пользователям.</span><span class="sxs-lookup"><span data-stu-id="5d1af-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5d1af-154">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="5d1af-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5d1af-155">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5d1af-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5d1af-156">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="5d1af-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="5d1af-157">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="5d1af-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5d1af-158">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="5d1af-158">has been announced.</span></span> <span data-ttu-id="5d1af-159">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5d1af-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5d1af-160">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="5d1af-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5d1af-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5d1af-161">Messenger.</span></span> <span data-ttu-id="5d1af-162">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="5d1af-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="5d1af-163">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="5d1af-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5d1af-164">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="5d1af-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5d1af-165">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="5d1af-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="5d1af-166">Предоставление поддержки КСМПП и Федерации для Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, если ваше развертывание будет использовать эти</span><span class="sxs-lookup"><span data-stu-id="5d1af-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="5d1af-167">Настройка брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="5d1af-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5d1af-168">В зависимости от вашей организации</span><span class="sxs-lookup"><span data-stu-id="5d1af-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="5d1af-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в сети периметра для Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d1af-170">Настройте обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="5d1af-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d1af-171">Настройте обратный прокси (например, для сервера Microsoft Forefront Threat Management Gateway 2010 или Microsoft Internet Security and Acceleration (ISA) с пакетом обновления 1 (SP1)) в демилитаризованной зоне, получите необходимые общедоступные сертификаты и настройте правила веб-публикации на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="5d1af-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="5d1af-172">Подготовьте обратное прокси-сервер для служб Mobility Service, если вы планируете использовать мобильность и разворачиваете службы Mobility Service в пуле переднего плана или на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5d1af-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d1af-173">Группа <strong>администраторов</strong> или обратный администратор прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5d1af-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="5d1af-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратного прокси-сервера для Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d1af-175">Настройка режиссера (необязательно).</span><span class="sxs-lookup"><span data-stu-id="5d1af-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d1af-176">Необязательно Установка и настройка одного или нескольких режиссеров во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="5d1af-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d1af-177">Группа <strong>администраторов</strong></span><span class="sxs-lookup"><span data-stu-id="5d1af-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="5d1af-178"><a href="lync-server-2013-setting-up-the-director.md">Настройка режиссера в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d1af-179">Настройте пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="5d1af-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5d1af-180">Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="5d1af-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-181">Транспортировка экспортированного файла конфигурации топологии на каждый пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="5d1af-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-182">Установите программное обеспечение Lync Server 2013 для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-183">Настройте пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="5d1af-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-184">Запросите и установите сертификаты для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-185">Запустите службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5d1af-186">Группа <strong>администраторов</strong></span><span class="sxs-lookup"><span data-stu-id="5d1af-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="5d1af-187"><a href="lync-server-2013-setting-up-edge-servers.md">Настройка пограничных серверов в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d1af-188">Настройка развертывания для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d1af-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5d1af-189">С помощью панели управления Lync Server вы можете настроить поддержку каждого из указанных ниже вариантов (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="5d1af-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="5d1af-190">Ретрансляция мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5d1af-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="5d1af-191">Маршрут Федерации</span><span class="sxs-lookup"><span data-stu-id="5d1af-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="5d1af-192">Удаленный доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="5d1af-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="5d1af-193">Интеграция с Lync Server, Office Communications Server и сервера Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="5d1af-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="5d1af-194">Подключение к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="5d1af-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="5d1af-195">КСМПП Федерация</span><span class="sxs-lookup"><span data-stu-id="5d1af-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="5d1af-196">Анонимные пользователи</span><span class="sxs-lookup"><span data-stu-id="5d1af-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="5d1af-197">Настройка учетных записей пользователей для удаленного доступа пользователей, Федерации, общедоступной службы обмена мгновенными сообщениями, КСМПП и анонимной поддержки пользователей (как применимо)</span><span class="sxs-lookup"><span data-stu-id="5d1af-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5d1af-198">Группа <strong>рткуниверсалсерверадминс</strong> или учетная запись пользователя, назначенная роли <strong>ксадминистратор</strong></span><span class="sxs-lookup"><span data-stu-id="5d1af-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="5d1af-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки внешнего доступа пользователей в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d1af-200">Проверьте конфигурацию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5d1af-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5d1af-201">Проверка подключения к серверу и репликация данных конфигурации с внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="5d1af-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-202">Убедитесь в том, что внешние пользователи могут подключаться, в том числе удаленных пользователей, пользователей в федеративных доменах, пользователей общедоступного обмена мгновенными сообщениями и анонимных пользователей в соответствии с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="5d1af-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="5d1af-203">Проверка конфигурации и связи с помощью анализатора удаленных подключений Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="5d1af-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="5d1af-204">Устранение проблем с настройкой и связью</span><span class="sxs-lookup"><span data-stu-id="5d1af-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5d1af-205">Для проверки репликации, группы <strong>рткуниверсалсерверадминс</strong> или учетной записи пользователя, назначенной роли <strong>ксадминистратор</strong></span><span class="sxs-lookup"><span data-stu-id="5d1af-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="5d1af-206">Для проверки возможности подключения пользователей к каждому типу внешних пользователей, которые поддерживаются</span><span class="sxs-lookup"><span data-stu-id="5d1af-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="5d1af-207">Удаленные пользователи</span><span class="sxs-lookup"><span data-stu-id="5d1af-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="5d1af-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Проверка развертывания пограничного сервера в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5d1af-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

