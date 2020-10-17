---
title: 'Lync Server 2013: Включение или отключение удаленного доступа пользователей'
description: 'Lync Server 2013: Включение или отключение удаленного доступа пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea2d58c1978ac2d52365a4a453c40b38dd89c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547895"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="3f766-103">Включение или отключение доступа удаленных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f766-103">Enable or disable remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f766-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3f766-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3f766-105">Удаленные пользователи — это сотрудники организации, которые обладают постоянным удостоверением Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f766-105">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="3f766-106">Удаленные пользователи часто входят в Lync Server извне вашей сети с помощью виртуальной частной сети (VPN), если они не подключены к сети Организации.</span><span class="sxs-lookup"><span data-stu-id="3f766-106">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="3f766-107">К удаленным пользователям относятся сотрудники, работающие на дому, находящиеся к командировке, или другие удаленные пользователи, например доверенные поставщики, которым предоставлены корпоративные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="3f766-107">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="3f766-108">Если вы разрешите удаленный доступ пользователей для удаленных пользователей, поддерживаемые удаленные пользователи подключаются через Интернет и не должны подключаться с помощью VPN для совместной работе с внутренними пользователями с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f766-108">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="3f766-p102">Для поддержки удаленного доступа пользователей необходимо включить эту функцию. При включении удаленного доступа пользователей эта функция включается для всей организации. Если впоследствии вы захотите временно или постоянно запретить удаленный доступ пользователей, вы сможете отключить его для организации. Используйте процедуру, описанную в этом разделе, чтобы включить или отключить удаленный доступ пользователей, которые являются сотрудниками вашей организации.
</span><span class="sxs-lookup"><span data-stu-id="3f766-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f766-113">Включение удаленного доступа пользователей указывает, что серверы, на которых работает пограничная служба доступа, поддерживают связь с удаленными пользователями, но удаленные пользователи не могут участвовать в обмене мгновенными сообщениями или конференциях в Организации до тех пор, пока не будет настроена хотя бы одна политика для управления использованием удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f766-113">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="3f766-114">Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="3f766-114">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3f766-115">Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="3f766-115">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3f766-116">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="3f766-116">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="3f766-117">Дополнительные сведения о настройке политик для использования удаленного доступа пользователей приведены <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">в статье Настройка политик для управления доступом удаленных пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3f766-117">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="3f766-118">Включение и выключение функции удаленного доступа пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="3f766-118">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="3f766-119">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="3f766-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f766-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f766-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f766-121">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3f766-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f766-122">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).</span><span class="sxs-lookup"><span data-stu-id="3f766-122">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3f766-123">На странице **Access Edge Configuration** (Конфигурация Access Edge) щелкните **Global** (Глобальные), щелкните **Edit** (Изменить), а затем щелкните **Show details** (Показать данные).</span><span class="sxs-lookup"><span data-stu-id="3f766-123">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3f766-124">В области **Edit Access Edge Configuration** (Изменение конфигурации Access Edge) выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3f766-124">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="3f766-125">Чтобы включить функцию удаленного доступа пользователей в организации, установите флажок **Enable remote user access** (Включить удаленный доступ пользователей).</span><span class="sxs-lookup"><span data-stu-id="3f766-125">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="3f766-126">Чтобы отключить функцию удаленного доступа пользователей в организации, снимите флажок **Enable remote user access** (Включить удаленный доступ пользователей).</span><span class="sxs-lookup"><span data-stu-id="3f766-126">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="3f766-127">Щелкните **Commit** (Выполнить).</span><span class="sxs-lookup"><span data-stu-id="3f766-127">Click **Commit**.</span></span>

<span data-ttu-id="3f766-128">Чтобы разрешить удаленным пользователям входить на серверы, на которых работает Lync Server, необходимо настроить по крайней мере одну политику внешнего доступа для поддержки доступа удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3f766-128">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="3f766-129">Дополнительные сведения: [Настройка политик для управления доступом удаленных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="3f766-129">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3f766-130">Включение или отключение доступа удаленных пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f766-130">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3f766-131">Доступ к удаленному пользователю можно управлять с помощью Windows PowerShell и командлета Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3f766-131">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3f766-132">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f766-132">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3f766-133">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3f766-133">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="3f766-134">Включение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="3f766-134">To enable remote user access</span></span>

  - <span data-ttu-id="3f766-135">Для включения удаленного доступа пользователей задайте для свойства **AllowOutsideUsers** значение «True» ($True):</span><span class="sxs-lookup"><span data-stu-id="3f766-135">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="3f766-136">Отключение доступа удаленного пользователя</span><span class="sxs-lookup"><span data-stu-id="3f766-136">To disable remote user access</span></span>

  - <span data-ttu-id="3f766-137">Для отключения удаленного доступа пользователей задайте для свойства **AllowOutsideUsers** значение «False» ($False):</span><span class="sxs-lookup"><span data-stu-id="3f766-137">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

