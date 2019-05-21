---
title: Включение и отключение режима обхода мультимедиа
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описано, как включать и отключать обход мультимедиа с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279587"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="d56f3-103">Включение и отключение обхода сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d56f3-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="d56f3-104">В этой статье описано, как включать и отключать обход мультимедиа с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d56f3-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="d56f3-105">Включение обхода сетевых мультимедийных данных</span><span class="sxs-lookup"><span data-stu-id="d56f3-105">Enable network media bypass</span></span> 

<span data-ttu-id="d56f3-106">Параметры обхода мультимедиа применяются глобально в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d56f3-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="d56f3-107">Обойти функцию мультимедиа позволяет обходить сервер.</span><span class="sxs-lookup"><span data-stu-id="d56f3-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="d56f3-108">Дополнительные сведения о том, когда следует использовать обход мультимедиа, приведены в разделе [Планирование обхода мультимедиа](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d56f3-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="d56f3-109">Вы можете включить и настроить обход мультимедиа с помощью панели управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="d56f3-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="d56f3-110">Включение и Настройка обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d56f3-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="d56f3-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d56f3-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d56f3-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d56f3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d56f3-113">На панели навигации слева выберите пункт **Настройка сети**, а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="d56f3-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="d56f3-114">На **глобальной** странице щелкните глобальную конфигурацию \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="d56f3-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="d56f3-115">Всегда существует только одна конфигурация, и она всегда имеет имя Global.</span><span class="sxs-lookup"><span data-stu-id="d56f3-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="d56f3-116">В меню **Правка** выберите команду **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="d56f3-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="d56f3-117">На странице " **изменение глобальных параметров** " установите флажок **включить обход мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="d56f3-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="d56f3-118">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d56f3-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="d56f3-119">**Всегда не использовать**   . Выберите этот параметр, чтобы попытаться обойти все звонки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d56f3-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="d56f3-120">Этот параметр будет недоступен, если включен элемент управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="d56f3-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="d56f3-121">Если функция CAC не включена, выберите этот параметр в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="d56f3-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="d56f3-122">Контроль за пропускной способностью не требуется.</span><span class="sxs-lookup"><span data-stu-id="d56f3-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="d56f3-123">Не нужно детально настраивать конфигурацию, чтобы определить, когда должно происходить обход.</span><span class="sxs-lookup"><span data-stu-id="d56f3-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="d56f3-124">Существует полная связь между шлюзами и клиентами.</span><span class="sxs-lookup"><span data-stu-id="d56f3-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="d56f3-125">**Использование сайтов и конфигурации**   областей если включена функция CAC, этот параметр установлен по умолчанию и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="d56f3-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="d56f3-126">Если выбран этот параметр, сайты и регионы настройки сети будут использоваться для определения способа обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d56f3-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="d56f3-127">Если выбрать этот параметр, вы можете включить обход для несопоставленных сайтов.</span><span class="sxs-lookup"><span data-stu-id="d56f3-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="d56f3-128">Установите флажок **Разрешить игнорировать для несопоставленных сайтов** только в том случае, если у вас есть один или несколько крупных сайтов, связанных с одним и тем же регионом, для которых не заданы ограничения пропускной способности (например, крупный центральный сайт), а также некоторые сайты филиалов, связанные с тот же регион с ограничениями пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d56f3-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="d56f3-129">При включении обхода для несопоставленных сайтов Настройка оптимизируется, так как вы указываете только подсети, связанные с сайтами филиалов, а не необходимость указывать все подсети, связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="d56f3-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="d56f3-130">Мы рекомендуем не устанавливать флажок **включить обход для несопоставленных сайтов** , если включен параметр CAC.</span><span class="sxs-lookup"><span data-stu-id="d56f3-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="d56f3-131">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d56f3-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="d56f3-132">Отключение обхода сетевого мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d56f3-132">Disable network media bypass</span></span>

<span data-ttu-id="d56f3-133">Параметры обхода мультимедиа применяются глобально в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d56f3-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="d56f3-134">Обойти функцию мультимедиа позволяет обходить сервер.</span><span class="sxs-lookup"><span data-stu-id="d56f3-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="d56f3-135">Дополнительные сведения о том, когда следует использовать обход мультимедиа, приведены в разделе [Планирование обхода мультимедиа](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d56f3-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="d56f3-136">Вы можете отключить обход мультимедиа с помощью панели управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="d56f3-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="d56f3-137">Отключение обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d56f3-137">To disable media bypass</span></span>

1.  <span data-ttu-id="d56f3-138">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d56f3-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d56f3-139">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d56f3-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d56f3-140">На панели навигации слева выберите пункт **Настройка сети**, а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="d56f3-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="d56f3-141">На **глобальной** странице щелкните глобальную конфигурацию \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="d56f3-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="d56f3-142">Всегда существует только одна конфигурация, и она всегда имеет имя Global.</span><span class="sxs-lookup"><span data-stu-id="d56f3-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="d56f3-143">В меню **Правка** выберите команду **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="d56f3-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="d56f3-144">На странице **изменение глобальных параметров** снимите флажок **включить обход мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="d56f3-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="d56f3-145">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d56f3-145">Click **Commit** to save your changes.</span></span>

  
