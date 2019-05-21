---
title: Настройка обхода мультимедиа в Skype для бизнеса Server для того, чтобы всегда обходить сервер-посредник
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Включите обход содержимого, чтобы всегда обходить сервер-посредник в корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275880"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="63c2c-103">Настройка обхода мультимедиа в Skype для бизнеса Server для того, чтобы всегда обходить сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="63c2c-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="63c2c-104">Включите обход содержимого, чтобы всегда обходить сервер-посредник в корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="63c2c-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="63c2c-105">Если вы используете действия, описанные в этом разделе, чтобы настроить общие параметры для обхода мультимедиа, предполагается, что у вас есть хорошее соединение между конечными точками Skype для бизнеса и любым одноранговым узлом, для которого вы настроили обходные носители на магистральном подключении.</span><span class="sxs-lookup"><span data-stu-id="63c2c-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="63c2c-106">Если у вас нет хорошей связи между конечными точками Skype для бизнеса и всеми одноранговыми узлами на сервере-посреднике, для которого соответствующие магистральные подключения включены для обхода мультимедиа, необходимо настроить глобальные параметры обхода для мультимедиа, чтобы использовать сведения о сайте и регионе. При использовании обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="63c2c-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="63c2c-107">Это позволяет более подробно управлять тем, когда мультимедиа обходит сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="63c2c-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="63c2c-108">Для этого выполните действия, описанные в разделе [Настройка обхода мультимедиа в глобальных параметрах в Skype для бизнеса Server, чтобы использовать сведения о сайте и регионе](use-site-and-region-information.md) и [сопоставить подсеть с сетевым сайтом](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="63c2c-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="63c2c-109">Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="63c2c-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="63c2c-110">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="63c2c-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="63c2c-111">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="63c2c-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="63c2c-112">Дважды щелкните конфигурацию **Глобальная** в данном списке.</span><span class="sxs-lookup"><span data-stu-id="63c2c-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="63c2c-113">На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="63c2c-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="63c2c-114">Щелкните **Всегда обходить**.</span><span class="sxs-lookup"><span data-stu-id="63c2c-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="63c2c-115">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="63c2c-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="63c2c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="63c2c-116">See also</span></span>

[<span data-ttu-id="63c2c-117">Планирование обхода мультимедиа в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="63c2c-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="63c2c-118">Обходной пропускной рекламы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="63c2c-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

