---
title: 'Lync Server 2013: Настройка поддержки заблокированных внешних доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="63e6b-102">Настройка поддержки заблокированных внешних доменов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63e6b-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63e6b-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="63e6b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="63e6b-104">Если настроена поддержка федеративных партнеров, можно управлять тем, федерация с какими доменами будет блокироваться на уровне организации.</span><span class="sxs-lookup"><span data-stu-id="63e6b-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="63e6b-105">Если включен рассматриваемый параметр, этот список доменов будет использоваться для блокировки (список явно запрещенных записей) и будет применяться при обнаружении федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="63e6b-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="63e6b-106">Дополнительные сведения см. [в статье Включение и отключение обнаружения партнеров Федерации в Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="63e6b-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="63e6b-p102">Заблокируйте один или несколько внешних доменов, чтобы они не смогли подключаться к организации. Для этого добавьте домен в список заблокированных доменов.</span><span class="sxs-lookup"><span data-stu-id="63e6b-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="63e6b-109">Чтобы добавить внешний домен в список заблокированных доменов, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="63e6b-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="63e6b-110">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="63e6b-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63e6b-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63e6b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63e6b-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63e6b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63e6b-113">На левой панели навигации щелкните пункт **Доступ для внешних пользователей**.</span><span class="sxs-lookup"><span data-stu-id="63e6b-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="63e6b-114">На странице **Федеративные домены** нажмите кнопку **Создать**, затем щелкните **Заблокированный домен**.</span><span class="sxs-lookup"><span data-stu-id="63e6b-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="63e6b-115">В области **Новые федеративные домены**, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="63e6b-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="63e6b-116">В поле **Доменное имя (или полное доменное имя)** введите имя домена федеративного партнера, который следует заблокировать.</span><span class="sxs-lookup"><span data-stu-id="63e6b-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="63e6b-117">Длина имени не должна превышать 256 символов.</span><span class="sxs-lookup"><span data-stu-id="63e6b-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="63e6b-p104">При поиске по имени федеративного домена партнера выполняется сопоставление суффикса. Например, если ввести <STRONG>contoso.com</STRONG>, поиск также возвратит и домен <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="63e6b-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="63e6b-120">Федеративный домен партнера не может быть одновременно и заблокирован, и разрешен.</span><span class="sxs-lookup"><span data-stu-id="63e6b-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="63e6b-121">Lync Server 2013 предотвращает возникновение этого действия, поэтому нет необходимости в синхронизации списков.</span><span class="sxs-lookup"><span data-stu-id="63e6b-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="63e6b-122">(Дополнительно) В поле **Примечание** введите сведения о конфигурации, которые следует предоставить другим системным администраторам.</span><span class="sxs-lookup"><span data-stu-id="63e6b-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="63e6b-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="63e6b-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="63e6b-124">Повторите шаги с 4 по 6 для каждого федеративного партнера, которого следует заблокировать.</span><span class="sxs-lookup"><span data-stu-id="63e6b-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="63e6b-125">Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку доступа федеративных пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="63e6b-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="63e6b-126">Дополнительные сведения см. [в статье Включение или отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="63e6b-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="63e6b-127">Кроме того, следует настроить и применить политику к пользователям, которым требуется разрешить совместную работу с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="63e6b-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="63e6b-128">Дополнительные сведения: [Настройка политик для управления доступом федеративных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="63e6b-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

