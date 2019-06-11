---
title: 'Lync Server 2013: включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="a5e6b-102">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5e6b-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5e6b-103">_**Тема последнего изменения:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="a5e6b-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="a5e6b-104">Поддержка Федерации необходима для предоставления пользователям, у которых есть учетная запись с надежной организацией клиента или партнера, включая домены партнера и пользователей поставщика общедоступных мгновенных сообщений, которые поддерживаются для совместной работы пользователей всей.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="a5e6b-105">Кроме того, для предоставления голосовой почты пользователям корпоративной голосовой связи, почтовые ящики которых находятся в размещенной службе Exchange, например Microsoft Exchange Online, необходимо также использовать поставщик размещенной службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="a5e6b-106">Если вы установили отношение доверия с внешними доменами, вы можете авторизовать пользователей в этих доменах для доступа к развертыванию и участия в связи с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="a5e6b-107">Это отношение доверия называется федерациям и не связано с отношением доверия Active Directory или зависимым от него.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="a5e6b-108">Для поддержки доступа пользователей федеративных доменов необходимо включить федерацию.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="a5e6b-109">Если вы включите Федерацию для своей организации, необходимо также указать, следует ли реализовать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a5e6b-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="a5e6b-110">**Включение обнаружения**   домена партнера если этот параметр включен, Lync Server использует записи DNS для обнаружения доменов, не указанных в списке разрешенные домены, автоматическая оценка входящего трафика от обнаруженных федеративных а также ограничивать или блокировать трафик на основании уровня доверия, количества трафика и параметров администратора.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="a5e6b-111">Если этот флажок не установлен, для пользователей из доменов, включенных в список разрешенных доменов, будет разрешен доступ федеративного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="a5e6b-112">Если вы выберете этот параметр, вы можете указать, что отдельные домены должны быть заблокированы или разрешены, включая ограничение доступа к определенным серверам, на которых запущена служба EDGE в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="a5e6b-113">Подробнее об управлении доступом с помощью федеративных доменов можно узнать [в разделе Настройка поддержки разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="a5e6b-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="a5e6b-114">**Отправить заявление об отказе на архивацию по**     уведомлению об отказе федеративных партнеров, которое отправляется федеративным партнерам, которые заархивированы в развертывании.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="a5e6b-115">Если вы поддерживаете архивацию внешней связи с доменами федеративных партнеров, включите уведомление об отказе в архивацию, чтобы предупредить партнеров о том, что их сообщения архивируются.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="a5e6b-116">Если в дальнейшем вы захотите временно запретить доступ пользователям федеративных доменов, вы можете отключить федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="a5e6b-117">В этом разделе описана процедура включения и отключения федеративного доступа пользователей для Организации, в том числе указание параметров интеграции, которые будут поддерживаться для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5e6b-118">Включение Федерации для вашей организации указывает на то, что серверы, на которых работает служба EDGE, поддерживают маршрутизацию на федеративные домены.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="a5e6b-119">Пользователи федеративных доменов не могут принимать участие в СООБЩЕНИЯх и конференциях в вашей организации, пока не будет настроена хотя бы одна политика для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="a5e6b-120">Пользователи общедоступных служб обмена мгновенными сообщениями не могут принимать участие в СООБЩЕНИЯх и конференциях в вашей организации, пока не будет настроена хотя бы одна политика для поддержки подключения к общедоступной службе</span><span class="sxs-lookup"><span data-stu-id="a5e6b-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="a5e6b-121">Lync Server не может использовать размещенную службу Exchange для обеспечения ответа на звонки, голосового доступа к Outlook (в том числе голосовой почты) или служб автоматического ассистента для пользователей, чьи почтовые ящики находятся на размещенной службе Exchange, пока не настроена политика размещенной голосовой почты. , который предоставляет сведения о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="a5e6b-122">Дополнительные сведения о настройке политик связи с пользователями федеративных доменов в других организациях можно найти в разделе <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Управление федеративными доменами SIP для Организации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="a5e6b-123">Кроме того, если вы хотите поддерживать связь с пользователями поставщиков услуг обмена мгновенными сообщениями, необходимо настроить политики для ее поддержки, а также настроить поддержку отдельных поставщиков услуг, которые будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="a5e6b-124">Дополнительные сведения можно найти <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">в разделе Управление поставщиками служб SIP для вашей организации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="a5e6b-125">Дополнительные сведения о создании политики размещенной голосовой почты можно найти <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">в разделе Управление политиками голосовой почты в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="a5e6b-126">Включение и отключение федеративного доступа пользователей для Организации</span><span class="sxs-lookup"><span data-stu-id="a5e6b-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="a5e6b-127">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5e6b-128">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a5e6b-129">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a5e6b-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a5e6b-130">На панели навигации слева выберите элемент **внешний доступ к пользователю**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a5e6b-131">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a5e6b-132">В окне **изменение конфигурации Edge Access**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="a5e6b-133">Чтобы включить Федеративные разрешения для пользователей в Организации, установите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="a5e6b-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="a5e6b-134">Чтобы отключить федеративного доступа пользователей для вашей организации, снимите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="a5e6b-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="a5e6b-135">Если установлен флажок **включить связь с федеративными пользователями** , выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="a5e6b-136">Если вы хотите поддерживать автоматическое обнаружение доменных партнеров, установите флажок **включить обнаружение доменов для партнеров** .</span><span class="sxs-lookup"><span data-stu-id="a5e6b-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="a5e6b-137">Если в вашей организации поддерживается архивация внешней связи, установите флажок **отправлять отказ от ответственности федеративным партнерам** .</span><span class="sxs-lookup"><span data-stu-id="a5e6b-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="a5e6b-138">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-138">Click **Commit**.</span></span>

<span data-ttu-id="a5e6b-139">Чтобы включить Федеративные пользователи для совместной работы с пользователями в среде Lync Server 2013, необходимо настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="a5e6b-140">Подробности можно найти в разделе [Настройка политик для управления доступом к федеративным пользователям в Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="a5e6b-141">Для управления доступом к определенным федеративным доменам ознакомьтесь со сведениями [Настройка поддержки разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5e6b-142">Включение и отключение служб федерации и общедоступных мгновенных сообщений с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5e6b-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5e6b-143">Кроме того, с помощью Windows PowerShell и командлета Set-Ксакцесседжеконфигуратион можно управлять подключением Федерации и общедоступной службы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="a5e6b-144">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5e6b-145">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5e6b-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="a5e6b-146">Включение подключения к службам федерации и общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="a5e6b-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="a5e6b-147">Чтобы включить функцию подключения к службам федерации и общедоступного обмена мгновенными сообщениями, установите для свойства **алловфедератедусерс** значение True ($true):</span><span class="sxs-lookup"><span data-stu-id="a5e6b-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="a5e6b-148">Отключение служб федерации и общедоступной службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="a5e6b-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="a5e6b-149">Чтобы отключить соединение Федерации и общедоступную службу обмена мгновенными сообщениями, установите для свойства **алловфедератедусерс** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="a5e6b-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

