---
title: 'Lync Server 2013: Настройка поддержки для разрешенных внешних доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ca4ebfd56407bfd162bd7df76be98c890e2fbf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="4a587-102">Настройка поддержки для разрешенных внешних доменов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a587-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a587-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4a587-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4a587-p101">Если настроена поддержка федеративных партнеров, можно управлять, какие домены будут образовывать федерацию с данной организацией. Один или несколько внешних доменов настраиваются как разрешенные домены федерации. Для этого добавьте каждый домен в список разрешенных доменов. Даже если обнаружение партнеров включено в организации, упомянутое выше действие следует выполнить, если домен является федеративным партнером, который будет обеспечивать связь с более чем 1000 пользователей в данной организации или если пользователи будут отправлять более 20 сообщений в секунду. Если обнаружение партнеров не включено в организации, в обмене мгновенными сообщениями и конференциях с участием пользователей данной организации смогут принимать участие только пользователи внешних доменов, добавленных разрешенные домены. Если необходимо ограничить доступ к федеративному домену определенным сервером, на котором работает служба пограничного доступа федеративного партнера, следует указать доменное имя сервера, на котором работает служба пограничного доступа. Это следует сделать для каждого домена в списке разрешенных.</span><span class="sxs-lookup"><span data-stu-id="4a587-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a587-110">В данной процедуре описывается, как настроить поддержку определенных доменов, однако для реализации поддержки федеративных пользователей также необходимо включить поддержку федеративных пользователей в данной организации наряду с настройкой и применением политик для управления тем, какие пользователи смогут работать совместно с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="4a587-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="4a587-111">Дополнительные сведения о включении поддержки федеративных пользователей можно узнать <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в статье Включение и отключение удаленного доступа пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4a587-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="4a587-112">Дополнительные сведения о настройке политик управления федерациями можно узнать в статье <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4a587-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="4a587-113">Чтобы добавить внешний домен в список разрешенных доменов, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="4a587-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="4a587-114">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4a587-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4a587-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a587-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a587-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a587-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a587-117">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Федеративные домены**.</span><span class="sxs-lookup"><span data-stu-id="4a587-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="4a587-118">На странице **Федеративные домены** нажмите кнопку **Создать**, затем щелкните **Разрешенный домен**.</span><span class="sxs-lookup"><span data-stu-id="4a587-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="4a587-119">В области **Новые федеративные домены**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a587-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="4a587-120">В поле **Доменное имя (или полное доменное имя)** введите имя домена федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="4a587-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4a587-p104">Это имя должно быть уникальным и не может уже существовать как разрешенный домен, указанный на сервере, где работает служба пограничного доступа. Длина имени не должна превышать 256 символов.</span><span class="sxs-lookup"><span data-stu-id="4a587-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="4a587-p105">При поиске по имени федеративного домена партнера выполняется сопоставление суффикса. Например, если ввести <STRONG>contoso.com</STRONG>, поиск также возвратит и домен <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4a587-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="4a587-125">Федеративный домен партнера не может быть одновременно и заблокирован, и разрешен.</span><span class="sxs-lookup"><span data-stu-id="4a587-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="4a587-126">Lync Server 2013 предотвращает возникновение этого действия, поэтому нет необходимости в синхронизации списков.</span><span class="sxs-lookup"><span data-stu-id="4a587-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="4a587-127">Если необходимо ограничить доступ для этого федеративного домена только пользователями определенного сервера с работающей службой пограничного доступа, в поле **Служба пограничного доступа (полное доменное имя)** введите полное доменное имя сервера федеративного домена, на котором работает служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="4a587-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="4a587-128">Если необходимо предоставить дополнительную информацию, в поле **Примечание** введите сведения о данной конфигурации, которые следует предоставить другим системным администраторам.</span><span class="sxs-lookup"><span data-stu-id="4a587-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="4a587-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4a587-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="4a587-130">Повторите шаги с 4 по 6 для каждого домена федеративного партнера, которого следует разрешить.</span><span class="sxs-lookup"><span data-stu-id="4a587-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="4a587-131">Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку доступа федеративных пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a587-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="4a587-132">Дополнительные сведения см. [в статье Включение или отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4a587-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="4a587-133">Кроме того, следует настроить и применить политику к пользователям, которым требуется разрешить совместную работу с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="4a587-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4a587-134">Дополнительные сведения: [Настройка политик для управления доступом федеративных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4a587-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

