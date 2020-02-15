---
title: Сценарии производительности для средства работы с нагрузочными испытаниями и производительности Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Задачи, которые необходимо выполнить для настройки Skype для бизнеса Server 2015, чтобы выполнить тестирование производительности и нагрузочного тестирования с помощью средства "нагрузка и производительность".
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983854"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2011d-103">Сценарии производительности для средства работы с нагрузочными испытаниями и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2011d-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="2011d-104">Задачи, которые необходимо выполнить для настройки Skype для бизнеса Server 2015, чтобы выполнить тестирование производительности и нагрузочного тестирования с помощью средства "нагрузка и производительность".</span><span class="sxs-lookup"><span data-stu-id="2011d-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="2011d-105">Для запуска средства нагрузки и производительности Skype для бизнеса Server 2015 (Линкперфтул) сначала необходимо настроить топологию Skype для бизнеса Server 2015 для наиболее подходящих сценариев.</span><span class="sxs-lookup"><span data-stu-id="2011d-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="2011d-106">Если Skype для бизнеса Server 2015 не настроен или настроен неправильно, то, скорее всего, произойдет ошибка при моделировании нагрузки.</span><span class="sxs-lookup"><span data-stu-id="2011d-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="2011d-107">С помощью средства "Нагрузочное обеспечение и производительность" в Skype для бизнеса Server 2015 мы предоставляем пример сценариев командной консоли Skype для бизнеса Server и базовых файлов ресурсов в процессе [загрузки средства](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="2011d-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="2011d-108">Они могут использоваться в качестве отправной точки для настройки развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2011d-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="2011d-109">В этой статье описываются примеры, приведенные в статье Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2011d-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2011d-110">В этом разделе описывается настройка Skype для бизнеса Server 2015, как правило, для этого у нас есть и другие темы по планированию и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2011d-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="2011d-111">Для получения дополнительных сведений о работе с Windows PowerShell в Skype для бизнеса Server 2015, ознакомьтесь с документацией по консоли управления Skype для бизнеса Server в статье INSERT введение.</span><span class="sxs-lookup"><span data-stu-id="2011d-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="2011d-112">Сведения о запуске сценариев командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2011d-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="2011d-113">Мы предоставляем примеры сценариев PowerShell, которые можно использовать для подготовки к нагрузочным имитации.</span><span class="sxs-lookup"><span data-stu-id="2011d-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="2011d-114">Так как эти сценарии предназначены для имитации нагрузки, вы найдете их как простые и нестрогие.</span><span class="sxs-lookup"><span data-stu-id="2011d-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="2011d-115">Это может быть не подходит для вашей рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="2011d-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="2011d-116">Еще раз проверим, что эти сценарии являются примерами, вам потребуется просмотреть их и во многих случаях внести изменения, связанные с вашей средой, прежде чем использовать их.</span><span class="sxs-lookup"><span data-stu-id="2011d-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="2011d-117">Как минимум, мы ожидаем, что вам потребуется изменить сценарий группы службы ответа (РСГ) в соответствии с вашей топологией (чтобы указать агентов, назначенных группам агентов).</span><span class="sxs-lookup"><span data-stu-id="2011d-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="2011d-118">Но не обязательно запускать их, если это не требуется.</span><span class="sxs-lookup"><span data-stu-id="2011d-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="2011d-119">Будьте внимательны и ознакомьтесь с этими примерами.</span><span class="sxs-lookup"><span data-stu-id="2011d-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="2011d-120">Сценарии заменят все существующие параметры в топологии при запуске.</span><span class="sxs-lookup"><span data-stu-id="2011d-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="2011d-121">Названия версий клиентов средства нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="2011d-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="2011d-122">Если вы ранее изменили параметры из значений по умолчанию, вам может потребоваться настроить политику проверки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2011d-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="2011d-123">Если вы не знаете это, ознакомьтесь с [документацией по проверке версии клиента](https://msdn.microsoft.com/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="2011d-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="2011d-124">При обмене данными с Skype для бизнеса Server 2015 в средстве "нагрузка и производительность" по умолчанию используются следующие версии агента пользователя:</span><span class="sxs-lookup"><span data-stu-id="2011d-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="2011d-125">ЛСПТ/15.0.0.0 (средство нагрузочного тестирования и производительности Skype для бизнеса Server 2015)</span><span class="sxs-lookup"><span data-stu-id="2011d-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="2011d-126">ОКФОНЕ/. 0.522</span><span class="sxs-lookup"><span data-stu-id="2011d-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="2011d-127">Для клиента мобильной связи (UCWA) в Линкперфтул:</span><span class="sxs-lookup"><span data-stu-id="2011d-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="2011d-128">Средство производительности UCWA/веб-конференция</span><span class="sxs-lookup"><span data-stu-id="2011d-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="2011d-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="2011d-129">UCWA Perf Tool/Mobile</span></span>
    

