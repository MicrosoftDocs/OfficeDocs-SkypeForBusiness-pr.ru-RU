---
title: Включение контроля допуска вызовов
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
description: " После настройки сети контроля допуска вызовов (CAC) необходимо включить контроль допуска вызовов для применения ограничений пропускной способности."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816509"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="a55b0-103">Включение контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a55b0-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="a55b0-104">Контроль допуска звонков — это сеть, состоящая из областей, узлов и подсетей, которая позволяет размещать ограничения на передачу аудио- и видеоданных на основе доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a55b0-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="a55b0-105">После настройки сети контроля допуска звонков необходимо включить контроль допуска звонков, чтобы ограничения пропускной способности вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="a55b0-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="a55b0-106">Для этого можно использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a55b0-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="a55b0-107">Чтобы включить контроль звонков из панели управления Skype для бизнеса Server, с помощью</span><span class="sxs-lookup"><span data-stu-id="a55b0-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a55b0-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a55b0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a55b0-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a55b0-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a55b0-110">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Глобальная".**</span><span class="sxs-lookup"><span data-stu-id="a55b0-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a55b0-111">На странице **Глобальная** выберите конфигурацию **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="a55b0-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="a55b0-112">Для любого развертывания Skype для бизнеса Server можно настроить только одну сеть, поэтому в списке никогда не будет более одной конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="a55b0-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="a55b0-113">Переименовать глобальную конфигурацию нельзя.</span><span class="sxs-lookup"><span data-stu-id="a55b0-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="a55b0-114">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a55b0-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a55b0-115">На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a55b0-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="a55b0-p103">При нажатии кнопки **Зафиксировать** запускается проверка конфигурации. Диалоговое окно **изменения глобальных параметров** закрывается, возвращая вас на страницу **Глобально**. Если в конфигурации будут обнаружены какие-либо ошибки или несоответствия, препятствующие ее корректной работе (например, если каждая область не связана с каждой другой областью промежуточным маршрутом), то вы получите предупреждение.</span><span class="sxs-lookup"><span data-stu-id="a55b0-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="a55b0-p104">При внесении изменений в конфигурацию сети можно снова выполнить проверку правильности, открыв глобальную конфигурацию и нажав кнопку **Зафиксировать**. Предварительно отключать контроль допуска звонков не требуется: оставьте этот флажок установленным и нажмите **Зафиксировать**. Это можно делать в любое время даже без внесения изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a55b0-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a55b0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a55b0-122">See Also</span></span>

[<span data-ttu-id="a55b0-123">Планирование контроля допуска вызовов</span><span class="sxs-lookup"><span data-stu-id="a55b0-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="a55b0-124">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="a55b0-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="a55b0-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a55b0-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="a55b0-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a55b0-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="a55b0-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a55b0-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
