---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Доверенным приложением является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103165"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="31aa6-103">Управление доверенными приложениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="31aa6-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="31aa6-104">Доверенным *приложением* является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="31aa6-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="31aa6-105">Подробные сведения о приложениях UCMA см. в материале "Объединенные коммуникации управляемый API 3.0 Core SDK https://go.microsoft.com/fwlink/p/?linkId=210320 Documentation".</span><span class="sxs-lookup"><span data-stu-id="31aa6-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="31aa6-106">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="31aa6-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="31aa6-107">В этой статье вы узнаете, как настроить новый надежный сервер приложений, просмотреть список доверенных приложений и просмотреть доверенные сведения о приложениях.</span><span class="sxs-lookup"><span data-stu-id="31aa6-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="31aa6-108">Настройка нового доверенного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="31aa6-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="31aa6-109">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="31aa6-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="31aa6-110">Начните строитель топологии: нажмите кнопку **Начните,** нажмите кнопку Все **программы,** **щелкните Skype для** бизнес-сервера, а затем нажмите Skype для **бизнес-сервера Топология Строитель**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="31aa6-111">Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="31aa6-112">В **диалоговом окне Сохранить** топологию как диалоговое окно щелкните файл Topology Builder, который необходимо использовать, а затем нажмите **кнопку Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="31aa6-113">В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="31aa6-114">В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="31aa6-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="31aa6-115">На **следующей странице "Выберите переход"** из списка выберите пул переднего конца Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="31aa6-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="31aa6-116">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="31aa6-117">Выберите верхний узел **Skype для бизнес-сервера,** а затем из меню **Действия** нажмите **кнопку Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="31aa6-118">Пул **доверенных приложений** должен был быть создан успешно и связан с правильным пулом переднего конца.</span><span class="sxs-lookup"><span data-stu-id="31aa6-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="31aa6-119">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="31aa6-119">View a list of trusted applications</span></span>

<span data-ttu-id="31aa6-120">Панель управления Skype для бизнес-серверов можно использовать для просмотра списка доверенных приложений, развернутых в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="31aa6-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="31aa6-121">Доверенным приложением является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="31aa6-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="31aa6-122">В списке ниже приведены сведения об этом отношении доверия.</span><span class="sxs-lookup"><span data-stu-id="31aa6-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="31aa6-123">Доверенные приложения не оспариваются для проверки подлинности с помощью Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="31aa6-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="31aa6-124">Доверенные приложения не являются регулированием с помощью Skype для бизнес-сервера для SIP-транзакций, подключений или исходяющих вызовов голосовой связи по протоколу Интернета (VoIP).</span><span class="sxs-lookup"><span data-stu-id="31aa6-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="31aa6-125">Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.</span><span class="sxs-lookup"><span data-stu-id="31aa6-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="31aa6-126">Доверенные приложения устойчивы и надежны.</span><span class="sxs-lookup"><span data-stu-id="31aa6-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="31aa6-127">В панели управления Skype для бизнес-серверов можно увидеть имя приложений, пул, в котором они работают, и порт, который они используют.</span><span class="sxs-lookup"><span data-stu-id="31aa6-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="31aa6-128">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="31aa6-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="31aa6-129">Из учетной записи пользователя, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или роли CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="31aa6-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="31aa6-130">Сведения о предопределеных административных ролях, доступных в Skype для бизнеса Server, см. в материале [Role-based access control (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)</span><span class="sxs-lookup"><span data-stu-id="31aa6-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="31aa6-131">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="31aa6-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="31aa6-132">В левой панели навигации щелкните **Топология** и нажмите кнопку **Доверенные приложения**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="31aa6-133">На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="31aa6-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="31aa6-134">Просмотр доверенных сведений о приложениях</span><span class="sxs-lookup"><span data-stu-id="31aa6-134">View trusted application information</span></span>

<span data-ttu-id="31aa6-135">Сведения о доверенных приложениях можно просматривать с помощью Windows PowerShell **и cmdlet Get-CsTrustedApplication.**</span><span class="sxs-lookup"><span data-stu-id="31aa6-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="31aa6-136">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31aa6-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="31aa6-137">Просмотр доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="31aa6-137">To view trusted applications</span></span>

<span data-ttu-id="31aa6-138">Чтобы просмотреть все доверенные приложения, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="31aa6-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="31aa6-139">Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:</span><span class="sxs-lookup"><span data-stu-id="31aa6-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="31aa6-140">Дополнительные сведения см. в разделе [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="31aa6-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>