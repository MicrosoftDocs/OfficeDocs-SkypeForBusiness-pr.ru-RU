---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Надежное приложение — это приложение, основанное на интерфейсе API единой системы обмена сообщениями (УКМА 3,0), который является надежным для Microsoft Skype для бизнеса Server.
ms.openlocfilehash: b2a257ad197d573beccb187ef49e41b3864c1a58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817080"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="34121-103">Управление доверенными приложениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="34121-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="34121-104">*Надежное приложение* — это приложение, основанное на интерфейсе API единой системы обмена сообщениями (УКМА 3,0), который является надежным для Microsoft Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="34121-105">Подробнее об УКМА приложениях можно найти в http://go.microsoft.com/fwlink/p/?linkId=210320разделе "управляемая унифицированная связь API 3,0 Core SDK".</span><span class="sxs-lookup"><span data-stu-id="34121-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="34121-106">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов Рткуниверсалсерверадминс и domain.</span><span class="sxs-lookup"><span data-stu-id="34121-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="34121-107">В этой статье рассказывается о том, как настроить новый доверенный сервер приложений, просмотреть список надежных приложений и просмотреть сведения о доверенных приложениях.</span><span class="sxs-lookup"><span data-stu-id="34121-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="34121-108">Настройка нового доверенного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="34121-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="34121-109">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="34121-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="34121-110">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а **затем —** **Построитель топологии Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="34121-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="34121-111">Выберите пункт **топология скачивания из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="34121-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="34121-112">В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологии, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="34121-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="34121-113">На левой панели щелкните правой кнопкой мыши **Доверенные серверы приложений**и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="34121-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="34121-114">Введите **полное доменное имя пула** для доверенного пула приложений, укажите, будет ли он одним или несколькими серверами, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34121-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="34121-115">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="34121-116">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="34121-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="34121-117">Выберите верхний узел в **Skype для бизнеса Server**, а затем в меню **действия** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="34121-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="34121-118">**Надежное приложение пула приложений** должно быть успешно создано и связано с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="34121-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="34121-119">Просмотр списка надежных приложений</span><span class="sxs-lookup"><span data-stu-id="34121-119">View a list of trusted applications</span></span>

<span data-ttu-id="34121-120">Вы можете использовать панель управления Skype для бизнеса Server для просмотра списка доверенных приложений, которые вы развернули в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="34121-121">Надежное приложение — это приложение, основанное на интерфейсе API единой системы обмена сообщениями (УКМА 3,0), который является надежным для Microsoft Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="34121-122">Это отношение доверия представлено в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="34121-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="34121-123">Доверенные приложения не предназначены для проверки подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="34121-124">Доверенные приложения не заменяются в Skype для бизнеса Server для транзакций SIP, подключений и исходящих голосовых вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="34121-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="34121-125">Доверенные приложения могут олицетворять любого пользователя и могут присоединиться к конференциям без отображения в списке.</span><span class="sxs-lookup"><span data-stu-id="34121-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="34121-126">Доверенные приложения являются высокодоступными и устойчивыми.</span><span class="sxs-lookup"><span data-stu-id="34121-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="34121-127">На панели управления сервера Skype для бизнеса можно просмотреть названия приложений, пула, в котором они выполняются, и используемого ими порта.</span><span class="sxs-lookup"><span data-stu-id="34121-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="34121-128">Просмотр списка надежных приложений</span><span class="sxs-lookup"><span data-stu-id="34121-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="34121-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="34121-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="34121-130">Подробные сведения о предопределенных административных ролях, доступных в Skype для бизнеса Server, можно найти в разделе [Управление доступом на основе ролей (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="34121-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="34121-131">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="34121-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="34121-132">На панели навигации слева щелкните **топология**и выберите пункт **доверенное приложение**.</span><span class="sxs-lookup"><span data-stu-id="34121-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="34121-133">На странице **Trusted Application (доверенное приложение** ) щелкните заголовок столбца, чтобы отсортировать приложения, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="34121-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="34121-134">Просмотр сведений о доверенном приложении</span><span class="sxs-lookup"><span data-stu-id="34121-134">View trusted application information</span></span>

<span data-ttu-id="34121-135">Вы можете просматривать сведения о доверенных приложениях с помощью Windows PowerShell и командлета **Get-кструстедаппликатион** .</span><span class="sxs-lookup"><span data-stu-id="34121-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="34121-136">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34121-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="34121-137">Просмотр надежных приложений</span><span class="sxs-lookup"><span data-stu-id="34121-137">To view trusted applications</span></span>

<span data-ttu-id="34121-138">Чтобы просмотреть все надежные приложения, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="34121-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="34121-139">Эта команда возвращает данные, подобные приведенным ниже, для каждого надежного приложения.</span><span class="sxs-lookup"><span data-stu-id="34121-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="34121-140">Подробности можно найти в [статьях Get-кструстедаппликатион](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="34121-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
