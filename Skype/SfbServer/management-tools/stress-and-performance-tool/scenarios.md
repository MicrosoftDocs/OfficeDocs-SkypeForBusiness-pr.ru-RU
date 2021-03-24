---
title: Сценарии производительности для средства стресса и производительности Skype для бизнеса Server 2015
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
description: Задачи, которые необходимо выполнять для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и нагрузки с помощью средства Stress и Performance Tool.
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105375"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e6da7-103">Сценарии производительности для средства стресса и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6da7-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e6da7-104">Задачи, которые необходимо выполнять для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и нагрузки с помощью средства Stress и Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="e6da7-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="e6da7-105">Чтобы запустить средство стресса и производительности Skype для бизнеса Server 2015 (LyncPerfTool), топология Skype для бизнеса Server 2015 должна сначала быть настроена для сценариев, соответствующих вам.</span><span class="sxs-lookup"><span data-stu-id="e6da7-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="e6da7-106">Если Skype для бизнеса Server 2015 не настроен или настроен неправильно, моделирование нагрузки, скорее всего, не удастся.</span><span class="sxs-lookup"><span data-stu-id="e6da7-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="e6da7-107">С помощью средства стресса и производительности Skype для бизнеса Server 2015 мы предоставляем примеры сценариев Skype для управления бизнес-серверами и базовых файлов ресурсов в рамках загрузки [инструмента.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="e6da7-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="e6da7-108">Они могут использоваться в качестве отправной точки для настройки развертывания Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="e6da7-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="e6da7-109">В этой статье описываются Windows PowerShell предоставленные примеры.</span><span class="sxs-lookup"><span data-stu-id="e6da7-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6da7-110">Этот раздел не поможет вам описать, как настроить Skype для бизнеса Server 2015 в целом, для этого у нас есть другие темы планирования и развертывания.</span><span class="sxs-lookup"><span data-stu-id="e6da7-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="e6da7-111">Дополнительные сведения о работе с Windows PowerShell в Skype для бизнеса Server 2015 см. в документации skype for Business Server Management Shell в вставки введение ЗДЕСЬ.</span><span class="sxs-lookup"><span data-stu-id="e6da7-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="e6da7-112">О запуске скриптов оболочки управления Skype для бизнес-сервера</span><span class="sxs-lookup"><span data-stu-id="e6da7-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="e6da7-113">Мы предоставляем примеры скриптов PowerShell, которые можно использовать для подготовки к имитации нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e6da7-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="e6da7-114">Поскольку эти скрипты предназначены для моделирования нагрузки, их можно найти простыми и разрешительными.</span><span class="sxs-lookup"><span data-stu-id="e6da7-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="e6da7-115">Возможно, это не подходит для вашей производственной среды.</span><span class="sxs-lookup"><span data-stu-id="e6da7-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="e6da7-116">Опять же мы подчеркиваем, что эти сценарии являются примерами, вам потребуется их просмотреть и во многих случаях внести изменения, соответствующие вашей среде, прежде чем они смогут использовать их на практике.</span><span class="sxs-lookup"><span data-stu-id="e6da7-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="e6da7-117">Как минимум, мы ожидаем, что вам потребуется изменить сценарий группы службы реагирования (RSG) с учетом топологии (чтобы указать агенты, назначенные группам агентов).</span><span class="sxs-lookup"><span data-stu-id="e6da7-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="e6da7-118">Но вам не нужно запускать это, если вам не нужно.</span><span class="sxs-lookup"><span data-stu-id="e6da7-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e6da7-119">Обратите внимание при просмотре и понимании этих примеров.</span><span class="sxs-lookup"><span data-stu-id="e6da7-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="e6da7-120">Сценарии переопишут все существующие параметры топологии при запуске.</span><span class="sxs-lookup"><span data-stu-id="e6da7-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="e6da7-121">Имена клиентских версий stress и Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e6da7-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="e6da7-122">Может потребоваться настроить политику проверки клиентской версии, если вы ранее изменили параметры из значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6da7-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="e6da7-123">Если вы не уверены в этом, проверьте документацию [проверки версии клиента.](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)</span><span class="sxs-lookup"><span data-stu-id="e6da7-123">If you're unsure about this, check the [Client Version Check documentation](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).</span></span>
  
<span data-ttu-id="e6da7-124">Средство стресса и производительности использует следующие версии агента пользователя по умолчанию при общении с Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="e6da7-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="e6da7-125">LSPT/15.0.0.0 (средство стресса и производительности Skype для бизнеса Server 2015)</span><span class="sxs-lookup"><span data-stu-id="e6da7-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="e6da7-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="e6da7-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="e6da7-127">Для клиента Mobility (UCWA) в LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="e6da7-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="e6da7-128">UCWA Perf Tool/Web Conference</span><span class="sxs-lookup"><span data-stu-id="e6da7-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="e6da7-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="e6da7-129">UCWA Perf Tool/Mobile</span></span>
