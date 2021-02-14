---
title: Включение или отключения удаленного доступа пользователей
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если вы включаете удаленный доступ пользователей для удаленных пользователей, поддерживаемые удаленные пользователи подключаются через Интернет и не должны подключаться через VPN для совместной работы с внутренними пользователями с помощью Skype для бизнеса Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817399"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="070c8-103">Включить или отключить удаленный доступ пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="070c8-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="070c8-104">Удаленные пользователи — это сотрудники организации, которые обладают постоянным удостоверением Active Directory.</span><span class="sxs-lookup"><span data-stu-id="070c8-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="070c8-105">Удаленные пользователи часто подключаются к Skype для бизнеса Server из-за пределов вашей сети, используя виртуальную частную сеть (VPN), если они не подключены к сети вашей организации.</span><span class="sxs-lookup"><span data-stu-id="070c8-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="070c8-106">К удаленным пользователям относятся сотрудники, работающие на дому, находящиеся к командировке, или другие удаленные пользователи, например доверенные поставщики, которым предоставлены корпоративные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="070c8-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="070c8-107">Если вы включаете удаленный доступ пользователей для удаленных пользователей, поддерживаемые удаленные пользователи подключаются через Интернет и не должны подключаться через VPN для совместной работы с внутренними пользователями с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="070c8-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="070c8-p102">Для поддержки удаленного доступа пользователей необходимо включить эту функцию. При включении удаленного доступа пользователей эта функция включается для всей организации. Если впоследствии вы захотите временно или постоянно запретить удаленный доступ пользователей, вы сможете отключить его для организации. Используйте процедуру, описанную в этом разделе, чтобы включить или отключить удаленный доступ пользователей, которые являются сотрудниками вашей организации.
</span><span class="sxs-lookup"><span data-stu-id="070c8-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="070c8-112">Включение доступа удаленных пользователей указывает только на то, что серверы, на которые запущена поминутная служба доступа, поддерживают связь с удаленными пользователями, но удаленные пользователи не могут участвовать в обмене мгновенными сообщениями или конференциях в организации, пока не будет настроена хотя бы одна политика для управления использованием удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="070c8-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="070c8-113">Параметры политики Skype для бизнеса Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="070c8-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="070c8-114">Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние). </span><span class="sxs-lookup"><span data-stu-id="070c8-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="070c8-115">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="070c8-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="070c8-116">Подробные сведения о настройке политик для использования удаленного доступа пользователей см. в подстройке "Настройка политик для управления удаленным доступом пользователей [в Skype для бизнеса Server".](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="070c8-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="070c8-117">Включение и выключение функции удаленного доступа пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="070c8-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="070c8-118">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="070c8-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="070c8-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="070c8-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="070c8-120">На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).</span><span class="sxs-lookup"><span data-stu-id="070c8-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="070c8-121">На странице **Access Edge Configuration** (Конфигурация Access Edge) щелкните **Global** (Глобальные), щелкните **Edit** (Изменить), а затем щелкните **Show details** (Показать данные).</span><span class="sxs-lookup"><span data-stu-id="070c8-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="070c8-122">В области **Edit Access Edge Configuration** (Изменение конфигурации Access Edge) выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="070c8-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="070c8-123">Чтобы включить функцию удаленного доступа пользователей в организации, установите флажок **Enable remote user access** (Включить удаленный доступ пользователей).</span><span class="sxs-lookup"><span data-stu-id="070c8-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="070c8-124">Чтобы отключить функцию удаленного доступа пользователей в организации, снимите флажок **Enable remote user access** (Включить удаленный доступ пользователей).</span><span class="sxs-lookup"><span data-stu-id="070c8-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="070c8-125">Щелкните **Commit** (Выполнить).</span><span class="sxs-lookup"><span data-stu-id="070c8-125">Click **Commit**.</span></span>

<span data-ttu-id="070c8-126">Чтобы позволить удаленным пользователям войти на серверы Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="070c8-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="070c8-127">For details, see [Configure policies to control remote user access in Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="070c8-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="070c8-128">Включение или отключение удаленного доступа пользователей с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="070c8-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="070c8-129">Удаленным доступом пользователей можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="070c8-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="070c8-130">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="070c8-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="070c8-131">Чтобы включить удаленный доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="070c8-131">To enable remote user access</span></span>

  - <span data-ttu-id="070c8-132">Для включения удаленного доступа пользователей задайте для свойства **AllowOutsideUsers** значение «True» ($True):</span><span class="sxs-lookup"><span data-stu-id="070c8-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="070c8-133">Отключение доступа удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="070c8-133">To disable remote user access</span></span>

  - <span data-ttu-id="070c8-134">Для отключения удаленного доступа пользователей задайте для свойства **AllowOutsideUsers** значение «False» ($False):</span><span class="sxs-lookup"><span data-stu-id="070c8-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


