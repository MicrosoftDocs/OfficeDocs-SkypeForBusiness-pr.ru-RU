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
description: 'Сводка: сведения о том, как установить средства администрирования, необходимые для установки Skype для бизнеса Server. Скачайте бесплатную пробную версию Skype для бизнеса Server из центра оценки Майкрософт по адресу: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790177"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="2d124-104">Установка средств администрирования в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2d124-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="2d124-105">**Сводка:** Сведения о том, как установить средства администрирования, необходимые для установки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="2d124-106">Скачайте бесплатную пробную версию Skype для бизнеса Server из центра оценки Майкрософт по адресу: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="2d124-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="2d124-107">К средствам администрирования относятся построитель топологий и панель управления.</span><span class="sxs-lookup"><span data-stu-id="2d124-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="2d124-108">Средства администрирования должны быть установлены по крайней мере на одном сервере в топологии или на рабочей станции управления 64-bit для Windows, которая поддерживается в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="2d124-109">Шаги с 1 по 5 могут выполняться в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="2d124-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="2d124-110">Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="2d124-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="2d124-111">Установка средств администрирования — шаг 3 из 8.</span><span class="sxs-lookup"><span data-stu-id="2d124-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="2d124-113">Установка средств администрирования Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2d124-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="2d124-114">Установочный носитель для Skype для бизнеса Server обеспечивает гибкие возможности.</span><span class="sxs-lookup"><span data-stu-id="2d124-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="2d124-115">При первом запуске файла Setup. exe единственными установленными инструментами являются Мастер развертывания Skype для бизнеса Server и консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2d124-116">С помощью этих двух инструментов, известных как основные компоненты, вы можете продолжить процесс установки, но они не предоставляют основную функциональность для общей среды Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="2d124-117">Мастер развертывания автоматически запускается после установки основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="2d124-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="2d124-118">Раздел мастера развертывания с названием " **Установка средств администрирования** " Построитель топологии Skype для бизнеса Server и панель управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="2d124-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2d124-119">Каждая серверная среда Skype для бизнеса должна иметь хотя бы один сервер с установленными инструментами администрирования.</span><span class="sxs-lookup"><span data-stu-id="2d124-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="2d124-120">Смотреть видеоруководство **Установка средств администрирования**.</span><span class="sxs-lookup"><span data-stu-id="2d124-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="2d124-121">Установка средств администрирования Skype для бизнеса Server с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="2d124-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="2d124-122">Вставьте установочный носитель Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="2d124-123">Если установка не началась автоматически, дважды щелкните файл **Setup**.</span><span class="sxs-lookup"><span data-stu-id="2d124-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="2d124-p106">Для запуска установочного носителя требуется Microsoft Visual C++. Открывается диалоговое окно с запросом подтверждения установки. Нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="2d124-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="2d124-127">С помощью интеллектуальной настройки, новой функции в Skype для бизнеса Server можно подключаться к Интернету для проверки наличия обновлений в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="2d124-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="2d124-128">Это повышает эффективность работы, так как вы можете быть уверены в получении самых последних обновлений продукта.</span><span class="sxs-lookup"><span data-stu-id="2d124-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="2d124-129">Нажмите кнопку **Установить**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="2d124-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="2d124-130">Внимательно просмотрите лицензионное соглашение. Если вы согласны, выберите **Я принимаю условия лицензионного соглашения** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d124-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="2d124-131">Основные компоненты сервера Skype для бизнеса будут установлены на сервере.</span><span class="sxs-lookup"><span data-stu-id="2d124-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="2d124-132">Состав основных компонентов показан на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2d124-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="2d124-134">**Мастер развертывания Skype для бизнеса Server** Программа развертывания, которая предоставляет стартовый планшет для установки различных компонентов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="2d124-135">**Командная консоль управления Skype для бизнеса Server** Предварительно настроенная программа PowerShell, разрешающая администрирование Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2d124-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="2d124-136">После завершения установки основных компонентов мастер развертывания в Skype для бизнеса Server будет автоматически запущен, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2d124-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Мастер развертывания Skype для бизнеса Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="2d124-138">В дополнение к основным компонентам вам также потребуется установить построитель топологии Skype для бизнеса Server и панель управления "Skype для бизнеса" на сервере по крайней мере одного сервера в среде.</span><span class="sxs-lookup"><span data-stu-id="2d124-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="2d124-139">Щелкните **Установить средства администрирования** в окне мастера развертывания.</span><span class="sxs-lookup"><span data-stu-id="2d124-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="2d124-140">Нажмите кнопку **Далее**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="2d124-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="2d124-p109">После завершения установки нажмите кнопку **Готово**. Теперь средства администрирования добавлены на сервер, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2d124-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Средства администрирования Skype для бизнеса Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="2d124-144">**Построитель топологии Skype для бизнеса Server** Программа, используемая для создания и развертывания топологий и управления ими.</span><span class="sxs-lookup"><span data-stu-id="2d124-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="2d124-145">**Панель управления "Skype для бизнеса" на сервере** Программа, используемая для управления установкой.</span><span class="sxs-lookup"><span data-stu-id="2d124-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

