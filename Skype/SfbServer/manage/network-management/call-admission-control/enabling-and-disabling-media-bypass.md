---
title: Включение и отключение обхода мультимедиа
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Используйте процедуры, которые данная статья позволяет включить или отключить обход сервера-посредника с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816499"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="a565a-103">Включение и отключение обхода сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a565a-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="a565a-104">Используйте процедуры, которые данная статья позволяет включить или отключить обход сервера-посредника с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="a565a-105">Включить сетевой обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a565a-105">Enable network media bypass</span></span> 

<span data-ttu-id="a565a-106">Параметры обхода сервера-посредника применяются глобально в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a565a-107">Обход сервера-посредника позволяет звонкам обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a565a-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a565a-108">Сведения о том, когда использовать обход мультимедиа, см. в подсети ["Планирование обхода мультимедиа".](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="a565a-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="a565a-109">Вы можете включить и настроить обход сервера-посредника с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="a565a-110">Включение и настройка обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a565a-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="a565a-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a565a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a565a-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a565a-113">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Глобальная".**</span><span class="sxs-lookup"><span data-stu-id="a565a-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a565a-p102">На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="a565a-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a565a-116">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a565a-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a565a-117">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="a565a-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a565a-118">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="a565a-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="a565a-119">**Всегда обходить**   Выберите этот параметр, чтобы попытаться обойти посредника во всех вызовах.</span><span class="sxs-lookup"><span data-stu-id="a565a-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="a565a-120">Этот параметр будет недоступен, если включен контроль допуска вызовов (CAC).</span><span class="sxs-lookup"><span data-stu-id="a565a-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="a565a-121">Если CAC не включен, выберите этот параметр в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="a565a-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="a565a-122">не требуется контроль за пропускной способностью канала;</span><span class="sxs-lookup"><span data-stu-id="a565a-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="a565a-123">не требуется выполнять сложный контроль, когда должен происходить обход;</span><span class="sxs-lookup"><span data-stu-id="a565a-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="a565a-124">между клиентами и шлюзами есть подключение.</span><span class="sxs-lookup"><span data-stu-id="a565a-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="a565a-125">**Использование конфигурации сайтов и регионов**   Если cac включен, этот параметр выбран по умолчанию и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="a565a-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="a565a-126">При выборе этого параметра для определения возможности обхода мультимедиа будут использоваться узлы и регионы конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="a565a-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="a565a-127">При выборе этого параметра можно включить обход для ненавязаных сайтов.</span><span class="sxs-lookup"><span data-stu-id="a565a-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="a565a-128">Если  с одной областью связан один или несколько крупных сайтов, которые не имеют ограничений пропускной способности (например, большой центральный сайт), а также с некоторыми сайтами филиалов, связанными с той же областью, с которыми связаны ограничения пропускной способности, щелкните "Включить обход".</span><span class="sxs-lookup"><span data-stu-id="a565a-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="a565a-129">Когда вы включаете обход для ненастраиваемых сайтов, конфигурация упрощается, так как указываются только подсети, связанные с сайтами филиалов, а не требуется указывать все подсети, связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="a565a-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="a565a-130">Если контроль cac включен,  не рекомендуется выбирать обход включения для ненавязчивых сайтов.</span><span class="sxs-lookup"><span data-stu-id="a565a-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="a565a-131">Чтобы сохранить изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a565a-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="a565a-132">Отключение обхода сетевого носители</span><span class="sxs-lookup"><span data-stu-id="a565a-132">Disable network media bypass</span></span>

<span data-ttu-id="a565a-133">Параметры обхода сервера-посредника применяются глобально в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a565a-134">Обход сервера-посредника позволяет звонкам обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a565a-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a565a-135">Сведения о том, когда использовать обход мультимедиа, см. в подсети ["Планирование обхода мультимедиа".](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="a565a-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="a565a-136">Вы можете отключить обход сервера-посредника на панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="a565a-137">Отключение обхода медиаданных</span><span class="sxs-lookup"><span data-stu-id="a565a-137">To disable media bypass</span></span>

1.  <span data-ttu-id="a565a-138">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a565a-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a565a-139">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a565a-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a565a-140">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Глобальная".**</span><span class="sxs-lookup"><span data-stu-id="a565a-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a565a-p106">На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="a565a-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a565a-143">В меню **Изменить** щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="a565a-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a565a-144">На странице **Изменить глобальную настройку** снимите флажок **Разрешить обход мультимедиа**.</span><span class="sxs-lookup"><span data-stu-id="a565a-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a565a-145">Щелкните **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="a565a-145">Click **Commit** to save your changes.</span></span>

  
