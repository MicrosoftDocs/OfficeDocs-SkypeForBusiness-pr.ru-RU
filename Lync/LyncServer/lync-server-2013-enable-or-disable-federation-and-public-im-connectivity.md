---
title: 'Lync Server 2013: Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526796"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="e54df-102">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e54df-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e54df-103">_**Последнее изменение темы:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="e54df-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="e54df-104">Поддержка федерации требуется для того, чтобы пользователи с учетной записью доверенного клиента или партнерской организации, включая пользователей партнерских доменов и общедоступных поставщиков услуг обмена мгновенными сообщениями, могли работать совместно с пользователями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e54df-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="e54df-105">Федерация также необходима для использования поставщика размещенной службы Exchange, предоставляющего услуги голосовой почты пользователям корпоративной голосовой связи, почтовые ящики которых находятся в размещенной службе Exchange, такой как Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e54df-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="e54df-106">Когда вы установили отношение доверия с этими внешними доменами, вы можете авторизовать пользователей в этих доменах для доступа к развертыванию и участия в связи с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e54df-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="e54df-107">Такое отношение доверия называется федерацией; оно не связано с отношением доверия Active Directory и не зависит от него.</span><span class="sxs-lookup"><span data-stu-id="e54df-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="e54df-p102">Для поддержки доступа пользователей федеративных доменов необходимо включить федерацию. При включении федерации для организации необходимо указать, реализуются ли следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="e54df-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="e54df-110">**Включение обнаружения**     доменных партнеров Если этот параметр включен, Lync Server использует записи службы доменных имен (DNS) для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивая входящий трафик от обнаруженных федеративных партнеров и ограничивая или блокирующая трафик на основе уровня доверия, объема трафика и параметров администратора.</span><span class="sxs-lookup"><span data-stu-id="e54df-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="e54df-111">Если этот параметр не выбран, доступ будет разрешен только для федеративных пользователей из доменов, включенных в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="e54df-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="e54df-112">Независимо от выбора этого параметра можно указать отдельные домены, которые будут заблокированы или разрешены, включая ограничение доступа к конкретным серверам пограничной службы доступа в федеративном домене.</span><span class="sxs-lookup"><span data-stu-id="e54df-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="e54df-113">Сведения об управлении доступом с помощью федеративных доменов приведены [в статье Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="e54df-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="e54df-114">**Отправка заявления об отказе от архивации федеративным партнерам**     Уведомление об отказе отправляется федеративным партнерам, на которых выполняется архивация в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e54df-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="e54df-115">Если поддерживается архивация внешних контактов с доменами федеративных партнеров, необходимо включить отправку заявления об ограничении ответственности в связи с архивацией, чтобы предупредить партнеров, что их сообщения архивируются.</span><span class="sxs-lookup"><span data-stu-id="e54df-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="e54df-p105">Если позднее понадобится временно или постоянно запретить доступ пользователей федеративных доменов, можно отключить федерацию для организации. Используйте описанную в этом разделе процедуру для включения или отключения доступа федеративных пользователей в организации, включая указание подходящих параметров федерации, которые должны поддерживаться в организации.</span><span class="sxs-lookup"><span data-stu-id="e54df-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e54df-118">Включение федерации для организации определяет только то, что серверы пограничной службы доступа поддерживают маршрутизацию для федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="e54df-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="e54df-119">Пользователи из федеративных доменов не смогут участвовать в обмене мгновенными сообщениями или в конференциях в организации, пока не будет настроена хотя бы одна политика для поддержки доступа федеративных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e54df-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="e54df-120">Пользователи общедоступных поставщиков услуг обмена мгновенными сообщениями не смогут участвовать в обмене мгновенными сообщениями или в конференциях в организации, пока не будет настроена хотя бы одна политика для поддержки связи с общедоступными поставщиками услуг обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e54df-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="e54df-121">Lync Server не сможет использовать размещенную службу Exchange для поддержки служб автоответчика, голосового доступа к Outlook (включая голосовую почту) или автосекретаря для пользователей, почтовые ящики которых находятся в размещенной службе Exchange, пока не будет настроена политика маршрутизации размещенной голосовой почты, предоставляющая сведения о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e54df-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="e54df-122">Дополнительные сведения о настройке политик для связи с пользователями федеративных доменов в других организациях можно найти в статье <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Управление федеративными доменами SIP для Организации в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e54df-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="e54df-123">Кроме того, если необходима поддержка связи с пользователями поставщиков услуг обмена мгновенными сообщениями, следует настроить соответствующие политики поддержки, а также поддержку отдельных поставщиков услуг, которые должны поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="e54df-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="e54df-124">Дополнительные сведения см в статье <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage Федеративные поставщики SIP для вашей организации в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e54df-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="e54df-125">Дополнительные сведения о создании политики размещенной голосовой почты можно найти в статье <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage Hosted Voice Policy policys in Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e54df-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="e54df-126">Включение или отключение доступа федеративных пользователей для организации</span><span class="sxs-lookup"><span data-stu-id="e54df-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="e54df-127">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e54df-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e54df-128">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e54df-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e54df-129">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e54df-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e54df-130">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="e54df-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="e54df-131">На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="e54df-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e54df-132">В разделе **Изменить настройку пограничного доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e54df-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="e54df-133">Чтобы включить доступ федеративных пользователей для организации, установите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="e54df-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="e54df-134">Чтобы отключить доступ федеративных пользователей для организации, снимите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="e54df-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="e54df-135">Если флажок **Разрешить взаимодействие с федеративными пользователями** установлен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e54df-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="e54df-136">Если необходима поддержка автоматического обнаружения доменов партнеров, установите флажок **Разрешить обнаружение домена партнера**.</span><span class="sxs-lookup"><span data-stu-id="e54df-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="e54df-137">Если организация поддерживает архивацию внешних контактов, установите флажок **Отправить федеративным партнерам заявление об отказе относительно архивации**.</span><span class="sxs-lookup"><span data-stu-id="e54df-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="e54df-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e54df-138">Click **Commit**.</span></span>

<span data-ttu-id="e54df-139">Чтобы разрешить федеративным пользователям совместно работать с пользователями в развертывании Lync Server 2013, необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="e54df-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="e54df-140">Дополнительные сведения: [Настройка политик для управления доступом федеративных пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e54df-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="e54df-141">Чтобы управлять доступом для определенных федеративных доменов, ознакомьтесь со статьей [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e54df-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e54df-142">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e54df-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e54df-143">Кроме того, с помощью Windows PowerShell и командлета Set-CsAccessEdgeConfiguration можно управлять службой федерации и общедоступной службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e54df-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="e54df-144">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e54df-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e54df-145">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e54df-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="e54df-146">Включение Федерации и общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="e54df-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="e54df-147">Чтобы включить федерацию и связь с общедоступными поставщиками услуг обмена мгновенными сообщениями, задайте свойству **AllowFederatedUsers** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="e54df-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="e54df-148">Отключение Федерации и общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="e54df-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="e54df-149">Чтобы отключить федерацию и связь с общедоступными поставщиками услуг обмена мгновенными сообщениями, задайте свойству **AllowFederatedUsers** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="e54df-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

