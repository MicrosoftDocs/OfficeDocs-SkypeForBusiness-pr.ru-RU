---
title: Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Задачи, которые необходимо выполнить для настройки Скайп для 2015 Business Server для выполнения нагрузочного тестирования производительности и с помощью Stress and Performance Tool.
ms.openlocfilehash: 06ca34717080421129fc03475103b34804ef280a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901699"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="cde04-103">Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="cde04-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="cde04-104">Задачи, которые необходимо выполнить для настройки Скайп для 2015 Business Server для выполнения нагрузочного тестирования производительности и с помощью Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="cde04-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="cde04-105">Чтобы запустить Скайп для Business Server 2015 Stress and Performance Tool (LyncPerfTool), Скайп для Business Server 2015 топологии необходимо настроить для сценариев, относящиеся к вам.</span><span class="sxs-lookup"><span data-stu-id="cde04-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="cde04-106">Если Скайп для Business Server 2015 не настроены или настроены неправильно, скорее всего, могут быть вашей моделирование нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cde04-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="cde04-107">С помощью Скайп для Business Server 2015 Stress and Performance Tool мы предлагаем пример Скайп скрипты консоли Business Server и основных файлов как часть [загрузить средство](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="cde04-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="cde04-108">Их можно использовать в качестве отправной точки для настройки вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="cde04-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="cde04-109">В этой статье описываются примеры Windows PowerShell, предоставляемые.</span><span class="sxs-lookup"><span data-stu-id="cde04-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cde04-110">В этом разделе не позволит описывается настройка Скайп для Business Server 2015, как правило, у нас есть другие разделы, планирование и развертывание, которые.</span><span class="sxs-lookup"><span data-stu-id="cde04-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="cde04-111">Для получения дополнительных сведений о работе с Windows PowerShell в Скайп для Business Server 2015 видеть Скайп для консоли Business Server документации по вставки введения.</span><span class="sxs-lookup"><span data-stu-id="cde04-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="cde04-112">О запуске Скайп сценариев командной консоли для управления Business Server</span><span class="sxs-lookup"><span data-stu-id="cde04-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="cde04-113">Мы предлагаем примеры скриптов PowerShell, которые можно использовать для подготовки для нагрузочного моделирования.</span><span class="sxs-lookup"><span data-stu-id="cde04-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="cde04-114">Так как эти сценарии, предназначены для моделирования нагрузки, вы найдете простой и Нестрогое их.</span><span class="sxs-lookup"><span data-stu-id="cde04-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="cde04-115">Который может оказаться подходящую для производственной среды.</span><span class="sxs-lookup"><span data-stu-id="cde04-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="cde04-116">Еще раз внимание, что эти сценарии, примеры, вам потребуется просмотреть их и во многих случаях внести изменения относится к вашей среде прежде чем приступать к практическим использовать их.</span><span class="sxs-lookup"><span data-stu-id="cde04-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="cde04-117">Как минимум хотели бы, что необходимо изменить сценарий службы группы ответа (RSG) в топологии в виду (для указания агенты, назначенные группы агентов).</span><span class="sxs-lookup"><span data-stu-id="cde04-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="cde04-118">Однако не нужно выполнить, если вам не нужно.</span><span class="sxs-lookup"><span data-stu-id="cde04-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="cde04-119">Следует соблюдать осторожность в поиске и общие сведения об этих примеров.</span><span class="sxs-lookup"><span data-stu-id="cde04-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="cde04-120">Скрипты будут перезаписаны все существующие параметры в топологии при запуске.</span><span class="sxs-lookup"><span data-stu-id="cde04-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="cde04-121">Имена версии клиента Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="cde04-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="cde04-122">Может потребоваться настроить политику проверки версии клиента, если ранее было изменено параметры из значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cde04-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="cde04-123">Если вы не уверены в том об этом, обратитесь к [документации проверка версии клиента](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="cde04-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="cde04-124">Stress and Performance Tool используется в следующих версиях агента пользователя по умолчанию при взаимодействии с Скайп для Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="cde04-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="cde04-125">LSPT/15.0.0.0 (Скайп для Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="cde04-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="cde04-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="cde04-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="cde04-127">Для клиентских мобильных устройств (UCWA) в LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="cde04-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="cde04-128">UCWA средство производительности и веб-конференции</span><span class="sxs-lookup"><span data-stu-id="cde04-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="cde04-129">Средство производительности UCWA/Mobile</span><span class="sxs-lookup"><span data-stu-id="cde04-129">UCWA Perf Tool/Mobile</span></span>
    

