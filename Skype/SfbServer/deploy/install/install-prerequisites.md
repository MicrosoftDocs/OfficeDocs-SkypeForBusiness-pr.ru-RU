---
title: Установка необходимых компонентов для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: Сводка. сведения о серверах и ролях серверов, которые необходимо настроить перед установкой Skype для бизнеса Server. Скачайте бесплатную пробную версию Skype для бизнеса Server в центре оценки Майкрософт по адресу https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018260"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="2cd65-104">Установка необходимых компонентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2cd65-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="2cd65-105">**Сводка:** Сведения о серверах и ролях серверов, которые необходимо настроить перед установкой Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2cd65-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="2cd65-106">Скачайте бесплатную пробную версию Skype для бизнеса Server в [центре оценки Майкрософт](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="2cd65-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="2cd65-107">Установка необходимых компонентов состоит из настройки Windows Server путем установки необходимых ролей и компонентов на каждом сервере в топологии.</span><span class="sxs-lookup"><span data-stu-id="2cd65-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="2cd65-108">Требования основаны на роли, которую сервер будет выполнять в топологии.</span><span class="sxs-lookup"><span data-stu-id="2cd65-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="2cd65-109">Шаги с 1 по 5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="2cd65-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="2cd65-110">Однако шаги 6, 7 и 8 необходимо выполнять по порядку, а после шагов 1 – 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="2cd65-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="2cd65-111">Установка необходимых компонентов — шаг 1 из 8.</span><span class="sxs-lookup"><span data-stu-id="2cd65-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Обзорная схема — Установка необходимых компонентов.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="2cd65-113">Настройка Windows Server</span><span class="sxs-lookup"><span data-stu-id="2cd65-113">Setup Windows Server</span></span>

<span data-ttu-id="2cd65-114">Для установки Skype для бизнеса Server требуется операционная система Windows Server и ряд необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="2cd65-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="2cd65-115">Сведения о планировании обязательных компонентов можно найти в статье [требования к серверу для Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cd65-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="2cd65-116">В этой процедуре используется Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="2cd65-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="2cd65-117">Если вы используете другую версию Windows Server, процедура может быть несколько другой.</span><span class="sxs-lookup"><span data-stu-id="2cd65-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2cd65-118">Перед началом работы убедитесь, что Windows Server обновлен с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="2cd65-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Система Windows Server обновлена.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="2cd65-120">Просмотрите видеодействия по **установке необходимых компонентов**:</span><span class="sxs-lookup"><span data-stu-id="2cd65-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="2cd65-121">Установка необходимых ролей и компонентов для серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="2cd65-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="2cd65-122">Необходимые роли и компоненты можно установить с помощью диспетчера серверов.</span><span class="sxs-lookup"><span data-stu-id="2cd65-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="2cd65-123">Установите необходимые компоненты программного обеспечения, перечисленные в разделе [требования к серверу Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cd65-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="2cd65-124">Необходимое программное обеспечение должно находиться на сервере, на котором будет выполняться Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2cd65-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2cd65-125">Windows Server 2012 R2 по умолчанию не устанавливает все исходные файлы для необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="2cd65-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="2cd65-126">Если сервер не подключен к Интернету, необходимо вставить носитель Windows Server 2012 R2 и выбрать **указать альтернативный исходный путь** для установки необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="2cd65-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="2cd65-127">Исходные файлы находятся в каталоге саурцес\сксс</span><span class="sxs-lookup"><span data-stu-id="2cd65-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="2cd65-128">Например, если в качестве носителя Windows Server 2012 R2 используется диск D, необходимо задать путь `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="2cd65-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="2cd65-129">Важно иметь последние обновления из центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="2cd65-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="2cd65-130">Если вы не подключены к Интернету, вам потребуется вручную установить все необходимые обновления, а также все необходимые компоненты для необходимых обновлений.</span><span class="sxs-lookup"><span data-stu-id="2cd65-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="2cd65-131">Когда появится диалоговое окно с сообщением о завершении установки, необходимо перезагрузить сервер для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="2cd65-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="2cd65-132">Запустите **Обновление Windows** еще раз, чтобы проверить наличие обновлений для установленных ролей и служб.</span><span class="sxs-lookup"><span data-stu-id="2cd65-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="2cd65-133">Если вы будете использовать панель управления Skype для бизнеса Server на этом сервере, необходимо также установить Silverlight.</span><span class="sxs-lookup"><span data-stu-id="2cd65-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="2cd65-134">Чтобы установить Silverlight, обратитесь к разделу [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="2cd65-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2cd65-135">Необходимые условия для серверов, выполняющих роли, отличные от сервера переднего плана, например роль директора, сохраняемого чата или пограничного сервера, имеют свои предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="2cd65-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="2cd65-136">Для получения подробных сведений о важных компонентах, необходимых для каждого типа сервера, обратитесь к разделу [Server требований для Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cd65-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

