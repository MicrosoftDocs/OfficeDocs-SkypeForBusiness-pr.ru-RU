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
description: Доверенного приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826279"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="e5e4a-103">Управление доверенными приложениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5e4a-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="e5e4a-104">*Доверенного* приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="e5e4a-105">Подробные сведения о приложениях UCMA см. в подразделе "Документация по unified Communications Managed API 3.0 Core SDK" по этой https://go.microsoft.com/fwlink/p/?linkId=210320 теме.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="e5e4a-106">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="e5e4a-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="e5e4a-107">В этой статье вы узнаете, как настроить новый доверенный сервер приложений, просмотреть список доверенных приложений и просмотреть сведения о доверенных приложениях.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="e5e4a-108">Настройка нового сервера доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="e5e4a-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="e5e4a-109">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e5e4a-110">Запустите построитель топологий: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **Server"** и **"Построитель топологий Skype** для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="e5e4a-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="e5e4a-111">Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="e5e4a-112">В **диалоговом** окне "Сохранить топологию как" щелкните нужный файл построитель топологий и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e5e4a-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="e5e4a-113">В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="e5e4a-114">В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="e5e4a-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5e4a-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="e5e4a-116">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="e5e4a-117">Выберите верхний узел **Skype для бизнеса Server,** а затем в меню "Действия" щелкните **"Опубликовать топологию".** </span><span class="sxs-lookup"><span data-stu-id="e5e4a-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="e5e4a-118">Пул **доверенных приложений** должен быть успешно создан и связан с правильным пулом переднего входа.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="e5e4a-119">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="e5e4a-119">View a list of trusted applications</span></span>

<span data-ttu-id="e5e4a-120">Панель управления Skype для бизнеса Server можно использовать для просмотра списка доверенных приложений, развернутых в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="e5e4a-121">Доверенного приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="e5e4a-122">В списке ниже приведены сведения об этом отношении доверия.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="e5e4a-123">Доверенные приложения не будут подавлять заявки на проверку подлинности в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="e5e4a-124">Skype для бизнеса Server не отрегулжимает доверенные приложения для транзакций SIP, подключений и исходяющих вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="e5e4a-125">Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="e5e4a-126">Доверенные приложения устойчивы и надежны.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="e5e4a-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="e5e4a-128">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="e5e4a-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="e5e4a-129">Из учетной записи пользователя, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="e5e4a-130">Подробные сведения о предопределеных административных ролях, доступных в Skype для бизнеса Server, см. в средстве управления доступом на основе [ролей (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)</span><span class="sxs-lookup"><span data-stu-id="e5e4a-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="e5e4a-131">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="e5e4a-132">В левой панели навигации щелкните **"Топология"** и выберите **"Доверенного приложения".**</span><span class="sxs-lookup"><span data-stu-id="e5e4a-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="e5e4a-133">На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="e5e4a-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="e5e4a-134">Просмотр сведений о доверенных приложениях</span><span class="sxs-lookup"><span data-stu-id="e5e4a-134">View trusted application information</span></span>

<span data-ttu-id="e5e4a-135">Сведения о доверенных приложениях можно просмотреть с помощью Windows PowerShell и с помощью Windows PowerShell **Get-CsTrustedApplication.**</span><span class="sxs-lookup"><span data-stu-id="e5e4a-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="e5e4a-136">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5e4a-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="e5e4a-137">Просмотр доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="e5e4a-137">To view trusted applications</span></span>

<span data-ttu-id="e5e4a-138">Чтобы просмотреть все доверенные приложения, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="e5e4a-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="e5e4a-139">Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:</span><span class="sxs-lookup"><span data-stu-id="e5e4a-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="e5e4a-140">Дополнительные сведения см. в разделе [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="e5e4a-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
