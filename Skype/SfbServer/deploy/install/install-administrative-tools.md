---
title: Установка средств администрирования в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Сводка: Узнайте, как установить средства администрирования, необходимые для установки Скайп для Business Server 2015. Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 104919e66ea16777582d28617c78853ba6f2f1e3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="2520b-104">Установка средств администрирования в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2520b-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2520b-105">**Сводка:** Узнайте, как установить средства администрирования, необходимые для установки Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2520b-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="2520b-106">Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="2520b-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="2520b-107">К средствам администрирования относятся построитель топологий и панель управления.</span><span class="sxs-lookup"><span data-stu-id="2520b-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="2520b-108">Средства администрирования необходимо установить по крайней мере на одном сервере в топологии или рабочей станции управления 64-разрядная версии ОС Windows, который поддерживается для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="2520b-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="2520b-109">Шаги с 1 по 5 могут выполняться в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="2520b-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="2520b-110">Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="2520b-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="2520b-111">Установка средств администрирования — шаг 3 из 8.</span><span class="sxs-lookup"><span data-stu-id="2520b-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="2520b-113">Установка Скайп для средств администрирования Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2520b-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="2520b-114">Установочного носителя для Скайп для Business Server 2015 предоставляют гибкие возможности.</span><span class="sxs-lookup"><span data-stu-id="2520b-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="2520b-115">При первом запуске Setup.exe установлены средства только являются Скайп для мастер развертывания Business Server и Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="2520b-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2520b-116">С помощью этих двух средств, известных как основные компоненты можно продолжить процесс установки, но они не обеспечивают основные функциональные возможности для общего Скайп для среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="2520b-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="2520b-117">Мастер развертывания автоматически запускается после установки основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="2520b-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="2520b-118">В разделе мастер развертывания под названием **Установить средства администрирования** устанавливает Скайп для Business Server Topology Builder и Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="2520b-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2520b-119">Каждый Скайп для среды Business Server необходимо иметь хотя бы один сервер с установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="2520b-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="2520b-120">Смотреть видеоруководство **Установка средств администрирования**.</span><span class="sxs-lookup"><span data-stu-id="2520b-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="2520b-121">Установка Скайп для средств администрирования Business Server 2015 с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="2520b-121">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="2520b-122">Вставка Скайп для Business Server 2015 установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="2520b-122">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="2520b-123">Если установка не началась автоматически, дважды щелкните файл **Setup**.</span><span class="sxs-lookup"><span data-stu-id="2520b-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="2520b-p106">Для запуска установочного носителя требуется Microsoft Visual C++. Открывается диалоговое окно с запросом подтверждения установки. Нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="2520b-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="2520b-127">С помощью смарт-установки компонента в Скайп для Business Server 2015, может подключиться к Интернету, чтобы проверить наличие обновлений во время установки.</span><span class="sxs-lookup"><span data-stu-id="2520b-127">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="2520b-128">Это повышает эффективность работы, так как вы можете быть уверены в получении самых последних обновлений продукта.</span><span class="sxs-lookup"><span data-stu-id="2520b-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="2520b-129">Нажмите кнопку **Установить**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="2520b-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="2520b-130">Внимательно просмотрите лицензионное соглашение. Если вы согласны, выберите **Я принимаю условия лицензионного соглашения** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2520b-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="2520b-131">Скайп для Business Server 2015 основные компоненты будут установлены на сервере.</span><span class="sxs-lookup"><span data-stu-id="2520b-131">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="2520b-132">Состав основных компонентов показан на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2520b-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="2520b-134">**Скайп для 2015 мастер развертывания Business Server** Программа развертывания, который содержит панель запуска для установки различных компонентов Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2520b-134">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="2520b-135">**Скайп оболочки управления 2015 Business Server** Предварительно настроенного PowerShell программа, которая предоставляет возможности администрирования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2520b-135">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="2520b-136">После завершения установки основных компонентов Скайп мастер развертывания 2015 Business Server для автоматического запуска, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2520b-136">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Мастер развертывания Skype для бизнеса Server 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="2520b-138">Кроме основных компонентов будет необходимо также установить Скайп для Business Server 2015 Topology Builder и Скайп для панели управления 2015 Business Server по крайней мере на одном сервере в среде.</span><span class="sxs-lookup"><span data-stu-id="2520b-138">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="2520b-139">Щелкните **Установить средства администрирования** в окне мастера развертывания.</span><span class="sxs-lookup"><span data-stu-id="2520b-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="2520b-140">Нажмите кнопку **Далее**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="2520b-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="2520b-p109">После завершения установки нажмите кнопку **Готово**. Теперь средства администрирования добавлены на сервер, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="2520b-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Средства администрирования Skype для бизнеса Server 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="2520b-144">**Скайп для бизнеса 2015 построитель топологий** Программа, используемая для построения, развертывания и управления топологии.</span><span class="sxs-lookup"><span data-stu-id="2520b-144">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="2520b-145">**Скайп для панели управления 2015 Business Server** Программа, используемая для администрирования установки.</span><span class="sxs-lookup"><span data-stu-id="2520b-145">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

