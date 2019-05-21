---
title: Установка предварительных требований для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Сводка: сведения о серверах и ролях серверов, которые необходимо настроить перед установкой Skype для бизнеса Server. Загрузите бесплатную пробную версию Skype для бизнеса на сервере Microsoft Evaluation Center по адресу https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 7b2369af5a95d027edff0db291af37c710813465
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306607"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="22012-104">Установка предварительных требований для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="22012-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="22012-105">**Сводка:** Сведения о серверах и ролях серверов, которые необходимо настроить перед установкой Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="22012-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="22012-106">Загрузите бесплатную пробную версию Skype для бизнеса Server в [центре оценки Майкрософт](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="22012-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="22012-107">При настройке Windows Server на каждом из серверов в топологии устанавливаются роли и функции, которые являются необходимыми компонентами.</span><span class="sxs-lookup"><span data-stu-id="22012-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="22012-108">Требования зависят от роли, которую выполняет сервер в топологии.</span><span class="sxs-lookup"><span data-stu-id="22012-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="22012-109">Шаги 1–5 можно выполнять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="22012-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="22012-110">Однако шаги 6, 7 и 8 необходимо выполнять в указанном порядке и только после шагов 1–5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="22012-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="22012-111">Обязательные компоненты устанавливаются на шаге 1 из 8.</span><span class="sxs-lookup"><span data-stu-id="22012-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Обзорная схема - установка предварительных компонентов.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="22012-113">Настройка Windows Server</span><span class="sxs-lookup"><span data-stu-id="22012-113">Setup Windows Server</span></span>

<span data-ttu-id="22012-114">Для установки Skype для бизнеса Server требуется операционная система Windows Server и ряд необходимых предварительных условий.</span><span class="sxs-lookup"><span data-stu-id="22012-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="22012-115">Сведения о планировании предварительных требований можно найти в разделе [требования к серверу в Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22012-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="22012-116">Здесь приведена процедура для Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="22012-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="22012-117">Процедуры для других версий Windows Server могут незначительно отличаться.</span><span class="sxs-lookup"><span data-stu-id="22012-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="22012-118">Прежде чем начать, убедитесь в том, что у Windows Server есть актуальная дата с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="22012-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server обновлен.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="22012-120">Посмотрите видео с инструкциями по **установке необходимых компонентов**:</span><span class="sxs-lookup"><span data-stu-id="22012-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="22012-121">Установка необходимых ролей и компонентов для серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="22012-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="22012-122">Вы можете установить необходимые роли и компоненты с помощью диспетчера серверов.</span><span class="sxs-lookup"><span data-stu-id="22012-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="22012-123">Установите необходимые компоненты программного обеспечения, указанные в разделе [требования к серверу в Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22012-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="22012-124">Необходимое программное обеспечение должно находиться на сервере, на котором работает Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="22012-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="22012-125">По умолчанию в Windows Server 2012 R2 не устанавливаются все исходные файлы для обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="22012-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="22012-126">Если сервер не подключен в сети Интернет, для установки обязательных компонентов потребуется установить носитель Windows Server 2012 R2 и выбрать **Указать альтернативный исходный путь**.</span><span class="sxs-lookup"><span data-stu-id="22012-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="22012-127">Исходные файлы находятся в каталоге sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="22012-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="22012-128">Например, если в качестве носителя Windows Server 2012 R2 указан диск D, укажите путь к нему `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="22012-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="22012-129">Важно получить последние пакеты обновления из центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="22012-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="22012-130">При отсутствии интернет-подключения потребуется вручную установить все необходимые пакеты обновления, а также обязательные компоненты для этих пакетов.</span><span class="sxs-lookup"><span data-stu-id="22012-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="22012-131">Когда в диалоговом окне появляется сообщение о завершении установки, для окончательного завершения процесса необходимо перезагрузить сервер.</span><span class="sxs-lookup"><span data-stu-id="22012-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="22012-132">Снова запустите **центр обновления Windows** и проверьте наличие обновлений для установленных ролей и служб.</span><span class="sxs-lookup"><span data-stu-id="22012-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="22012-133">Если вы будете использовать серверную панель управления Skype для бизнеса на этом сервере, необходимо также установить Silverlight.</span><span class="sxs-lookup"><span data-stu-id="22012-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="22012-134">Чтобы установить Silverlight, ознакомьтесь со сведениями о [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="22012-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="22012-135">Для серверов, роль которых отличается от роли сервера переднего плана, например для директоров, серверов сохраняемого чата и пограничных серверов, предусмотрены особые наборы обязательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="22012-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="22012-136">Подробные сведения о конкретных предварительных требованиях, необходимых для каждого типа сервера, приведены в разделе [требования к серверу в Skype для бизнеса Server](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22012-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

