---
title: Включение контроля допуска звонков
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " После настройки сетевой контроля допуска допуска звонков необходимо включить контроль допуска звонков для принудительного применения ограничения пропускной способности."
ms.openlocfilehash: 9c264305a38bf4bf9ef3716c5df82d74155e8936
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222837"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="b21c4-103">Включение контроля допуска звонков в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b21c4-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="b21c4-104">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b21c4-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="b21c4-105">После настройки сетевой контроля допуска звонков необходимо включить контроль допуска звонков для принудительного применения ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b21c4-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="b21c4-106">Для этого можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="b21c4-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="b21c4-107">Чтобы включить контроль допуска звонков из Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="b21c4-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b21c4-108">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b21c4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b21c4-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="b21c4-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b21c4-110">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="b21c4-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="b21c4-111">На странице **глобально** выберите **глобальную** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b21c4-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="b21c4-112">Только один сетевой можно настроить для любого Скайп для развертывания Business Server, поэтому никогда не будет более одного конфигурация сети в списке.</span><span class="sxs-lookup"><span data-stu-id="b21c4-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="b21c4-113">Невозможно переименование глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b21c4-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="b21c4-114">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b21c4-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b21c4-115">На странице **Изменение глобального параметра** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b21c4-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="b21c4-116">Если нажать кнопку **зафиксировать**, выполнить проверку конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b21c4-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="b21c4-117">Диалоговое окно **Изменение глобальных параметров** закроется, на страницу **Global** .</span><span class="sxs-lookup"><span data-stu-id="b21c4-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="b21c4-118">Если в конфигурации сети, которая не позволит правильно работать (например, если каждого региона не подключен к каждой области через регионами; маршруты) обнаруживаются ошибки и несоответствия будет показано предупреждение.</span><span class="sxs-lookup"><span data-stu-id="b21c4-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="b21c4-119">При внесении изменений в конфигурацию сети можно запустить проверку еще раз, открыв глобальную конфигурацию и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b21c4-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="b21c4-120">Необходимо сначала отключить контроль допуска звонков: этот флажок установлен и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b21c4-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="b21c4-121">Это можно сделать в любое время без внесения изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b21c4-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="b21c4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b21c4-122">See Also</span></span>

[<span data-ttu-id="b21c4-123">Планирование контроля доступа звонков</span><span class="sxs-lookup"><span data-stu-id="b21c4-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="b21c4-124">Развертывание контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="b21c4-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="b21c4-125">Командлет Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b21c4-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="b21c4-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b21c4-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="b21c4-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b21c4-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
