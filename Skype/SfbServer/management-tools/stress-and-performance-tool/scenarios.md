---
title: Сценарии производительности для средства "Нагрузка и производительность Skype для бизнеса Server 2015"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Задачи, необходимые для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и загрузки с помощью средства Stress and Performance Tool.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814709"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8a6e3-103">Сценарии производительности для средства "Нагрузка и производительность Skype для бизнеса Server 2015"</span><span class="sxs-lookup"><span data-stu-id="8a6e3-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="8a6e3-104">Задачи, необходимые для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и загрузки с помощью средства Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="8a6e3-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="8a6e3-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="8a6e3-107">В средстве Skype для бизнеса Server 2015 Stress and Performance Tool мы предоставляем примеры сценариев оболочки управления Skype для бизнеса Server и базовых файлов ресурсов в рамках скачивания [средства.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="8a6e3-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="8a6e3-108">Их можно использовать в качестве отправной точки для настройки развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="8a6e3-109">В этой статье описываются Windows PowerShell примеры.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a6e3-110">В этом разделе не описывается, как настроить Skype для бизнеса Server 2015 в целом. Для этого у нас есть другие разделы по планированию и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="8a6e3-111">Дополнительные сведения о работе с Windows PowerShell в Skype для бизнеса Server 2015 см. в документации по skype для бизнеса Server Management Shell на веб-вкладке "Вставка".</span><span class="sxs-lookup"><span data-stu-id="8a6e3-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="8a6e3-112">О запуске сценариев оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8a6e3-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="8a6e3-113">Мы предоставляем примеры сценариев PowerShell, которые можно использовать для подготовки к имитации загрузки.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="8a6e3-114">Так как эти сценарии предназначены для моделирования нагрузки, они будут простыми и неумещенными.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="8a6e3-115">Возможно, это не подходит для вашей производственной среды.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="8a6e3-116">Опять же, мы подчеркиваем, что эти сценарии являются примерами, вам потребуется просмотреть их и во многих случаях внести изменения, релевантные для вашей среды, прежде чем использовать их на практике.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="8a6e3-117">Как минимум, предполагается, что вам потребуется изменить скрипт группы ответа (RSG) с учетом топологии (чтобы указать агентов, которые назначены группам агентов).</span><span class="sxs-lookup"><span data-stu-id="8a6e3-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="8a6e3-118">Но это не требуется, если это не требуется.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8a6e3-119">Внимательно просмотрите эти примеры и понимайте их.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="8a6e3-120">При запуске сценарии переопишут все существующие параметры в топологии.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="8a6e3-121">Названия версий клиентов средства stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="8a6e3-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="8a6e3-122">Вам может потребоваться настроить политику проверки версий клиентов, если вы ранее изменили параметры со значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a6e3-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="8a6e3-123">Если вы не уверены в этом, проверьте документацию по проверке [версий клиентов.](https://msdn.microsoft.com/vsto/jj923060)</span><span class="sxs-lookup"><span data-stu-id="8a6e3-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="8a6e3-124">Средство stress and Performance использует следующие версии агента пользователя по умолчанию при связи со Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="8a6e3-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="8a6e3-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="8a6e3-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="8a6e3-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="8a6e3-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="8a6e3-127">Для клиента Mobility (UCWA) в LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="8a6e3-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="8a6e3-128">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="8a6e3-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="8a6e3-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="8a6e3-129">UCWA Perf Tool/Mobile</span></span>
    

