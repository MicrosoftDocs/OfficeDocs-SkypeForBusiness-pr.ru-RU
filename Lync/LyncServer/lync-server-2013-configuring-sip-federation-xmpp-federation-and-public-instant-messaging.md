---
title: Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21f2c094eb7b5c342c31387b6732a2565f01197
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e761e-102">Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e761e-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e761e-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="e761e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="e761e-104">Федерация, подключения к общедоступным службам обмена мгновенными сообщениями и протокол XMPP обуславливают появление нового типа внешних пользователей — федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e761e-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="e761e-105">Пользователи федеративного развертывания Lync Server или развертывания XMPP имеют доступ к ограниченному набору служб и проходят проверку подлинности с помощью внешнего развертывания.</span><span class="sxs-lookup"><span data-stu-id="e761e-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="e761e-106">Удаленные пользователи являются участниками развертывания Lync Server и имеют доступ ко всем службам, предлагаемым вашим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="e761e-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e761e-107">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e761e-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="e761e-108">объявлено.</span><span class="sxs-lookup"><span data-stu-id="e761e-108">has been announced.</span></span> <span data-ttu-id="e761e-109">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e761e-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e761e-110">Общедоступная служба обмена мгновенными сообщениями — это особый тип Федерации, позволяющий клиенту Lync Server получать доступ к настроенным партнерам общедоступной службы обмена мгновенными сообщениями с помощью Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e761e-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="e761e-111">В настоящее время доступны следующие партнерские службы:</span><span class="sxs-lookup"><span data-stu-id="e761e-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="e761e-112">America Online</span><span class="sxs-lookup"><span data-stu-id="e761e-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="e761e-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="e761e-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="e761e-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="e761e-114">Yahoo\!</span></span>

<span data-ttu-id="e761e-115">Конфигурация подключений к общедоступным службам обмена мгновенными сообщениями обеспечивает следующие возможности связи для пользователей Lync:</span><span class="sxs-lookup"><span data-stu-id="e761e-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="e761e-116">Обмен мгновенными сообщениями и сведениями о присутствии</span><span class="sxs-lookup"><span data-stu-id="e761e-116">IM and Presence</span></span>

  - <span data-ttu-id="e761e-117">возможность просмотра контактов общедоступной службы обмена мгновенными сообщениями в клиенте Lync;</span><span class="sxs-lookup"><span data-stu-id="e761e-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="e761e-118">двусторонние текстовые беседы с контактами;</span><span class="sxs-lookup"><span data-stu-id="e761e-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="e761e-119">звуковые и видеозвонки пользователям Windows Live.</span><span class="sxs-lookup"><span data-stu-id="e761e-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="e761e-p104">Федерация Lync Server предусматривает наличие соглашения о взаимодействии между вашим развертыванием Lync Server и другими развертываниями Office Communications Server 2007 R2 или Lync Server. Федеративная конфигурация Lync Server обеспечивает следующие возможности связи пользователей Lync с федеративными пользователями:</span><span class="sxs-lookup"><span data-stu-id="e761e-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="e761e-122">обмен мгновенными сообщениями и сведениями о присутствии;</span><span class="sxs-lookup"><span data-stu-id="e761e-122">IM and Presence</span></span>

  - <span data-ttu-id="e761e-123">создание федеративных контактов в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="e761e-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="e761e-p105">Федерация XMPP предусматривает наличие внешнего развертывания на основе протокола XMPP. Конфигурация XMPP обеспечивает следующие возможности связи пользователей Lync с разрешенными пользователями домена XMPP:</span><span class="sxs-lookup"><span data-stu-id="e761e-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="e761e-126">обмен мгновенными сообщениями и сведениями о присутствии (только в двустороннем режиме);</span><span class="sxs-lookup"><span data-stu-id="e761e-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="e761e-127">Создание федеративных контактов XMPP в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="e761e-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e761e-128">Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите.</span><span class="sxs-lookup"><span data-stu-id="e761e-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="e761e-129">Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="e761e-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="e761e-130">Развертывание внешней федерации пограничного сервера, подключения к общедоступным службам обмена мгновенными сообщениями и протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="e761e-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e761e-131">Этап</span><span class="sxs-lookup"><span data-stu-id="e761e-131">Phase</span></span></th>
<th><span data-ttu-id="e761e-132">Шаги</span><span class="sxs-lookup"><span data-stu-id="e761e-132">Steps</span></span></th>
<th><span data-ttu-id="e761e-133">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e761e-133">Permissions</span></span></th>
<th><span data-ttu-id="e761e-134">Документация</span><span class="sxs-lookup"><span data-stu-id="e761e-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e761e-135">Определение параметров, добавляемых в существующее развертывание пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e761e-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="e761e-136">Запустите построитель топологий, чтобы изменить параметры пограничного сервера и создать и опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="e761e-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="e761e-137">Существующая пограничная топология реплицирует изменения из центрального хранилища управления на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="e761e-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="e761e-138">Группа "Администраторы домена" и группа RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e761e-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="e761e-139">Вы можете изменить топологию с помощью учетной записи члена группы локальных пользователей, однако для публикации топологии требуется учетная запись члена группы "Администраторы домена" и группы RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e761e-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="e761e-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Создание топологии пограничных серверов и директоров в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e761e-141">Подготовка к установке</span><span class="sxs-lookup"><span data-stu-id="e761e-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e761e-142">Убедитесь, что удовлетворены все требования к системе.</span><span class="sxs-lookup"><span data-stu-id="e761e-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="e761e-143">Настройте внутренние и внешние DNS-записи для поддержки подключения к общедоступным службам обмена сообщениями, федерации Lync и федерации XMPP.</span><span class="sxs-lookup"><span data-stu-id="e761e-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="e761e-144">Настройте порты и протоколы на брандмауэре для поддержки типов развертываемой федерации.</span><span class="sxs-lookup"><span data-stu-id="e761e-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="e761e-p108">Получите и установите общедоступные сертификаты. Время, требуемое для получения сертификатов, зависит от используемого центра сертификации (ЦС). На этом этапе развертывания данный этап является необязательным. Если этот шаг пропущен, то потребуется выполнить соответствующие действия в ходе настройки пограничного сервера. Служба пограничного сервера будет запущена только после получения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e761e-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e761e-150">Зависят от организации, поскольку эти роли обычно распределены между множеством рабочих групп</span><span class="sxs-lookup"><span data-stu-id="e761e-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="e761e-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Планирование SIP, Федерации XMPP и общедоступных мгновенных сообщений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e761e-152">Настройка пограничных серверов для сценариев федерации</span><span class="sxs-lookup"><span data-stu-id="e761e-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e761e-153">Добавьте экспортированный файл конфигурации топологии на каждой пограничный сервер или дождитесь завершения репликации.</span><span class="sxs-lookup"><span data-stu-id="e761e-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="e761e-154">Чтобы установить компоненты для поддержки федерации, запустите мастер развертывания повторно.</span><span class="sxs-lookup"><span data-stu-id="e761e-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="e761e-155">Настройте пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="e761e-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="e761e-156">Запросите сертификаты для каждого пограничного сервера и установите их.</span><span class="sxs-lookup"><span data-stu-id="e761e-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="e761e-157">Перезапустите службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e761e-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e761e-158">Группа "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="e761e-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="e761e-159"><a href="lync-server-2013-setting-up-lync-federation.md">Настройка Федерации Lync в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e761e-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Настройка подключения к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e761e-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Настройка Федерации XMPP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e761e-162">Настройка поддержки доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="e761e-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e761e-163">Использование доступа внешних пользователей в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e761e-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="e761e-164">Настройте политику внешнего доступа для включения коммуникаций с федеративными пользователями или внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="e761e-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="e761e-165">Настройте федеративные домены SIP, чтобы разрешить или заблокировать домены.</span><span class="sxs-lookup"><span data-stu-id="e761e-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="e761e-166">Включите федеративных поставщиков SIP для поставщиков общедоступных служб обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e761e-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="e761e-167">Настройте федеративных партнеров XMPP для каждого домена XMPP.</span><span class="sxs-lookup"><span data-stu-id="e761e-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e761e-168">Группа RTCUniversalServerAdmins или учетная запись пользователя, назначенная роли CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="e761e-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="e761e-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки доступа внешних пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e761e-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e761e-171">Проверка конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e761e-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="e761e-172">Проверьте возможности подключения к серверу и репликацию данных конфигурации с внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="e761e-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="e761e-173">Для проверки репликации требуется учетная запись группы RTCUniversalServerAdmins или учетная запись пользователя, назначенная роли CSAdministrator Для проверки подключения требуются учетные записи, представляющие все типы федеративных пользователей</span><span class="sxs-lookup"><span data-stu-id="e761e-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="e761e-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Проверка развертывания пограничного сервера в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e761e-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e761e-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</a></span><span class="sxs-lookup"><span data-stu-id="e761e-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

