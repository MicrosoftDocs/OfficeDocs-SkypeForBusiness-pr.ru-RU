---
title: Включение контроля допуска звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " После настройки сетевой контроля допуска допуска звонков необходимо включить контроль допуска звонков для принудительного применения ограничения пропускной способности."
ms.openlocfilehash: a819f3a42078c094c0fc8bf10f788bbaf3361e20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888333"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="0cb88-103">Включение контроля допуска звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0cb88-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="0cb88-104">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="0cb88-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="0cb88-105">После настройки сетевой контроля допуска звонков необходимо включить контроль допуска звонков для принудительного применения ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="0cb88-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="0cb88-106">Для этого можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cb88-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="0cb88-107">Чтобы включить контроль допуска звонков из Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="0cb88-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0cb88-108">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0cb88-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0cb88-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cb88-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0cb88-110">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="0cb88-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0cb88-111">На странице **глобально** выберите **глобальную** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0cb88-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="0cb88-112">Только один сетевой можно настроить для любого Скайп для развертывания Business Server, поэтому никогда не будет более одного конфигурация сети в списке.</span><span class="sxs-lookup"><span data-stu-id="0cb88-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="0cb88-113">Невозможно переименование глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0cb88-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="0cb88-114">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0cb88-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0cb88-115">На странице **Изменение глобального параметра** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cb88-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="0cb88-116">Если нажать кнопку **зафиксировать**, выполнить проверку конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cb88-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="0cb88-117">Диалоговое окно **Изменение глобальных параметров** закроется, на страницу **Global** .</span><span class="sxs-lookup"><span data-stu-id="0cb88-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="0cb88-118">Если в конфигурации сети, которая не позволит правильно работать (например, если каждого региона не подключен к каждой области через регионами; маршруты) обнаруживаются ошибки и несоответствия будет показано предупреждение.</span><span class="sxs-lookup"><span data-stu-id="0cb88-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="0cb88-119">При внесении изменений в конфигурацию сети можно запустить проверку еще раз, открыв глобальную конфигурацию и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cb88-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="0cb88-120">Необходимо сначала отключить контроль допуска звонков: этот флажок установлен и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cb88-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="0cb88-121">Это можно сделать в любое время без внесения изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0cb88-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cb88-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0cb88-122">See Also</span></span>

[<span data-ttu-id="0cb88-123">Планирование контроля доступа звонков</span><span class="sxs-lookup"><span data-stu-id="0cb88-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="0cb88-124">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0cb88-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="0cb88-125">Командлет Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cb88-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="0cb88-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cb88-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="0cb88-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cb88-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
