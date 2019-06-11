---
title: 'Lync Server 2013: включение или отключения удаленного доступа пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="4ff13-102">Включение или отключения удаленного доступа пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ff13-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ff13-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4ff13-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4ff13-104">Удаленные пользователи — это пользователи в вашей организации, у которых есть постоянная идентификация Active Directory в Организации.</span><span class="sxs-lookup"><span data-stu-id="4ff13-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="4ff13-105">Удаленные пользователи часто входят в Lync Server из-за пределов вашей сети, используя виртуальную частную сеть (VPN), если они не подключены к сети Организации.</span><span class="sxs-lookup"><span data-stu-id="4ff13-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="4ff13-106">Удаленные пользователи включают сотрудников, работающих дома или в дороге и другие удаленные работники, такие как доверенные поставщики, которым предоставлены корпоративные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="4ff13-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="4ff13-107">Если вы разрешите удаленному пользователю доступ для удаленных пользователей, они будут подключены через Интернет и не должны подключаться с помощью VPN для совместной работы с внутренними пользователями с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ff13-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="4ff13-108">Для поддержки удаленного доступа пользователей необходимо разрешить удаленный доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="4ff13-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="4ff13-109">При включении удаленного доступа пользователь включается для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="4ff13-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="4ff13-110">Если позже вы захотите временно запретить доступ к удаленному пользователю, вы можете отключить его для своей организации.</span><span class="sxs-lookup"><span data-stu-id="4ff13-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="4ff13-111">Чтобы включить или отключить удаленный доступ пользователей для вашей организации, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4ff13-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ff13-112">Разрешение удаленного доступа пользователей означает, что серверы, на которых работает служба EDGE, поддерживают связь с удаленными пользователями, но удаленные пользователи не могут участвовать в обмене мгновенными сообщениями и конференциях в вашей организации, пока не будет настроена бы одна политика для управления использованием удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ff13-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="4ff13-113">Параметры политики сервера Lync Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="4ff13-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="4ff13-114">Приоритет политики Lync Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="4ff13-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="4ff13-115">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="4ff13-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="4ff13-116">Подробнее о настройке политик удаленного доступа пользователей можно узнать <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">в разделе Настройка политик для управления доступом удаленных пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ff13-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="4ff13-117">Включение и отключение удаленного доступа пользователей для Организации</span><span class="sxs-lookup"><span data-stu-id="4ff13-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="4ff13-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4ff13-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4ff13-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ff13-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4ff13-120">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4ff13-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4ff13-121">На левой панели навигации щелкните **Федерация и внешний доступ**, а затем щелкните **Конфигурация пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="4ff13-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="4ff13-122">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4ff13-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4ff13-123">В окне **изменение конфигурации Edge Access**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4ff13-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="4ff13-124">Чтобы разрешить удаленному пользователю доступ к Организации, установите флажок **Разрешить удаленный доступ к пользователям** .</span><span class="sxs-lookup"><span data-stu-id="4ff13-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="4ff13-125">Чтобы запретить удаленному пользователю доступ к вашей организации, снимите флажок **Разрешить удаленный доступ к пользователям** .</span><span class="sxs-lookup"><span data-stu-id="4ff13-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="4ff13-126">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4ff13-126">Click **Commit**.</span></span>

<span data-ttu-id="4ff13-127">Чтобы разрешить удаленным пользователям входить на серверы с Lync Server, необходимо также настроить хотя бы одну политику внешнего доступа, чтобы обеспечить доступ к удаленному пользователю.</span><span class="sxs-lookup"><span data-stu-id="4ff13-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="4ff13-128">Подробности можно найти в разделе [Настройка политик для управления доступом удаленных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="4ff13-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4ff13-129">Включение и отключение удаленного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ff13-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4ff13-130">Доступ к удаленному пользователю можно управлять с помощью Windows PowerShell и командлета Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="4ff13-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4ff13-131">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ff13-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4ff13-132">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ff13-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="4ff13-133">Разрешение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="4ff13-133">To enable remote user access</span></span>

  - <span data-ttu-id="4ff13-134">Чтобы разрешить удаленному пользователю доступ, присвойте свойству **алловаутсидеусерс** значение True ($true):</span><span class="sxs-lookup"><span data-stu-id="4ff13-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="4ff13-135">Отключение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="4ff13-135">To disable remote user access</span></span>

  - <span data-ttu-id="4ff13-136">Чтобы запретить удаленному доступу пользователей, установите для свойства **алловаутсидеусерс** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="4ff13-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

