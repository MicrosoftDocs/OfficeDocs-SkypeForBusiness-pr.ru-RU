---
title: Управление политикой внешнего доступа для организации
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
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
description: После развертывания одного или нескольких пограничных серверов необходимо включить типы внешнего доступа, которые будут поддерживаться организацией.
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817259"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="ef663-103">Управление политикой внешнего доступа для организации</span><span class="sxs-lookup"><span data-stu-id="ef663-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="ef663-104">После развертывания одного или нескольких пограничных серверов необходимо включить типы внешнего доступа, которые будут поддерживаться организацией.</span><span class="sxs-lookup"><span data-stu-id="ef663-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="ef663-p101">По умолчанию нет настроенных политик для поддержки доступа внешних пользователей, включая доступ удаленных пользователей и доступ федеративных пользователей, даже если доступ внешних пользователей уже включен в организации. Чтобы управлять использованием внешнего доступа пользователей, необходимо настроить одну или несколько политик, указывая тип внешнего доступа пользователей, поддерживаемого каждой политикой. Для создания и настройки доступны перечисленные ниже области действия политик. По умолчанию созданная глобальная политика не может быть удалена.</span><span class="sxs-lookup"><span data-stu-id="ef663-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="ef663-109">**Глобальная политика**   Глобальная политика создается при развертывании своих серверов.</span><span class="sxs-lookup"><span data-stu-id="ef663-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="ef663-110">По умолчанию в глобальной политике не включены параметры доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ef663-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="ef663-111">Чтобы обеспечить доступ внешних пользователей на глобальном уровне, настройте глобальную политику для поддержки одного или нескольких вариантов доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="ef663-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="ef663-112">Глобальная политика применяется ко всем пользователям в организации, но политики сайтов и политики пользователей переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="ef663-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="ef663-113">Если вы удаляете глобальную политику, она не исчезает.</span><span class="sxs-lookup"><span data-stu-id="ef663-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="ef663-114">Вместо этого восстанавливаются параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef663-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="ef663-115">**Политика сайта**   Можно создать и настроить одну или несколько политик сайта, чтобы ограничить поддержку доступа внешних пользователей к определенным сайтам.</span><span class="sxs-lookup"><span data-stu-id="ef663-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="ef663-116">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="ef663-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="ef663-117">Например, если в глобальной политике включен доступ удаленных пользователей, можно задать политику сайта, которая отключает доступ удаленных пользователей для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="ef663-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="ef663-118">По умолчанию политика сайта применяется ко всем пользователям этого сайта, но можно назначать пользователю политику пользователя, чтобы переопределить политику сайта для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef663-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="ef663-119">**Политика пользователя**   Вы можете создать и настроить одну или несколько политик пользователей, чтобы ограничить поддержку доступа удаленных пользователей определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="ef663-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="ef663-120">Конфигурация в политике пользователя переопределяет глобальную политику и политику сайта, но только для тех пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="ef663-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="ef663-121">Например, если в глобальной политике и в политике сайта включен доступ удаленных пользователей, можно задать политику пользователя, которая отключает доступ удаленных пользователей, и назначить эту политику конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="ef663-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="ef663-122">Если создается политика пользователя, то чтобы она начала действовать, ее необходимо назначить хотя бы одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="ef663-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="ef663-123">Параметры политики, применяемые на уровне одной политики, могут переопределять параметры, применяемые на уровне другой политики.</span><span class="sxs-lookup"><span data-stu-id="ef663-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ef663-124">Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние). </span><span class="sxs-lookup"><span data-stu-id="ef663-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ef663-125">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="ef663-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="ef663-126">Эти параметры включают следующие типы внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="ef663-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="ef663-127">**Включить взаимодействие с федеративными пользователями**   В этом случае вы хотите поддерживать доступ пользователей к федератным доменам партнеров.</span><span class="sxs-lookup"><span data-stu-id="ef663-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ef663-128">Этот параметр настраивает для пользователей возможность взаимодействовать с другими федератными доменами SIP, а также с поставщиками услуг hosted, например Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef663-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="ef663-129">**Включить взаимодействие с удаленными пользователями**   Включении этого параметра необходимо, чтобы пользователи в вашей организации, которые находятся за пределами брандмауэра, такие как телекоммуникационные метры и пользователи, которые находятся в командировке, могли подключаться к Skype для бизнеса Server через Интернет.</span><span class="sxs-lookup"><span data-stu-id="ef663-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="ef663-130">**Включить взаимодействие с общедоступными пользователями**   Этот параметр включается, если вы хотите, чтобы внутренние пользователи могли взаимодействовать с контактами общедоступных поставщиков услуг im.</span><span class="sxs-lookup"><span data-stu-id="ef663-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="ef663-131">Помимо включения поддержки внешнего доступа пользователей, необходимо также настроить политики для управления использованием внешнего доступа пользователей в организации до того, как любой из типов внешнего доступа станет доступным пользователям.</span><span class="sxs-lookup"><span data-stu-id="ef663-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ef663-132">Сведения о создании, настройке и применении политик внешнего доступа пользователей см. в статье [Включение или отключение удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ef663-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="ef663-133">**Просмотр политик внешнего доступа с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ef663-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ef663-134">Вы можете просматривать политики внешнего доступа, используя командную консоль Skype для бизнеса Server и командлет **Get-CsExternalAccessPolicy**.</span><span class="sxs-lookup"><span data-stu-id="ef663-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="ef663-135">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef663-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="ef663-136">Чтобы просмотреть сведения обо всех политиках внешнего доступа, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="ef663-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="ef663-137">Эта команда возвращает следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="ef663-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
