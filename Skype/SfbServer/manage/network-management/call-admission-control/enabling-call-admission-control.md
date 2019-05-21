---
title: Включение управления допуском звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " После настройки сети управления допуском звонков (CAC) необходимо включить CAC для обеспечения ограничения пропускной способности."
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279552"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="5ee0a-103">Включение контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ee0a-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="5ee0a-104">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="5ee0a-105">После настройки сети CAC необходимо включить функцию CAC для обеспечения ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="5ee0a-106">Это можно сделать с помощью панели управления сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="5ee0a-107">Активация CAC с помощью панели управления "Skype для бизнеса" на сервере</span><span class="sxs-lookup"><span data-stu-id="5ee0a-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5ee0a-108">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ee0a-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ee0a-110">На панели навигации слева выберите пункт **Настройка сети**, а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="5ee0a-111">На **глобальной** странице щелкните глобальную конфигурацию \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="5ee0a-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="5ee0a-112">Для развертывания Skype для бизнеса Server можно настроить только одну сеть, поэтому в списке никогда не будет более одной конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="5ee0a-113">Вы не можете переименовать глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="5ee0a-114">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5ee0a-115">На странице **изменение глобальных параметров** установите флажок **включить управление допуском звонков** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="5ee0a-116">При нажатии \*\*\*\* кнопки зафиксировать вы запускаете тест конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="5ee0a-117">Диалоговое окно " **изменение глобальных параметров** " закроется и \*\*\*\* будет возвращено на глобальную страницу.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="5ee0a-118">Вы получите предупреждение о том, что в конфигурации сети обнаружены ошибки или несоответствия (например, если каждый регион не подключен к каждому из них через маршрут между регионами).</span><span class="sxs-lookup"><span data-stu-id="5ee0a-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="5ee0a-119">Если вы вносите изменения в конфигурацию сети, вы можете снова выполнить проверку, открыв глобальную конфигурацию и выбрав команду **Commit (сохранить**).</span><span class="sxs-lookup"><span data-stu-id="5ee0a-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="5ee0a-120">Отключить CAC сначала не требуется: Оставьте флажок установленным, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="5ee0a-121">Это можно сделать в любое время, не внося каких – либо изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="5ee0a-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ee0a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee0a-122">See Also</span></span>

[<span data-ttu-id="5ee0a-123">Планирование контроля доступа звонков</span><span class="sxs-lookup"><span data-stu-id="5ee0a-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="5ee0a-124">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="5ee0a-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="5ee0a-125">Get-Кснетворкконфигуратион</span><span class="sxs-lookup"><span data-stu-id="5ee0a-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="5ee0a-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ee0a-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="5ee0a-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ee0a-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
