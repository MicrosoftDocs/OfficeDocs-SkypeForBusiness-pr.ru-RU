---
title: Установка средств администрирования в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Сводка: Узнайте, как установить средства администрирования, необходимые для установки Скайп для Business Server. Загрузить бесплатную пробную версию программы Скайп для Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a51de57ca8eaa7d303af4240b5d30e8a5ca51f70
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882132"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="84b7e-104">Установка средств администрирования в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="84b7e-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="84b7e-105">**Сводка:** Узнайте, как установить средства администрирования, необходимые для установки Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="84b7e-106">Загрузить бесплатную пробную версию программы Скайп для Business Server в центре Microsoft оценки по: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="84b7e-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="84b7e-107">К средствам администрирования относятся построитель топологий и панель управления.</span><span class="sxs-lookup"><span data-stu-id="84b7e-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="84b7e-108">Средства администрирования необходимо установить по крайней мере на одном сервере в топологии или рабочей станции управления 64-разрядная версии ОС Windows, который поддерживается для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="84b7e-109">Шаги с 1 по 5 могут выполняться в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="84b7e-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="84b7e-110">Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="84b7e-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="84b7e-111">Установка средств администрирования — шаг 3 из 8.</span><span class="sxs-lookup"><span data-stu-id="84b7e-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Обзорная схема](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="84b7e-113">Установка Скайп для средств администрирования Business Server</span><span class="sxs-lookup"><span data-stu-id="84b7e-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="84b7e-114">Установочный носитель Скайп для Business Server предоставляют гибкие возможности.</span><span class="sxs-lookup"><span data-stu-id="84b7e-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="84b7e-115">При первом запуске Setup.exe установлены средства только являются Скайп для мастер развертывания Business Server и Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="84b7e-116">С помощью этих двух средств, известных как основные компоненты можно продолжить процесс установки, но они не обеспечивают основные функциональные возможности для общего Скайп для среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="84b7e-117">Мастер развертывания автоматически запускается после установки основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="84b7e-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="84b7e-118">В разделе мастер развертывания под названием **Установить средства администрирования** устанавливает Скайп для Business Server Topology Builder и Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84b7e-119">Каждый Скайп для среды Business Server необходимо иметь хотя бы один сервер с установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="84b7e-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="84b7e-120">Смотреть видеоруководство **Установка средств администрирования**.</span><span class="sxs-lookup"><span data-stu-id="84b7e-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="84b7e-121">Установка Скайп для средств администрирования сервера с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="84b7e-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="84b7e-122">Вставка Скайп для установочного носителя Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="84b7e-123">Если установка не началась автоматически, дважды щелкните файл **Setup**.</span><span class="sxs-lookup"><span data-stu-id="84b7e-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="84b7e-p106">Для запуска установочного носителя требуется Microsoft Visual C++. Открывается диалоговое окно с запросом подтверждения установки. Нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="84b7e-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="84b7e-127">С помощью смарт-установки компонента в Скайп для Business Server может подключиться к Интернету, чтобы проверить наличие обновлений во время установки.</span><span class="sxs-lookup"><span data-stu-id="84b7e-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="84b7e-128">Это повышает эффективность работы, так как вы можете быть уверены в получении самых последних обновлений продукта.</span><span class="sxs-lookup"><span data-stu-id="84b7e-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="84b7e-129">Нажмите кнопку **Установить**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="84b7e-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="84b7e-130">Внимательно просмотрите лицензионное соглашение. Если вы согласны, выберите **Я принимаю условия лицензионного соглашения** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84b7e-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="84b7e-131">Скайп для основных компонентов Business Server будет установлен на сервере.</span><span class="sxs-lookup"><span data-stu-id="84b7e-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="84b7e-132">Состав основных компонентов показан на рисунке.</span><span class="sxs-lookup"><span data-stu-id="84b7e-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Основные компоненты на экране приложений.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="84b7e-134">**Скайп для мастер развертывания Business Server** Программа развертывания, который содержит панель запуска для установки различных компонентов Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
  - <span data-ttu-id="84b7e-135">**Скайп для консоли Business Server** Предварительно настроенного PowerShell программа, которая предоставляет возможности администрирования Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="84b7e-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
    <span data-ttu-id="84b7e-136">После завершения установки основных компонентов Скайп мастер развертывания Business Server для автоматического запуска, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="84b7e-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Мастер развертывания Skype для бизнеса Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="84b7e-138">В дополнение к основные компоненты будет также необходимо установить Скайп Business Server Topology Builder и Скайп для панели управления Business Server по крайней мере на одном сервере в среде.</span><span class="sxs-lookup"><span data-stu-id="84b7e-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="84b7e-139">Щелкните **Установить средства администрирования** в окне мастера развертывания.</span><span class="sxs-lookup"><span data-stu-id="84b7e-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="84b7e-140">Нажмите кнопку **Далее**, чтобы начать установку.</span><span class="sxs-lookup"><span data-stu-id="84b7e-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="84b7e-p109">После завершения установки нажмите кнопку **Готово**. Теперь средства администрирования добавлены на сервер, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="84b7e-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Скайп для средств администрирования Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="84b7e-144">**Скайп для Business Server Topology Builder** Программа, используемая для построения, развертывания и управления топологии.</span><span class="sxs-lookup"><span data-stu-id="84b7e-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="84b7e-145">**Скайп для панели управления Business Server** Программа, используемая для администрирования установки.</span><span class="sxs-lookup"><span data-stu-id="84b7e-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

