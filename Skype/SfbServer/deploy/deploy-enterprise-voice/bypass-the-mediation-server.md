---
title: Настройка сервера-посредника в Скайп для Business Server, чтобы всегда сервера-посредника
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Включите обход сервера-посредника для всегда сервера-посредника в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 518191dcf690650ebd614259e289f6cbf75ca8ce
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982610"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="4598f-103">Настройка сервера-посредника в Скайп для Business Server, чтобы всегда сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="4598f-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="4598f-104">Включите обход сервера-посредника для всегда сервера-посредника в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4598f-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="4598f-105">Если вы используете пропускать действия, описанные в этом разделе, чтобы настроить глобальные параметры для мультимедиа, предполагается наличие хорошее подключение между Скайп для конечных точек бизнеса и любой узел, для которого вы настроили обход сервера-посредника на магистральном соединении.</span><span class="sxs-lookup"><span data-stu-id="4598f-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="4598f-106">Если у вас хорошее подключение между Скайп для конечных точек бизнеса и всем участникам сервера-посредника, соответствующих магистрали подключения был разрешен доступ к сервера-посредника, необходимо настроить глобальные параметры сервера-посредника для использования сведений об узлах и областях Когда применение сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4598f-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="4598f-107">Это позволяет больше контроля в определение, когда мультимедиа обходом сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4598f-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="4598f-108">Для этого используйте действия, описанные в [настройки сервера-посредника глобальных параметров в Скайп для Business Server для использования сведений об узлах и областях](use-site-and-region-information.md) и [связать подсеть с сетевым узлом](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="4598f-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="4598f-109">Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4598f-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="4598f-110">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="4598f-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="4598f-111">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="4598f-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="4598f-112">Дважды щелкните конфигурацию **Глобальная** в данном списке.</span><span class="sxs-lookup"><span data-stu-id="4598f-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="4598f-113">На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="4598f-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="4598f-114">Щелкните **Всегда обходить**.</span><span class="sxs-lookup"><span data-stu-id="4598f-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="4598f-115">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4598f-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4598f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4598f-116">See also</span></span>

[<span data-ttu-id="4598f-117">Планирование для сервера-посредника в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4598f-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="4598f-118">Развертывание сервера-посредника в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="4598f-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

