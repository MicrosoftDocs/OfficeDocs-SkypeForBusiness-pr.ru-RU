---
title: Включение и отключение сервера-посредника
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Используйте процедуры, описанные в этой статье для включения или отключения сервера-посредника с помощью Скайп для панели управления Business Server.
ms.openlocfilehash: f595ab5380575f34c0a470cb58c82459841ee4d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222760"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="5c741-103">Включение и отключение мультимедиа обхода в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5c741-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="5c741-104">Используйте процедуры, описанные в этой статье для включения или отключения сервера-посредника с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="5c741-105">Включение сетевого сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="5c741-105">Enable network media bypass</span></span> 

<span data-ttu-id="5c741-106">Параметры сервера-посредника мультимедиа применяются глобально через Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="5c741-107">Обход сервера-посредника разрешает вызовы сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5c741-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="5c741-108">Для получения дополнительных сведений об использовании мультимедиа обходить, ознакомьтесь со статьей [Plan для мультимедиа обходить](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="5c741-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="5c741-109">Можно включить и настроить обход сервера-посредника из Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="5c741-110">Чтобы включить и настроить обход сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="5c741-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="5c741-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5c741-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c741-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c741-113">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="5c741-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="5c741-114">На странице **глобально** выберите **глобальную** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="5c741-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="5c741-115">Всегда существует только одна конфигурация, и он всегда носит Global.</span><span class="sxs-lookup"><span data-stu-id="5c741-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="5c741-116">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="5c741-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="5c741-117">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника** .</span><span class="sxs-lookup"><span data-stu-id="5c741-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="5c741-118">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="5c741-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="5c741-119">**Всегда пропускать**   установите этот флажок, чтобы попытаться мультимедиа обхода для всех звонков.</span><span class="sxs-lookup"><span data-stu-id="5c741-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="5c741-120">Этот параметр будет недоступен, если этот параметр включен контроль допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="5c741-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="5c741-121">Если CAC не включен, выберите этот параметр, в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="5c741-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="5c741-122">Нет необходимости для управления пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="5c741-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="5c741-123">Нет не требуется выполнять для когда должен происходить обход.</span><span class="sxs-lookup"><span data-stu-id="5c741-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="5c741-124">Есть подключение между клиентами и шлюзами.</span><span class="sxs-lookup"><span data-stu-id="5c741-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="5c741-125">**Использовать конфигурацию узлов и областей**   Если контроль допуска звонков включен, этот параметр установлен по умолчанию и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="5c741-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="5c741-126">Если выбран этот параметр, сетевой сайты и регионы конфигурации будет использоваться для определения возможности выполнения обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5c741-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="5c741-127">Если выбран этот параметр, можно включить обход сервера-посредника для сайтов, не сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="5c741-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="5c741-128">Установите флажок **Включить обход сервера-посредника для сайтов, не являющиеся сопоставляются** только в том случае, если у вас есть один или несколько крупных узлы, связанные с той же области, у которых нет ограничений пропускной способности (например, для крупных центрального сайта), а также некоторые сайты филиалов, связанных с же регионе, есть ли у ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="5c741-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="5c741-129">При включении обхода для сайтов не сопоставлены, конфигурации упрощается, так как указать только подсети, связанные с сайтами филиалов, а не требуется указать все подсети связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="5c741-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="5c741-130">Мы рекомендуем не установите флажок **Включить обход сервера-посредника для сайтов не сопоставлены** , если этот параметр включен контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="5c741-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="5c741-131">Нажмите кнопку **Сохранить** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="5c741-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="5c741-132">Отключение сервера-посредника сети</span><span class="sxs-lookup"><span data-stu-id="5c741-132">Disable network media bypass</span></span>

<span data-ttu-id="5c741-133">Параметры сервера-посредника мультимедиа применяются глобально через Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="5c741-134">Обход сервера-посредника разрешает вызовы сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5c741-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="5c741-135">Для получения дополнительных сведений об использовании мультимедиа обходить, ознакомьтесь со статьей [Plan для мультимедиа обходить](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="5c741-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="5c741-136">Обход сервера-посредника из Скайп можно отключить для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="5c741-137">Чтобы отключить сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="5c741-137">To disable media bypass</span></span>

1.  <span data-ttu-id="5c741-138">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5c741-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c741-139">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c741-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5c741-140">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="5c741-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="5c741-141">На странице **глобально** выберите **глобальную** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="5c741-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="5c741-142">Всегда существует только одна конфигурация, и он всегда носит Global.</span><span class="sxs-lookup"><span data-stu-id="5c741-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="5c741-143">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="5c741-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="5c741-144">На странице **Изменение глобальных параметров** снимите флажок **Включить обход сервера-посредника** .</span><span class="sxs-lookup"><span data-stu-id="5c741-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="5c741-145">Нажмите кнопку **Сохранить** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="5c741-145">Click **Commit** to save your changes.</span></span>

  