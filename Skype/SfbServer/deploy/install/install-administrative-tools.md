---
title: Установка средств администрирования в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Сводка. Узнайте, как установить средства администрирования, необходимые для установки Skype для бизнеса Server. Скачайте бесплатную пробную версия Skype для бизнеса Server в Центре оценки Майкрософт по https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ссылке:'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812109"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="03667-104">Установка средств администрирования в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="03667-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="03667-105">**Сводка:** Узнайте, как установить средства администрирования, необходимые для установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="03667-106">Скачайте бесплатную пробную версия Skype для бизнеса Server в Центре оценки Майкрософт по [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) ссылке:</span><span class="sxs-lookup"><span data-stu-id="03667-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="03667-107">Средства администрирования включают построитель топологий и панель управления.</span><span class="sxs-lookup"><span data-stu-id="03667-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="03667-108">Средства администрирования должны быть установлены по крайней мере на одном сервере в топологии или на 64-битной рабочей станции управления с версией ОС Windows, поддерживаемой Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="03667-109">Шаги 1-5 можно делать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="03667-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="03667-110">Однако шаги 6, 7 и 8 необходимо делать по порядку и после шагов с 1 по 5, как описано на схеме.</span><span class="sxs-lookup"><span data-stu-id="03667-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="03667-111">Установка средств администрирования — шаг 3 из 8.</span><span class="sxs-lookup"><span data-stu-id="03667-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="03667-113">Установка средств администрирования Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="03667-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="03667-114">Установок носителя для Skype для бизнеса Server обеспечивает гибкие возможности.</span><span class="sxs-lookup"><span data-stu-id="03667-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="03667-115">При первом запуске Setup.exe устанавливаются только мастер развертывания Skype для бизнеса Server и оболочка управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="03667-116">С помощью этих двух средств, известных как основные компоненты, можно продолжить процесс установки, но они не предоставляют основные функции для всей среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="03667-117">Мастер развертывания запускается автоматически после установки основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="03667-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="03667-118">В разделе мастера развертывания  "Установка средств администрирования" устанавливаются построитель топологий Skype для бизнеса Server и панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03667-119">В каждой среде Skype для бизнеса Server должен быть по крайней мере один сервер с установленными средствами администрирования.</span><span class="sxs-lookup"><span data-stu-id="03667-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="03667-120">Посмотрите видео по установке **средств администрирования:**</span><span class="sxs-lookup"><span data-stu-id="03667-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="03667-121">Установка средств администрирования Skype для бизнеса Server из мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="03667-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="03667-122">Вставка установного носителя Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="03667-123">Если установка не начинается автоматически, дважды щелкните **ее.**</span><span class="sxs-lookup"><span data-stu-id="03667-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="03667-124">Для запуска установного носителя требуется Microsoft Visual C++.</span><span class="sxs-lookup"><span data-stu-id="03667-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="03667-125">В диалоговом окне будет выявиться запрос на установку.</span><span class="sxs-lookup"><span data-stu-id="03667-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="03667-126">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="03667-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="03667-127">С помощью интеллектуальной установки, новой функции в Skype для бизнеса Server, вы можете подключиться к Интернету, чтобы проверить обновления во время установки.</span><span class="sxs-lookup"><span data-stu-id="03667-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="03667-128">Это обеспечивает более простое качество благодаря установке последних обновлений продукта.</span><span class="sxs-lookup"><span data-stu-id="03667-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="03667-129">Нажмите **кнопку** "Установить", чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="03667-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="03667-130">Внимательно просмотрите лицензионный договор и, если вы согласны, выберите "Я принимаю условия лицензионного соглашения" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="03667-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="03667-131">На сервере будут установлены основные компоненты Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="03667-132">Основные компоненты состоят из следующих компонентов, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="03667-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="03667-134">**Мастер развертывания Skype для бизнеса Server** Программа развертывания, которая предоставляет панель запуска для установки различных компонентов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="03667-135">**Skype для бизнеса Server Management Shell** Предварительно заданная программа PowerShell, которая позволяет администрирование Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="03667-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="03667-136">После завершения установки основных компонентов автоматически запустится мастер развертывания Skype для бизнеса Server, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="03667-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Мастер развертывания Skype для бизнеса Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="03667-138">Помимо основных компонентов, необходимо также установить построитель топологий Skype для бизнеса Server и панель управления Skype для бизнеса Server по крайней мере на одном сервере в среде.</span><span class="sxs-lookup"><span data-stu-id="03667-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="03667-139">Щелкните **"Установка средств администрирования"** в мастере развертывания.</span><span class="sxs-lookup"><span data-stu-id="03667-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="03667-140">Чтобы начать установку, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="03667-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="03667-141">После завершения установки нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="03667-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="03667-142">Средства администрирования теперь добавляются на сервер, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="03667-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Средства администрирования Skype для бизнеса Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="03667-144">**Построитель топологий Skype для бизнеса Server** Программа, используемая для создания, развертывания и управления topologies.</span><span class="sxs-lookup"><span data-stu-id="03667-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="03667-145">**Панель управления Skype для бизнеса Server** Программа, используемая для администрирования установки.</span><span class="sxs-lookup"><span data-stu-id="03667-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

