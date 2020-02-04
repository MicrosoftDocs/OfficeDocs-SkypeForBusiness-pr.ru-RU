---
title: Настройка федерации SIP, федерации XMPP и общедоступных служб обмена мгновенными сообщениями
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
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="48370-102">Настройка федерации SIP, федерации XMPP и общедоступных служб обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48370-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48370-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="48370-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="48370-104">Интеграция, общедоступная служба обмена мгновенными сообщениями и расширенный протокол обмена сообщениями (КСМПП) определяют различные классы внешних пользователей — федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="48370-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="48370-105">Пользователи федеративного сервера Lync Server или развертывание КСМПП имеют доступ к ограниченному набору служб и проходят проверку подлинности с помощью внешнего развертывания.</span><span class="sxs-lookup"><span data-stu-id="48370-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="48370-106">Удаленные пользователи — это участники развертывания Lync Server, у которых есть доступ ко всем службам, предлагаемым вашим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="48370-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="48370-107">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="48370-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="48370-108">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="48370-108">has been announced.</span></span> <span data-ttu-id="48370-109">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48370-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="48370-110">Общедоступная служба обмена мгновенными сообщениями — это особый тип Федерации, который позволяет клиенту Lync Server получать доступ к настроенным участникам обмена мгновенными сообщениями с помощью Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="48370-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="48370-111">Среди текущих партнеров по подключению к мгновенным сообщениям:</span><span class="sxs-lookup"><span data-stu-id="48370-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="48370-112">America Online</span><span class="sxs-lookup"><span data-stu-id="48370-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="48370-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="48370-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="48370-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="48370-114">Yahoo\!</span></span>

<span data-ttu-id="48370-115">Общедоступная конфигурация службы мгновенных сообщений позволяет пользователям Lync получать доступ к общедоступным пользователям по подключению к службе мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="48370-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="48370-116">Обмен мгновенными сообщениями и сведениями о присутствии</span><span class="sxs-lookup"><span data-stu-id="48370-116">IM and Presence</span></span>

  - <span data-ttu-id="48370-117">Видимость контактных данных общедоступной службы обмена мгновенными сообщениями в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="48370-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="48370-118">Человеко общаться с контактами с помощью общения</span><span class="sxs-lookup"><span data-stu-id="48370-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="48370-119">Голосовые и видеозвонки с пользователями Windows Live</span><span class="sxs-lookup"><span data-stu-id="48370-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="48370-120">Платформа Lync Server Federation определяет соглашение между развертыванием Lync Server и другими развертываниями Office Communications Server 2007 R2 или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48370-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="48370-121">Интегрированная конфигурация Lync Server позволяет пользователям Lync получать доступ к федеративным пользователям, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="48370-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="48370-122">Обмен мгновенными сообщениями и сведениями о присутствии</span><span class="sxs-lookup"><span data-stu-id="48370-122">IM and Presence</span></span>

  - <span data-ttu-id="48370-123">Создание федеративных контактов в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="48370-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="48370-124">КСМПП Федерация определяет внешнее развертывание на основе расширенного протокола обмена сообщениями и присутствия.</span><span class="sxs-lookup"><span data-stu-id="48370-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="48370-125">Конфигурация КСМПП позволяет пользователям Lync получать доступ к разрешенным пользователям домена КСМПП, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="48370-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="48370-126">Обмен сообщениями и присутствие — только для человека</span><span class="sxs-lookup"><span data-stu-id="48370-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="48370-127">Создание федеративных контактов КСМПП в клиенте Lync</span><span class="sxs-lookup"><span data-stu-id="48370-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="48370-p106">Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="48370-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="48370-130">Внешняя Федерация пограничного сервера, соединение общедоступных мгновенных сообщений и процесс развертывания КСМПП пользователей</span><span class="sxs-lookup"><span data-stu-id="48370-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48370-131">Этап</span><span class="sxs-lookup"><span data-stu-id="48370-131">Phase</span></span></th>
<th><span data-ttu-id="48370-132">Шаги</span><span class="sxs-lookup"><span data-stu-id="48370-132">Steps</span></span></th>
<th><span data-ttu-id="48370-133">Разрешения</span><span class="sxs-lookup"><span data-stu-id="48370-133">Permissions</span></span></th>
<th><span data-ttu-id="48370-134">Документация</span><span class="sxs-lookup"><span data-stu-id="48370-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48370-135">Определение параметров для добавления в существующее развертывание пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="48370-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="48370-136">Запустите построитель топологии, чтобы изменить параметры пограничного сервера и создать и опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="48370-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="48370-137">Существующая топология пограничного сервера будет реплицировать изменения из хранилища центрального управления на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="48370-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="48370-138">Группа «Администраторы домена» и группа «Рткуниверсалсерверадминс»</span><span class="sxs-lookup"><span data-stu-id="48370-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="48370-139">Вы можете изменить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии требуется учетная запись, которая входит в группу "Администраторы домена" и в группу "Рткуниверсалсерверадминс".</span><span class="sxs-lookup"><span data-stu-id="48370-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="48370-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Создание топологии пограничных серверов и директора в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48370-141">Подготовка к установке</span><span class="sxs-lookup"><span data-stu-id="48370-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="48370-142">Убедитесь в том, что соблюдены требования к системе.</span><span class="sxs-lookup"><span data-stu-id="48370-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="48370-143">Настройка внутренних и внешних DNS-записей для поддержки общедоступной службы обмена мгновенными сообщениями, Федерации Lync и КСМПП Федерации</span><span class="sxs-lookup"><span data-stu-id="48370-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="48370-144">Настройка портов и протоколов в брандмауэре для поддержки типов интеграции, которые вы развертываете</span><span class="sxs-lookup"><span data-stu-id="48370-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="48370-145">Получение и установка общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="48370-145">Obtain and install public certificates.</span></span> <span data-ttu-id="48370-146">Время, необходимое для получения сертификатов, зависит от того, какой центр сертификации (ЦС) выдаст сертификат.</span><span class="sxs-lookup"><span data-stu-id="48370-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="48370-147">Этот шаг является необязательным в этой точке развертывания.</span><span class="sxs-lookup"><span data-stu-id="48370-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="48370-148">Если вы не выполнили этот этап на этом этапе, необходимо сделать это во время настройки пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="48370-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="48370-149">Служба пограничного сервера не может быть запущена, пока не будут получены сертификаты</span><span class="sxs-lookup"><span data-stu-id="48370-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="48370-150">В соответствии с вашей организацией, так как эти роли обычно делятся на несколько рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="48370-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="48370-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Планирование SIP, Федерации КСМПП и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48370-152">Настройка пограничных серверов для сценариев интеграции</span><span class="sxs-lookup"><span data-stu-id="48370-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="48370-153">Передача экспортированного файла конфигурации топологии на пограничный сервер или разрешение выполнения репликации</span><span class="sxs-lookup"><span data-stu-id="48370-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="48370-154">Повторное выполнение мастера развертывания для установки вспомогательных компонентов для Федерации</span><span class="sxs-lookup"><span data-stu-id="48370-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="48370-155">Настройка пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="48370-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="48370-156">Запрос и установка сертификатов для каждого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="48370-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="48370-157">Перезапуск служб пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="48370-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="48370-158">Группа администраторов</span><span class="sxs-lookup"><span data-stu-id="48370-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="48370-159"><a href="lync-server-2013-setting-up-lync-federation.md">Настройка федерации в Lync в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="48370-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Настройка соединения для общедоступных служб обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="48370-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Настройка федерации XMPP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48370-162">Настройка поддержки внешнего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="48370-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="48370-163">Использование внешних пользователей панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="48370-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="48370-164">Настройка политики внешнего доступа для подключения к данным с помощью федеративных пользователей или открытых пользователей</span><span class="sxs-lookup"><span data-stu-id="48370-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="48370-165">Настройка федеративных доменов SIP для разрешения или блокировки доменов</span><span class="sxs-lookup"><span data-stu-id="48370-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="48370-166">Включение поставщиков услуг SIP Федерации для общедоступных служб обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="48370-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="48370-167">Настройка федеративных партнеров КСМПП для КСМПП домена</span><span class="sxs-lookup"><span data-stu-id="48370-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="48370-168">Группа Рткуниверсалсерверадминс или учетная запись пользователя, назначенная роли Ксадминистратор</span><span class="sxs-lookup"><span data-stu-id="48370-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="48370-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Настройка поддержки доступа внешних пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="48370-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48370-171">Проверка конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="48370-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="48370-172">Проверка подключения к серверу и репликация данных конфигурации с внутренних серверов</span><span class="sxs-lookup"><span data-stu-id="48370-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="48370-173">Для проверки репликации, Рткуниверсалсерверадминс или учетной записи пользователя, назначенной для Ксадминистратор Ролефор проверки подключения пользователей, пользователь для каждого типа федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="48370-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="48370-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Проверка развертывания пограничного сервера в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48370-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="48370-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="48370-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

