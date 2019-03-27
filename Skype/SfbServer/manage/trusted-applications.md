---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Доверенное приложение — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server.
ms.openlocfilehash: 3ca8621148a4b6ce3530f23a61312f63f3d3cd30
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882144"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="63746-103">Управление доверенными приложениями в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="63746-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="63746-104">*Доверенное приложение* — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="63746-105">Для получения дополнительных сведений о приложениях UCMA документации «единой Communications управляемых API 3.0 Core SDK» в http://go.microsoft.com/fwlink/p/?linkId=210320.</span><span class="sxs-lookup"><span data-stu-id="63746-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="63746-106">Для успешной публикации, включения или отключения топологии при добавлении или удалении роль сервера, необходимо войти в систему как пользователь, являющийся членом группы RTCUniversalServerAdmins и "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="63746-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="63746-107">Используйте эту статью, чтобы узнать, как для настройки нового сервера доверенных приложений, Просмотр списка доверенных приложений и просмотра сведений о доверенном приложении.</span><span class="sxs-lookup"><span data-stu-id="63746-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="63746-108">Настройка нового сервера доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="63746-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="63746-109">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="63746-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="63746-110">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для Business Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="63746-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="63746-111">Выберите **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="63746-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="63746-112">В диалоговом окне **Save Topology As** щелкните Topology Builder файл, который требуется использовать и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="63746-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="63746-113">В левой области щелкните правой кнопкой мыши **серверы доверенных приложений**и нажмите кнопку **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="63746-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="63746-114">Введите **Полное доменное имя пула** пула доверенных приложений, выберите, будет ли он будет одним или несколькими серверами и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="63746-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="63746-115">На странице **Выбор следующего прыжка** в списке выберите Скайп для пула переднего плана Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="63746-116">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="63746-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="63746-117">Выберите верхний узел **Скайп для Business Server**и затем в меню **действия** щелкните **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="63746-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="63746-118">Следует, **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="63746-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="63746-119">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="63746-119">View a list of trusted applications</span></span>

<span data-ttu-id="63746-120">Скайп для панели управления Business Server можно использовать для просмотра списка доверенных приложений, которые развернуты в вашей Скайп среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="63746-121">Доверенное приложение — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="63746-122">В списке ниже приведен этого отношения доверия:</span><span class="sxs-lookup"><span data-stu-id="63746-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="63746-123">К доверенным приложениям не требуется проходить проверки подлинности Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="63746-124">К доверенным приложениям не применяется регулирование Скайп для Business Server для транзакций SIP, подключений или исходящих вызовов по протоколу (VoIP).</span><span class="sxs-lookup"><span data-stu-id="63746-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="63746-125">Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.</span><span class="sxs-lookup"><span data-stu-id="63746-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="63746-126">Доверенные приложения устойчивы и надежны.</span><span class="sxs-lookup"><span data-stu-id="63746-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="63746-127">В Скайп для панели управления Business Server можно видеть имя приложения, пул, в котором оно выполняется и порт, которые они используют.</span><span class="sxs-lookup"><span data-stu-id="63746-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="63746-128">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="63746-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="63746-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="63746-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="63746-130">Для получения дополнительных сведений о предопределенные административные роли, доступные в Скайп для Business Server см [управления доступом на основе ролей (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="63746-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="63746-131">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="63746-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="63746-132">В левой панели навигации щелкните **Топология**и нажмите кнопку **Доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="63746-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="63746-133">На странице **Доверенное приложение** щелкните заголовок столбца, чтобы отсортировать приложения при необходимости.</span><span class="sxs-lookup"><span data-stu-id="63746-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="63746-134">Просмотр сведений о доверенном приложении</span><span class="sxs-lookup"><span data-stu-id="63746-134">View trusted application information</span></span>

<span data-ttu-id="63746-135">Можно просмотреть сведения о доверенных приложений с помощью командлета **Get-CsTrustedApplication** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63746-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="63746-136">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63746-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="63746-137">Просмотр доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="63746-137">To view trusted applications</span></span>

<span data-ttu-id="63746-138">Для просмотра всех доверенных приложений, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="63746-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="63746-139">Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:</span><span class="sxs-lookup"><span data-stu-id="63746-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="63746-140">Дополнительные сведения см [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="63746-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
