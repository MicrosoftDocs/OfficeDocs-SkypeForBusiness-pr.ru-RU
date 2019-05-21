---
title: Сценарии производительности для средства "стресс и производительность" в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Задачи, которые необходимо выполнить, чтобы настроить Skype для бизнеса Server 2015 для работы с производительностью и тестированием нагрузки с помощью средства "стресс и производительность".
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299385"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e3821-103">Сценарии производительности для средства "стресс и производительность" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e3821-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e3821-104">Задачи, которые необходимо выполнить, чтобы настроить Skype для бизнеса Server 2015 для работы с производительностью и тестированием нагрузки с помощью средства "стресс и производительность".</span><span class="sxs-lookup"><span data-stu-id="e3821-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="e3821-105">Для работы с утилитой нагрузки и производительности Skype для бизнеса Server 2015 (Линкперфтул) необходимо сначала настроить топологию Skype для бизнеса Server 2015 для необходимых вам сценариев.</span><span class="sxs-lookup"><span data-stu-id="e3821-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="e3821-106">Если приложение Skype для бизнеса Server 2015 не настроено или настроено неправильно, возможно, произойдет сбой моделирования нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e3821-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="e3821-107">С помощью средства "стресс и производительность" в Skype для бизнеса Server 2015 мы предоставляем примеры сценариев командной консоли Skype для бизнеса Server и базовых файлов ресурсов в рамках [загрузки средства](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="e3821-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="e3821-108">Эти данные можно использовать в качестве отправной точки для настройки развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e3821-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="e3821-109">В этой статье описаны примеры Windows PowerShell, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="e3821-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3821-110">В этой статье объясняется, как настроить Skype для бизнеса Server 2015, как правило, для этого у нас есть другие статьи, связанные с планированием и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="e3821-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="e3821-111">Подробные сведения о работе с Windows PowerShell в Skype для бизнеса Server 2015 можно найти в документации по консоли управления в Skype для бизнеса Server на странице Введение.</span><span class="sxs-lookup"><span data-stu-id="e3821-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="e3821-112">Сведения о работе со сценариями командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3821-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="e3821-113">Мы предоставляем образцы сценариев PowerShell, которые можно использовать для подготовки к нагрузочным эмуляциям.</span><span class="sxs-lookup"><span data-stu-id="e3821-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="e3821-114">Поскольку эти сценарии предназначены для моделирования нагрузки, вы увидите, что они являются простыми и нестрогими.</span><span class="sxs-lookup"><span data-stu-id="e3821-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="e3821-115">Это может быть неприемлемым для вашей производственной среды.</span><span class="sxs-lookup"><span data-stu-id="e3821-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="e3821-116">Еще раз мы загрузим, что эти сценарии являются примерами, вам потребуется изучить их и во многих случаях вносить изменения, связанные с вашей средой, прежде чем можно будет использовать их для практических целей.</span><span class="sxs-lookup"><span data-stu-id="e3821-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="e3821-117">Как минимум, мы ожидаем, что вам нужно было бы изменить сценарий группы обслуживания ответа (РСГ) с вашей топологией (чтобы указать агенты, назначенные группам агента).</span><span class="sxs-lookup"><span data-stu-id="e3821-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="e3821-118">Но если это не требуется, вам не нужно выполнять эти программы.</span><span class="sxs-lookup"><span data-stu-id="e3821-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e3821-119">Будьте внимательны и просматривая эти примеры.</span><span class="sxs-lookup"><span data-stu-id="e3821-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="e3821-120">Сценарии будут переопределять любые существующие параметры в топологии при запуске.</span><span class="sxs-lookup"><span data-stu-id="e3821-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="e3821-121">Названия версий клиента средства нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="e3821-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="e3821-122">Если вы ранее изменили настройки из значений по умолчанию, вам может потребоваться настроить политику проверки версии клиента.</span><span class="sxs-lookup"><span data-stu-id="e3821-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="e3821-123">Если вы не уверены в этом, ознакомьтесь с документацией для [проверки версии клиента](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="e3821-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="e3821-124">В средстве "стресс и производительность" по умолчанию используются следующие версии агента пользователя при общении с Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="e3821-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="e3821-125">ЛСПТ/15.0.0.0 (средство для обеспечения нагрузки и производительности в Skype для бизнеса Server 2015)</span><span class="sxs-lookup"><span data-stu-id="e3821-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="e3821-126">ОКФОНЕ/. 0.522</span><span class="sxs-lookup"><span data-stu-id="e3821-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="e3821-127">Для клиента мобильной связи (УКВА) в Линкперфтул:</span><span class="sxs-lookup"><span data-stu-id="e3821-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="e3821-128">Средство для УКВА производительности и веб-конференции</span><span class="sxs-lookup"><span data-stu-id="e3821-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="e3821-129">Средство для УКВА производительности и мобильные телефоны</span><span class="sxs-lookup"><span data-stu-id="e3821-129">UCWA Perf Tool/Mobile</span></span>
    

