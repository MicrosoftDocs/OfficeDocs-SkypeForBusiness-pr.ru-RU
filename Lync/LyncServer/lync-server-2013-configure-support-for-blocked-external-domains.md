---
title: 'Lync Server 2013: настройка поддержки заблокированных внешних доменов'
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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="d2e83-102">Настройка поддержки заблокированных внешних доменов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2e83-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2e83-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d2e83-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d2e83-104">Если вы настроили поддержку федеративных партнеров, вы можете управлять тем, какие домены будут блокироваться из Федерации в своей организации.</span><span class="sxs-lookup"><span data-stu-id="d2e83-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="d2e83-105">Список блокируемых доменов будет выступать в качестве черного списка (список явных записей, которые не разрешены) и будут применяться в случае обнаружения федеративного домена, если этот параметр включен.</span><span class="sxs-lookup"><span data-stu-id="d2e83-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="d2e83-106">Дополнительные сведения можно найти [в разделе Включение и отключение обнаружения партнеров Федерации в Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="d2e83-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="d2e83-107">Блокировать один или несколько внешних доменов из подключения к вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2e83-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="d2e83-108">Для этого добавьте домен в список блокируемых доменов.</span><span class="sxs-lookup"><span data-stu-id="d2e83-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="d2e83-109">Добавление внешнего домена в список блокируемых доменов</span><span class="sxs-lookup"><span data-stu-id="d2e83-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="d2e83-110">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d2e83-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d2e83-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2e83-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d2e83-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d2e83-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d2e83-113">На панели навигации слева выберите **внешний пользовательский доступ**.</span><span class="sxs-lookup"><span data-stu-id="d2e83-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="d2e83-114">Выберите пункт **федеративные домены**, нажмите кнопку **создать**и выберите пункт **заблокированный домен**.</span><span class="sxs-lookup"><span data-stu-id="d2e83-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="d2e83-115">В **новых федеративных доменах**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2e83-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="d2e83-116">В поле **доменное имя (или FQDN)** введите имя домена федеративного партнера, который вы хотите заблокировать.</span><span class="sxs-lookup"><span data-stu-id="d2e83-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d2e83-117">Длина имени не может превышать 256 знаков.</span><span class="sxs-lookup"><span data-stu-id="d2e83-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="d2e83-118">Поиск по имени домена федеративного партнера выполняется в соответствии с суффиксом.</span><span class="sxs-lookup"><span data-stu-id="d2e83-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="d2e83-119">Например, если ввести <STRONG>contoso.com</STRONG>, поиск будет также возвращать <STRONG>IT.contoso.com</STRONG>домена.</span><span class="sxs-lookup"><span data-stu-id="d2e83-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="d2e83-120">Домен федеративного партнера не может быть заблокирован и разрешен.</span><span class="sxs-lookup"><span data-stu-id="d2e83-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="d2e83-121">Lync Server 2013 предотвращает это, так что вам не нужно синхронизировать списки.</span><span class="sxs-lookup"><span data-stu-id="d2e83-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="d2e83-122">Необязательно В **примечании**введите данные, к которым вы хотите предоставить доступ другим системным администраторам об этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2e83-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="d2e83-123">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d2e83-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="d2e83-124">Повторите действия 4 – 6 для каждого федеративного партнера, который вы хотите заблокировать.</span><span class="sxs-lookup"><span data-stu-id="d2e83-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="d2e83-125">Для включения федеративного доступа пользователей также необходимо включить поддержку федеративного доступа пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2e83-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="d2e83-126">Дополнительные сведения можно найти [в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d2e83-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="d2e83-127">Кроме того, вы должны настроить политику и применить ее к пользователям, которые должны быть доступны для совместной работы с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="d2e83-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="d2e83-128">Подробности можно найти [в разделе Настройка политик для управления доступом к федеративным пользователям в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="d2e83-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

