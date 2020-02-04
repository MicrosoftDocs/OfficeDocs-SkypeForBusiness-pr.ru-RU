---
title: 'Lync Server 2013: управление политикой внешнего доступа для организации'
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
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="08282-102">Управление политикой внешнего доступа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08282-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="08282-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="08282-104">После развертывания одного или нескольких пограничных серверов необходимо включить типы внешних возможностей доступа, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="08282-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="08282-105">По умолчанию политики не настроены для поддержки внешнего доступа пользователей, включая удаленный доступ пользователей, доступ федеративных пользователей, даже если вы уже включили поддержку внешних пользователей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="08282-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="08282-106">Чтобы управлять использованием внешнего доступа пользователей, необходимо настроить одну или несколько политик, указав тип доступа внешних пользователей, которые поддерживаются для каждой политики.</span><span class="sxs-lookup"><span data-stu-id="08282-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="08282-107">Для создания и настройки доступны следующие области политики.</span><span class="sxs-lookup"><span data-stu-id="08282-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="08282-108">По умолчанию создается глобальная политика, но ее невозможно удалить.</span><span class="sxs-lookup"><span data-stu-id="08282-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="08282-109">**Глобальная политика**   . Глобальная политика создается при развертывании пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="08282-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="08282-110">По умолчанию в глобальной политике не включены параметры доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="08282-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="08282-111">Для поддержки внешнего доступа пользователей на глобальном уровне вы можете настроить глобальную политику для поддержки одного или нескольких типов внешних параметров доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="08282-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="08282-112">Глобальная политика применяется ко всем пользователям в Организации, но политики сайтов и политики пользователей переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="08282-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="08282-113">Если вы удалите глобальную политику, она не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="08282-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="08282-114">Вместо этого вы восстанавливаете значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08282-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="08282-115">**Политика сайта.**   вы можете создать и настроить одну или несколько политик сайта для ограничения поддержки внешних пользователей для доступа к определенным сайтам.</span><span class="sxs-lookup"><span data-stu-id="08282-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="08282-116">Конфигурация в политике сайта переопределяет глобальную политику, но только для сайта, к которому применяется эта политика.</span><span class="sxs-lookup"><span data-stu-id="08282-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="08282-117">Например, если вы разрешите удаленному пользователю доступ в глобальной политике, вы можете указать политику сайта, запрещающую доступ удаленных пользователей для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="08282-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="08282-118">По умолчанию политика сайта применяется ко всем пользователям этого сайта, но вы можете назначить пользователю политику, чтобы перекрыть параметр политики сайта.</span><span class="sxs-lookup"><span data-stu-id="08282-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="08282-119">**Политика пользователей вы**   можете создать и настроить одну или несколько политик пользователей для ограничения поддержки доступа удаленных пользователей к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="08282-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="08282-120">Конфигурация политики пользователя переопределяет глобальную политику и ее сайта, но только для определенных пользователей, которым назначена политика пользователя.</span><span class="sxs-lookup"><span data-stu-id="08282-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="08282-121">Например, если вы разрешите удаленному пользователю доступ в глобальной политике и в политике сайта, вы можете указать политику пользователей, запрещающую доступ к удаленному пользователю, а затем назначить эту политику пользователей конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="08282-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="08282-122">Если вы создаете политику пользователя, необходимо применить ее для одного или нескольких пользователей, прежде чем она вступит в силу.</span><span class="sxs-lookup"><span data-stu-id="08282-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08282-123">Параметры политики сервера Lync Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="08282-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="08282-124">Приоритет политики Lync Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="08282-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="08282-125">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="08282-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="08282-126">К этим параметрам относятся следующие типы внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="08282-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="08282-127">**Включите связь с федеративными пользователями**   . Включите этот параметр, если вы хотите поддерживать доступ пользователей к доменам федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="08282-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="08282-128">Этот параметр настраивает возможность взаимодействия пользователей с другими федеративными доменами SIP, а также внутрипроцессные поставщики, такие как Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="08282-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="08282-129">Выберите этот параметр, чтобы разрешить связь с федеративными доменами КСМПП.</span><span class="sxs-lookup"><span data-stu-id="08282-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="08282-130">Вы можете выбрать параметр **включить связь с федеративными партнерами КСМПП** , если сначала выбрать параметр **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="08282-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="08282-131">КСМПП Федерация — это Федерация организаций, использующих протокол расширенного обмена сообщениями и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="08282-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08282-132">Если включить федерацию КСМПП, необходимо также выбрать развертывание <STRONG>КСМПП Federation</STRONG> в разделе "конфигурация пулов Edge Builder" построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="08282-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="08282-133">Настройка для Федерации КСМПП развертывает прокси-сервер КСМПП на пограничном сервере и шлюз КСМПП на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="08282-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="08282-134">**Включение связи с удаленными пользователями**   . Включите этот параметр, если вы хотите, чтобы пользователи в вашей организации, находящиеся за пределами вашего брандмауэра, например абонентами удаленного доступа или удаленными пользователями, смогли подключиться к серверу Lync через Интернет.</span><span class="sxs-lookup"><span data-stu-id="08282-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="08282-135">**Включение связи с общедоступными пользователями**   . Включите этот параметр, если вы хотите, чтобы внутренние пользователи могли общаться с контактами общедоступной службы обмена мгновенными сообщениями\!, например предоставленными Windows Live, Yahoo и America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="08282-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="08282-136">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="08282-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="08282-137">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="08282-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="08282-138">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="08282-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="08282-139">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="08282-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="08282-140">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="08282-140">has been announced.</span></span> <span data-ttu-id="08282-141">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="08282-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="08282-142">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="08282-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="08282-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="08282-143">Messenger.</span></span> <span data-ttu-id="08282-144">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="08282-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="08282-145">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="08282-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="08282-146">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="08282-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="08282-147">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="08282-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="08282-148">Помимо включения поддержки внешних пользователей, необходимо также настроить политики для управления доступом внешних пользователей в Организации, прежде чем любой тип внешних пользователей будет доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="08282-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="08282-149">Дополнительные сведения о создании, настройке и применении политик внешних пользователей можно найти в разделе <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="08282-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="08282-150">**Просмотр политик внешнего доступа с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="08282-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="08282-151">Вы можете просматривать политики внешнего доступа с помощью командной консоли Lync Server Management Shell и командлета **Get-ксекстерналакцессполици** .</span><span class="sxs-lookup"><span data-stu-id="08282-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="08282-152">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08282-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="08282-153">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08282-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="08282-154">Чтобы просмотреть сведения обо всех политиках внешнего доступа, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="08282-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="08282-155">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="08282-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="08282-156">Содержание</span><span class="sxs-lookup"><span data-stu-id="08282-156">In This Section</span></span>

  - [<span data-ttu-id="08282-157">Настройка политик управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="08282-158">Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="08282-159">Настройка политик для управления удаленным доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="08282-160">Конфигурация политик для управления общим доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="08282-161">Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="08282-162">Сброс или удаление политик доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08282-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

