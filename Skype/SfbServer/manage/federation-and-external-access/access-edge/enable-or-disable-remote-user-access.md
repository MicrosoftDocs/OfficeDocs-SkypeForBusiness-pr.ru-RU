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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: При включении удаленного доступа пользователей для удаленных пользователей, поддерживаемых пользователей удаленного подключения через Интернет и не нужно подключиться, используя VPN работать с внутренними пользователями с помощью Скайп for Business Server.
ms.openlocfilehash: 7586d6af408c4f6dd6290ccf1fc9f19dbc23a87e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919477"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="c9e3c-103">Включение и отключение удаленного доступа пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c9e3c-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="c9e3c-104">Удаленные пользователи — пользователей в вашей организации, имеющих сохраняемого удостоверения Active Directory в рамках организации.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="c9e3c-105">Удаленные пользователи часто войдите в Скайп для Business Server из за пределами сети с помощью виртуальной частной сети (VPN), когда они не подключены к сети организации.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="c9e3c-106">Удаленные пользователи включают сотрудники, работающие дома или на дорогу и других удаленных сотрудников, таких как надежных поставщиков пользователей, которые были предоставлены учетные данные предприятия.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="c9e3c-107">При включении удаленного доступа пользователей для удаленных пользователей, поддерживаемых пользователей удаленного подключения через Интернет и не нужно подключиться, используя VPN работать с внутренними пользователями с помощью Скайп for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="c9e3c-108">Для поддержки доступа удаленных пользователей, необходимо включить удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="c9e3c-109">При включении удаленного доступа пользователей, можно включить для всей организации.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="c9e3c-110">Если позднее вы хотите временно или окончательно запретить доступ удаленных пользователей, его можно отключить для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="c9e3c-111">Используйте описанную в этом разделе для включения или отключения удаленного доступа пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="c9e3c-112">Включение удаленного доступа пользователей только указывает, что серверы, где выполняется служба пограничного сервера доступа поддерживают коммуникации с удаленными пользователями, но только после настройки на удаленных пользователей не могут участвовать в обмен мгновенными сообщениями обмена Мгновенными сообщениями и конференции в вашей организации как минимум одну политику для управления использованием удаленного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="c9e3c-113">Скайп Business Server параметры политики, применяемые на одном уровне политики можно переопределить параметры, которые применяются на уровне другой политики.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c9e3c-114">— Это Скайп для определения приоритета Business Server: политика пользователя (большинство влияют на то) переопределяет политики сайта, а затем политика сайта переопределяет глобальную политику (как минимум влияют на то).</span><span class="sxs-lookup"><span data-stu-id="c9e3c-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c9e3c-115">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="c9e3c-116">Для получения дополнительных сведений о настройке политик для использования удаленного доступа пользователей видеть [Настройка политик для управления доступом удаленных пользователей в Скайп для Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c9e3c-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="c9e3c-117">Для включения или отключения удаленного доступа пользователей в вашей организации</span><span class="sxs-lookup"><span data-stu-id="c9e3c-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="c9e3c-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9e3c-119">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c9e3c-120">На левой панели навигации щелкните **Федерация и внешний доступ**, а затем щелкните **Конфигурация пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="c9e3c-121">На странице **Настройка пограничного доступа** щелкните **Глобальная**, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c9e3c-122">В **Изменить настройку пограничного доступа**выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e3c-123">Включение удаленного доступа пользователей в вашей организации, установите флажок **Включить доступ удаленных пользователей** .</span><span class="sxs-lookup"><span data-stu-id="c9e3c-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="c9e3c-124">Для отключения удаленного доступа пользователей в вашей организации, снимите флажок **Включить доступ удаленных пользователей** .</span><span class="sxs-lookup"><span data-stu-id="c9e3c-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="c9e3c-125">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-125">Click **Commit**.</span></span>

<span data-ttu-id="c9e3c-126">Предоставление внешним пользователям выполнить вход на серверы, где выполняется Скайп для Business Server, необходимо также настроить по крайней мере одной политики внешнего доступа для поддержки доступа удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="c9e3c-127">Дополнительные сведения см [Настройка политик для управления доступом удаленных пользователей в Скайп для Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c9e3c-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c9e3c-128">Включение или отключение удаленного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9e3c-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c9e3c-129">Доступ удаленных пользователей можно управлять с помощью командлета Set-CsAccessEdgeConfiguration и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c9e3c-130">Этот командлет можно запустить из Скайп оболочки управления Business Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9e3c-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="c9e3c-131">Включение удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="c9e3c-131">To enable remote user access</span></span>

  - <span data-ttu-id="c9e3c-132">Чтобы включить доступ удаленных пользователей, задайте значение свойства **AllowOutsideUsers** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="c9e3c-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="c9e3c-133">Для отключения удаленного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="c9e3c-133">To disable remote user access</span></span>

  - <span data-ttu-id="c9e3c-134">Чтобы отключить доступ удаленных пользователей, задайте значение свойства **AllowOutsideUsers** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="c9e3c-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


