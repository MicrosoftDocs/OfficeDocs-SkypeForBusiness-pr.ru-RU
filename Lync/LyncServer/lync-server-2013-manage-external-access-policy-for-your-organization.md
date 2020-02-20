---
title: 'Lync Server 2013: Управление политикой внешнего доступа для Организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37395879164509b35a5d04896f29c41a658fb857
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="1f800-102">Управление политикой внешнего доступа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f800-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1f800-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1f800-104">После развертывания одного или нескольких пограничных серверов необходимо включить типы внешнего доступа, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1f800-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="1f800-p101">По умолчанию нет настроенных политик для поддержки доступа внешних пользователей, включая доступ удаленных пользователей и доступ федеративных пользователей, даже если доступ внешних пользователей уже включен в организации. Чтобы управлять использованием внешнего доступа пользователей, необходимо настроить одну или несколько политик, указывая тип внешнего доступа пользователей, поддерживаемого каждой политикой. Для создания и настройки доступны перечисленные ниже области действия политик. По умолчанию созданная глобальная политика не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="1f800-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="1f800-109">**Глобальная политика**   Глобальная политика создается при развертывании пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="1f800-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="1f800-110">По умолчанию в глобальной политике нет включенных параметров доступа к внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="1f800-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="1f800-111">Для поддержки доступа внешних пользователей на глобальном уровне необходимо настроить глобальную политику для поддержки одного или нескольких типов параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f800-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="1f800-112">Глобальная политика применяется ко всем пользователям в Организации, но политики сайтов и политики пользователей переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="1f800-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="1f800-113">Если вы удалите глобальную политику, она не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="1f800-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="1f800-114">Вместо этого вы восстанавливаете значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1f800-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="1f800-115">**Политика сайта.**   вы можете создать и настроить одну или несколько политик сайта, чтобы ограничить поддержку доступа внешних пользователей к определенным сайтам.</span><span class="sxs-lookup"><span data-stu-id="1f800-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="1f800-116">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="1f800-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="1f800-117">Например, если в глобальной политике включен доступ удаленных пользователей, можно задать политику сайта, которая отключает доступ удаленных пользователей для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="1f800-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="1f800-118">По умолчанию политика сайта применяется ко всем пользователям этого сайта, но можно назначать пользователю политику пользователя, чтобы переопределить политику сайта для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f800-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="1f800-119">**Политика пользователя вы**   можете создать и настроить одну или несколько политик пользователей, чтобы ограничить поддержку доступа удаленных пользователей к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="1f800-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="1f800-120">Конфигурация в политике пользователя переопределяет глобальную политику и политику сайта, но только для тех пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="1f800-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="1f800-121">Например, если в глобальной политике и в политике сайта включен доступ удаленных пользователей, можно задать политику пользователя, которая отключает доступ удаленных пользователей, и назначить эту политику конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="1f800-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="1f800-122">Если создается политика пользователя, то чтобы она начала действовать, ее необходимо назначить хотя бы одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="1f800-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f800-123">Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="1f800-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1f800-124">Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="1f800-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1f800-125">Это означает, что параметр политики ближе к объекту, на который влияет политика, чем больше влияет на объект.</span><span class="sxs-lookup"><span data-stu-id="1f800-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="1f800-126">Эти параметры включают следующие типы внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="1f800-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="1f800-127">**Разрешить взаимодействие с федеративными пользователями**   это можно сделать, если вы хотите обеспечить доступ пользователей к доменам федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="1f800-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="1f800-128">Этот параметр позволяет пользователям связываться с другими федеративными доменами SIP, а также с размещенными поставщиками, такими как Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f800-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="1f800-129">Выбор этого параметра позволяет выбрать возможность связи с федеративными доменами XMPP.</span><span class="sxs-lookup"><span data-stu-id="1f800-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="1f800-p107">Параметр **Разрешить взаимодействие с федеративными пользователями XMPP** доступен для выбора, если уже выбран параметр **Разрешить взаимодействие с федеративными пользователями**. Федерация XMPP — это федерация с организациями, использующими протокол XMPP.</span><span class="sxs-lookup"><span data-stu-id="1f800-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f800-132">Если включена Федерация XMPP, необходимо также выбрать развертывание <STRONG>Федерации XMPP</STRONG> в разделе Конфигурация пограничных пулов построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="1f800-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="1f800-133">Настройка для Федерации XMPP развертывает прокси-сервер XMPP на пограничном сервере и шлюз XMPP на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f800-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="1f800-134">**Разрешить взаимодействие с удаленными пользователями**   включите этот параметр, чтобы пользователи в Организации, находящиеся за пресылаемым брандмауэром, такие как удаленные пользователи и пользователи, которые находятся в поездках, могли подключаться к Lync Server через Интернет.</span><span class="sxs-lookup"><span data-stu-id="1f800-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="1f800-135">**Разрешить взаимодействие с общедоступными пользователями**   включите этот параметр, чтобы внутренние пользователи могли общаться с контактами общедоступных служб обмена мгновенными сообщениями, например, предоставляемые\!Windows Live, Yahoo и America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="1f800-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="1f800-136">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="1f800-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1f800-137">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1f800-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1f800-138">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="1f800-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="1f800-139">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1f800-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1f800-140">объявлено.</span><span class="sxs-lookup"><span data-stu-id="1f800-140">has been announced.</span></span> <span data-ttu-id="1f800-141">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1f800-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1f800-142">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1f800-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1f800-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="1f800-143">Messenger.</span></span> <span data-ttu-id="1f800-144">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="1f800-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1f800-145">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="1f800-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1f800-146">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="1f800-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1f800-147">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="1f800-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="1f800-148">Помимо включения поддержки внешнего доступа пользователей, необходимо также настроить политики для управления использованием внешнего доступа пользователей в организации до того, как любой из типов внешнего доступа станет доступным пользователям.</span><span class="sxs-lookup"><span data-stu-id="1f800-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="1f800-149">Сведения о создании, настройке и применении политик для доступа внешних пользователей см в разделе <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение или отключение удаленного доступа пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1f800-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1f800-150">**Просмотр политик внешнего доступа с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1f800-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="1f800-151">Для просмотра политик внешнего доступа можно использовать командную консоль Lync Server и командлет **Get – CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="1f800-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="1f800-152">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f800-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1f800-153">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="1f800-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="1f800-154">Чтобы просмотреть сведения обо всех политиках внешнего доступа, введите в командную консоль Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="1f800-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="1f800-155">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="1f800-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="1f800-156">Содержание</span><span class="sxs-lookup"><span data-stu-id="1f800-156">In This Section</span></span>

  - [<span data-ttu-id="1f800-157">Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="1f800-158">Настройка политик для управления доступом федеративных пользователей XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="1f800-159">Настройка политик для управления удаленным доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="1f800-160">Настройка политик для управления доступом открытых пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="1f800-161">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="1f800-162">Сброс или удаление политик доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f800-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

