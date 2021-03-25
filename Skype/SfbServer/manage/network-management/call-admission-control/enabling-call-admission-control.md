---
title: Включение управления приемом вызовов
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
description: " После настройки сети управления приемом вызовов (CAC) необходимо включить CAC для применения ограничений пропускной способности."
ms.openlocfilehash: 090b19282ce85289b0e79e09d58646c5bf5e81e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118578"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="bad6c-103">Включение контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bad6c-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="bad6c-104">Контроль допуска звонков — это сеть, состоящая из областей, узлов и подсетей, которая позволяет размещать ограничения на передачу аудио- и видеоданных на основе доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="bad6c-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="bad6c-105">После настройки сети контроля допуска звонков необходимо включить контроль допуска звонков, чтобы ограничения пропускной способности вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="bad6c-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="bad6c-106">Для этого можно использовать панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bad6c-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="bad6c-107">Включить CAC из панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="bad6c-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="bad6c-108">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="bad6c-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bad6c-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bad6c-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bad6c-110">В левой панели навигации щелкните **Конфигурация сети** и нажмите кнопку **Глобальный**.</span><span class="sxs-lookup"><span data-stu-id="bad6c-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="bad6c-111">На странице **Глобальная** выберите конфигурацию **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="bad6c-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="bad6c-112">Только одна сеть может быть настроена для любого развертывания Skype для бизнеса Server, поэтому в списке никогда не будет более одной конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="bad6c-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="bad6c-113">Переименовать глобальную конфигурацию нельзя.</span><span class="sxs-lookup"><span data-stu-id="bad6c-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="bad6c-114">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="bad6c-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="bad6c-115">На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="bad6c-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="bad6c-p103">При нажатии кнопки **Зафиксировать** запускается проверка конфигурации. Диалоговое окно **изменения глобальных параметров** закрывается, возвращая вас на страницу **Глобально**. Если в конфигурации будут обнаружены какие-либо ошибки или несоответствия, препятствующие ее корректной работе (например, если каждая область не связана с каждой другой областью промежуточным маршрутом), то вы получите предупреждение.</span><span class="sxs-lookup"><span data-stu-id="bad6c-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="bad6c-p104">При внесении изменений в конфигурацию сети можно снова выполнить проверку правильности, открыв глобальную конфигурацию и нажав кнопку **Зафиксировать**. Предварительно отключать контроль допуска звонков не требуется: оставьте этот флажок установленным и нажмите **Зафиксировать**. Это можно делать в любое время даже без внесения изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bad6c-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="bad6c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bad6c-122">See Also</span></span>

[<span data-ttu-id="bad6c-123">Планирование управления приемом вызовов</span><span class="sxs-lookup"><span data-stu-id="bad6c-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="bad6c-124">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="bad6c-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="bad6c-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad6c-125">Get-CsNetworkConfiguration</span></span>](/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="bad6c-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad6c-126">Set-CsNetworkConfiguration</span></span>](/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="bad6c-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad6c-127">Remove-CsNetworkConfiguration</span></span>](/powershell/module/skype/Remove-CsNetworkConfiguration)