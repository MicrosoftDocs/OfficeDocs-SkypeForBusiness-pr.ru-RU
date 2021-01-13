---
title: Настройка обхода сервера-посредника в Skype для бизнеса Server для всегдаго обхода сервера-посредника
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Включить обход сервера-посредника для обхода сервера-посредника в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804219"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5bc82-103">Настройка обхода сервера-посредника в Skype для бизнеса Server для всегдаго обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="5bc82-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="5bc82-104">Включить обход сервера-посредника для обхода сервера-посредника в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="5bc82-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="5bc82-105">Если вы используете действия, которые вы используете в этом разделе для настройки глобальных параметров для обхода мультимедиа, предположим, что у вас есть хорошая связь между конечными точками Skype для бизнеса и любым одноранговой точкой, для которой вы настроили обход мультимедиа в магистрали.</span><span class="sxs-lookup"><span data-stu-id="5bc82-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="5bc82-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span><span class="sxs-lookup"><span data-stu-id="5bc82-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="5bc82-107">Это обеспечивает более точный контроль над процессом обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5bc82-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="5bc82-108">Для этого используйте действия, которые необходимо предпринять в настройке глобальных параметров обхода сервера-посредника в Skype для бизнеса [Server,](use-site-and-region-information.md) чтобы использовать сведения о сайте и регионе, а затем связать подсеть с сетевым [сайтом.](deploy-network.md#BKMK_AssociateSubnets)</span><span class="sxs-lookup"><span data-stu-id="5bc82-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="5bc82-109">Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5bc82-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="5bc82-110">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5bc82-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5bc82-111">В левой панели навигации щелкните **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="5bc82-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="5bc82-112">Дважды щелкните конфигурацию **Глобальная** в списке.</span><span class="sxs-lookup"><span data-stu-id="5bc82-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="5bc82-113">На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="5bc82-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="5bc82-114">Щелкните **Всегда обходить**.</span><span class="sxs-lookup"><span data-stu-id="5bc82-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="5bc82-115">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5bc82-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5bc82-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5bc82-116">See also</span></span>

[<span data-ttu-id="5bc82-117">Планирование обхода мультимедиа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5bc82-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="5bc82-118">Развертывание обхода сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5bc82-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

