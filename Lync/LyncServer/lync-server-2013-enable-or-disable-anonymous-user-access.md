---
title: 'Lync Server 2013: Включение или отключение анонимного доступа пользователей'
description: 'Lync Server 2013: Включение или отключение анонимного доступа пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca36cffc25cd31d057b00c22cb299c56cfd7b3c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544775"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="f4b88-103">Включение или отключение анонимного доступа пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b88-103">Enable or disable anonymous user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4b88-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f4b88-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f4b88-105">Анонимные пользователи — это пользователи, которые не имеют учетной записи в доменных службах Active Directory или в поддерживаемом федеративного домене, но могут быть приглашены удаленно участвовать в локальной конференции.</span><span class="sxs-lookup"><span data-stu-id="f4b88-105">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="f4b88-106">Разрешая анонимное участие в собраниях, вы позволяете анонимным пользователям (удостоверение которых подтверждено только ключом собрания или конференции) присоединяться к собраниям.</span><span class="sxs-lookup"><span data-stu-id="f4b88-106">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="f4b88-107">Для разрешения анонимного участия необходимо включить его в своей организации.</span><span class="sxs-lookup"><span data-stu-id="f4b88-107">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="f4b88-p102">Если позднее вам потребуется запретить анонимный доступ пользователей на временной или постоянной основе, вы можете отключить его в своей организации. Используйте приведенную здесь процедуру для включения и отключения анонимного доступа пользователей в своей организации.</span><span class="sxs-lookup"><span data-stu-id="f4b88-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4b88-110">Включив анонимный доступ пользователей для своей организации, вы просто указываете, что ваши серверы с пограничной службой доступа поддерживают анонимный доступ пользователей.</span><span class="sxs-lookup"><span data-stu-id="f4b88-110">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="f4b88-111">Анонимные пользователи не могут участвовать в собраниях вашей организации, пока вы не настроите хотя бы одну политику конференц-связи и не примените ее к одному или нескольким пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f4b88-111">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="f4b88-112">Приглашать анонимных пользователей на собрания могут только пользователи, которым назначена политика конференц-связи, настроенная для поддержки анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f4b88-112">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="f4b88-113">Дополнительные сведения о настройке политик конференц-связи для поддержки приглашения анонимных пользователей приведены <A href="lync-server-2013-conferencing-policies.md">в статье политики конференц-связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4b88-113">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="f4b88-114">Включение и отключение анонимного доступа пользователей в своей организации</span><span class="sxs-lookup"><span data-stu-id="f4b88-114">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="f4b88-115">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="f4b88-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4b88-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4b88-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4b88-117">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4b88-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4b88-118">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="f4b88-118">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f4b88-119">На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f4b88-119">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f4b88-120">В области **Изменение настройки пограничного доступа** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f4b88-120">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f4b88-121">Чтобы включить анонимный доступ пользователей для своей организации, установите флажок **Разрешить взаимодействие с анонимными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="f4b88-121">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="f4b88-122">Чтобы отключить анонимный доступ пользователей для своей организации, снимите флажок **Разрешить взаимодействие с анонимными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="f4b88-122">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="f4b88-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f4b88-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f4b88-124">Включение или отключение анонимного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4b88-124">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f4b88-125">Управлять доступом анонимных пользователей можно с помощью Windows PowerShell и командлета **Set – CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f4b88-125">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f4b88-126">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4b88-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f4b88-127">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f4b88-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="f4b88-128">Включение анонимного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="f4b88-128">To enable anonymous user access</span></span>

  - <span data-ttu-id="f4b88-129">Чтобы включить анонимный доступ пользователей, установите для свойства **AllowAnonymousUsers** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="f4b88-129">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="f4b88-130">Отключение анонимного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="f4b88-130">To disable anonymous user access</span></span>

  - <span data-ttu-id="f4b88-131">Чтобы отключить анонимный доступ пользователей, установите для свойства **AllowAnonymousUsers** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="f4b88-131">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4b88-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f4b88-132">See Also</span></span>


[<span data-ttu-id="f4b88-133">Справочник по параметрам политики конференц-связи для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b88-133">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

