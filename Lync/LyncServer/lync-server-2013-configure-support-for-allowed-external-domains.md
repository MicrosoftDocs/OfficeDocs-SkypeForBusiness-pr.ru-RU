---
title: 'Lync Server 2013: настройка поддержки для разрешенных внешних доменов'
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
ms.openlocfilehash: 31aa2ab9db9ffccd3acda90e9651dfad20b85e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="a44f9-102">Настройка поддержки для разрешенных внешних доменов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44f9-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44f9-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a44f9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a44f9-104">Если вы настроили поддержку федеративных партнеров, вы можете управлять тем, какие конкретные домены смогут использовать в своей организации.</span><span class="sxs-lookup"><span data-stu-id="a44f9-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="a44f9-105">Вы можете настроить один или несколько конкретных внешних доменов как разрешенные федеративные домены.</span><span class="sxs-lookup"><span data-stu-id="a44f9-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="a44f9-106">Для этого добавьте каждый домен в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="a44f9-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="a44f9-107">Если для организации включена возможность обнаружения партнеров, сделайте это, если домен является федеративным партнером, которому может потребоваться взаимодействовать с более чем 1 000 пользователей, или может потребоваться отправить более 20 сообщений в секунду.</span><span class="sxs-lookup"><span data-stu-id="a44f9-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="a44f9-108">Если в вашей организации не включена возможность обнаружения партнеров, пользователи из внешних доменов, добавленные в список разрешенных доменов, могут принимать участие в СООБЩЕНИЯх и конференциях с пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="a44f9-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="a44f9-109">Если вы хотите ограничить доступ к Федеративной домену определенному серверу, на котором запущена служба Edge для федеративного партнера, вы можете указать доменное имя сервера, на котором запущена служба пограничного доступа для каждого домена в списке разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="a44f9-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a44f9-110">В этой статье описано, как настроить поддержку для конкретных доменов, но реализация поддержки федеративных пользователей также требует включения поддержки федеративных пользователей для Организации, настройки и применения политик для управления тем, какие пользователи могут выполнять эти действия. Совместная работа с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="a44f9-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="a44f9-111">Дополнительные сведения о включении поддержки федеративных пользователей можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a44f9-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="a44f9-112">Дополнительные сведения о настройке политик для управления интеграцией можно найти <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">в разделе Настройка политик для управления доступом пользователей Федерации в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a44f9-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="a44f9-113">Добавление внешнего домена в список разрешенных доменов</span><span class="sxs-lookup"><span data-stu-id="a44f9-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="a44f9-114">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a44f9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a44f9-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a44f9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a44f9-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a44f9-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a44f9-117">На панели навигации слева выберите **внешний доступ для пользователей**, а затем — **федеративные домены**.</span><span class="sxs-lookup"><span data-stu-id="a44f9-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="a44f9-118">На странице **федеративные домены** нажмите кнопку **создать**, а затем выберите пункт **разрешенный домен**.</span><span class="sxs-lookup"><span data-stu-id="a44f9-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="a44f9-119">В **новых федеративных доменах**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a44f9-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="a44f9-120">В поле **Domain Name (или FQDN)** введите имя домена федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="a44f9-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a44f9-121">Это имя должно быть уникальным и не может быть уже разрешенным доменом для этого сервера, на котором запущена служба Edge Access.</span><span class="sxs-lookup"><span data-stu-id="a44f9-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="a44f9-122">Длина имени не может превышать 256 знаков.</span><span class="sxs-lookup"><span data-stu-id="a44f9-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="a44f9-123">Поиск по имени домена федеративного партнера выполняется в соответствии с суффиксом.</span><span class="sxs-lookup"><span data-stu-id="a44f9-123">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="a44f9-124">Например, если ввести <STRONG>contoso.com</STRONG>, поиск будет также возвращать <STRONG>IT.contoso.com</STRONG>домена.</span><span class="sxs-lookup"><span data-stu-id="a44f9-124">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="a44f9-125">Домен федеративного партнера не может быть заблокирован и разрешен.</span><span class="sxs-lookup"><span data-stu-id="a44f9-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="a44f9-126">Lync Server 2013 предотвращает это, так что вам не нужно синхронизировать списки.</span><span class="sxs-lookup"><span data-stu-id="a44f9-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="a44f9-127">Если вы хотите ограничить доступ для этого федеративного домена пользователям определенного сервера, на котором запущена служба пограничного доступа **(в Microsoft Edge Service)**, введите полное доменное имя сервера федеративного домена, на котором запущена служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="a44f9-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="a44f9-128">Если вы хотите предоставить дополнительные сведения, в **Комментарии**введите данные, к которым вы хотите предоставить доступ другим системным администраторам об этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a44f9-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="a44f9-129">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a44f9-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="a44f9-130">Повторите действия 4 – 6 для каждого домена федеративного партнера, который вы хотите разрешить.</span><span class="sxs-lookup"><span data-stu-id="a44f9-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="a44f9-131">Для включения федеративного доступа пользователей также необходимо включить поддержку федеративного доступа пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a44f9-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="a44f9-132">Дополнительные сведения можно найти [в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a44f9-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="a44f9-133">Кроме того, вы должны настроить политику и применить ее к пользователям, которые должны быть доступны для совместной работы с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="a44f9-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a44f9-134">Подробности можно найти [в разделе Настройка политик для управления доступом к федеративным пользователям в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a44f9-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

