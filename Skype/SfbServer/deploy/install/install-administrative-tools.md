---
title: Установка средств администрирования в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: Сводка. Узнайте, как установить средства администрирования, необходимые для установки Skype для бизнеса Server. Скачайте бесплатную пробную версию Skype для бизнеса Server в центре оценки Майкрософт по адресу https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018270"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="9e1b6-104">Установка средств администрирования в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9e1b6-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="9e1b6-105">**Сводка:** Узнайте, как установить средства администрирования, необходимые для установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="9e1b6-106">Скачайте бесплатную пробную версию Skype для бизнеса Server в центре оценки Майкрософт по адресу [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="9e1b6-107">Средства администрирования включают построитель топологий и панель управления.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="9e1b6-108">Средства администрирования должны быть установлены по крайней мере на одном сервере в топологии или в 64-разрядной рабочей станции управления с версией ОС Windows, поддерживаемой Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="9e1b6-109">Шаги с 1 по 5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="9e1b6-110">Однако шаги 6, 7 и 8 необходимо выполнять по порядку, а после шагов 1 – 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="9e1b6-111">Установка средств администрирования — шаг 3 из 8.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="9e1b6-113">Установка средств администрирования Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9e1b6-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="9e1b6-114">Установочный носитель для Skype для бизнеса Server обеспечивает гибкие возможности.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="9e1b6-115">При первом запуске Setup. exe единственными установленными инструментами являются Мастер развертывания Skype для бизнеса Server и Командная консоль Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9e1b6-116">Используя эти два средства, известные как основные компоненты, можно продолжить процесс установки, но они не предоставляют основные функции для общей среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="9e1b6-117">Мастер развертывания автоматически запускается после установки основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="9e1b6-118">Раздел мастера развертывания с названием **Установка средств администрирования** устанавливает построитель топологий Skype для бизнеса Server и панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9e1b6-119">Каждая среда Skype для бизнеса Server должна иметь по крайней мере один сервер с установленными средствами администрирования.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="9e1b6-120">Просмотрите видео шаги для **установки средств администрирования**:</span><span class="sxs-lookup"><span data-stu-id="9e1b6-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="9e1b6-121">Установка средств администрирования Skype для бизнеса Server с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="9e1b6-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="9e1b6-122">Вставьте установочный носитель Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="9e1b6-123">Если программа установки не запускается автоматически, дважды щелкните файл **Setup**.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="9e1b6-124">Для работы установочного носителя требуется Microsoft Visual C++.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="9e1b6-125">Появится диалоговое окно с вопросом, следует ли установить его.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="9e1b6-126">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="9e1b6-127">С помощью интеллектуальной установки, новой функции в Skype для бизнеса Server можно подключаться к Интернету, чтобы проверить наличие обновлений в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="9e1b6-128">Это позволяет улучшить работу, убедившись, что у вас есть самые последние обновления продукта во время установки.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="9e1b6-129">Нажмите кнопку **установить** , чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="9e1b6-130">Внимательно ознакомьтесь с лицензионным соглашением и, если вы согласны, установите флажок **я принимаю условия лицензионного соглашения**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="9e1b6-131">На сервере будут установлены основные компоненты Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="9e1b6-132">Основные компоненты состоят из следующих компонентов, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="9e1b6-134">**Мастер развертывания Skype для бизнеса Server** Программа развертывания, предоставляющая стартовый планшет для установки различных компонентов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="9e1b6-135">**Командная консоль Skype для бизнеса Server** Предварительно настроенная программа PowerShell, позволяющая администрировать Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="9e1b6-136">После завершения установки основных компонентов мастер развертывания Skype для бизнеса Server будет автоматически запущен, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Мастер развертывания Skype для бизнеса Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="9e1b6-138">Кроме основных компонентов, вам также потребуется установить построитель топологии Skype для бизнеса Server и панель управления Skype для бизнеса Server по крайней мере на одном сервере в среде.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="9e1b6-139">В мастере развертывания нажмите кнопку **установить средства администрирования** .</span><span class="sxs-lookup"><span data-stu-id="9e1b6-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="9e1b6-140">Чтобы начать установку, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="9e1b6-141">После завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="9e1b6-142">Теперь средства администрирования добавлены на сервер, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Средства администрирования Skype для бизнеса Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="9e1b6-144">**Построитель топологий Skype для бизнеса Server** Программа, используемая для построения и развертывания топологий, а затем для управления ими.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="9e1b6-145">**Панель управления Skype для бизнеса Server** Программа, используемая для администрирования установки.</span><span class="sxs-lookup"><span data-stu-id="9e1b6-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

