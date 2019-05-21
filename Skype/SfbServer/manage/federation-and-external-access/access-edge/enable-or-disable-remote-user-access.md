---
title: Включение или отключения удаленного доступа пользователей
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если вы разрешите удаленному пользователю доступ для удаленных пользователей, они будут подключены через Интернет и не должны подключаться с помощью VPN для совместной работы с внутренними пользователями с помощью Skype для бизнеса Server.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280238"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="1905f-103">Включение и отключение удаленного доступа пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1905f-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="1905f-104">Удаленные пользователи — это пользователи в вашей организации, у которых есть постоянная идентификация Active Directory в Организации.</span><span class="sxs-lookup"><span data-stu-id="1905f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="1905f-105">Удаленные пользователи часто входят в Skype для бизнеса Server за пределами вашей сети, используя виртуальную частную сеть (VPN), если они не подключены к сети Организации.</span><span class="sxs-lookup"><span data-stu-id="1905f-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="1905f-106">Удаленные пользователи включают сотрудников, работающих дома или в дороге и другие удаленные работники, такие как доверенные поставщики, которым предоставлены корпоративные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1905f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="1905f-107">Если вы разрешите удаленному пользователю доступ для удаленных пользователей, они будут подключены через Интернет и не должны подключаться с помощью VPN для совместной работы с внутренними пользователями с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1905f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="1905f-108">Для поддержки удаленного доступа пользователей необходимо разрешить удаленный доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="1905f-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="1905f-109">При включении удаленного доступа пользователь включается для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="1905f-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="1905f-110">Если позже вы захотите временно запретить доступ к удаленному пользователю, вы можете отключить его для своей организации.</span><span class="sxs-lookup"><span data-stu-id="1905f-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="1905f-111">Чтобы включить или отключить удаленный доступ пользователей для вашей организации, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="1905f-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="1905f-112">Разрешение удаленного доступа пользователей означает, что серверы, на которых работает служба EDGE, поддерживают связь с удаленными пользователями, но удаленные пользователи не могут участвовать в обмене мгновенными сообщениями и конференциях в вашей организации, пока не будет настроена бы одна политика для управления использованием удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="1905f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="1905f-113">Параметры политики Skype для бизнеса Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="1905f-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1905f-114">Приоритет политики в Skype для бизнеса Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="1905f-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1905f-115">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="1905f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="1905f-116">Дополнительные сведения о настройке политик удаленного доступа пользователей можно найти [в разделе Настройка политик для управления доступом удаленных пользователей в Skype для бизнеса Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1905f-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="1905f-117">Включение и отключение удаленного доступа пользователей для Организации</span><span class="sxs-lookup"><span data-stu-id="1905f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="1905f-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1905f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1905f-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1905f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1905f-120">На левой панели навигации щелкните **Федерация и внешний доступ**, а затем щелкните **Конфигурация пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="1905f-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1905f-121">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="1905f-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1905f-122">В окне **изменение конфигурации Edge Access**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1905f-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1905f-123">Чтобы разрешить удаленному пользователю доступ к Организации, установите флажок **Разрешить удаленный доступ к пользователям** .</span><span class="sxs-lookup"><span data-stu-id="1905f-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="1905f-124">Чтобы запретить удаленному пользователю доступ к вашей организации, снимите флажок **Разрешить удаленный доступ к пользователям** .</span><span class="sxs-lookup"><span data-stu-id="1905f-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="1905f-125">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1905f-125">Click **Commit**.</span></span>

<span data-ttu-id="1905f-126">Чтобы разрешить удаленным пользователям входить на серверы, на которых работает Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="1905f-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="1905f-127">Подробности можно найти [в разделе Настройка политик для управления доступом удаленных пользователей в Skype для бизнеса Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1905f-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1905f-128">Включение и отключение удаленного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1905f-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1905f-129">Доступ к удаленному пользователю можно управлять с помощью Windows PowerShell и командлета Set-Ксакцесседжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="1905f-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="1905f-130">Этот командлет можно выполнить либо из управляющей оболочки Skype для бизнеса Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1905f-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="1905f-131">Разрешение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="1905f-131">To enable remote user access</span></span>

  - <span data-ttu-id="1905f-132">Чтобы разрешить удаленному пользователю доступ, присвойте свойству **алловаутсидеусерс** значение True ($true):</span><span class="sxs-lookup"><span data-stu-id="1905f-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="1905f-133">Отключение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="1905f-133">To disable remote user access</span></span>

  - <span data-ttu-id="1905f-134">Чтобы запретить удаленному доступу пользователей, установите для свойства **алловаутсидеусерс** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="1905f-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


