---
title: Включение контроля допуска звонков в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Включение контроля допуска звонков в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 7e4c444b5aa0b0e4d3c3517b9d242c839f6ecda5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872761"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="e3c1f-103">Включение контроля допуска звонков в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e3c1f-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="e3c1f-104">Включение контроля допуска звонков в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="e3c1f-105">Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).</span><span class="sxs-lookup"><span data-stu-id="e3c1f-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e3c1f-106">Включение контроля допуска звонков с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="e3c1f-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e3c1f-107">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e3c1f-p101">Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:</span><span class="sxs-lookup"><span data-stu-id="e3c1f-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="e3c1f-110">Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e3c1f-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e3c1f-111">Включение контроля допуска звонков с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="e3c1f-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e3c1f-112">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e3c1f-113">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="e3c1f-114">Нажмите кнопку навигации **Глобальные**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="e3c1f-115">Выберите **Глобальные** в списке и затем в меню **Изменить** выберите **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="e3c1f-116">На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3c1f-117">Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="e3c1f-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="e3c1f-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e3c1f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e3c1f-119">See also</span></span>

[<span data-ttu-id="e3c1f-120">Командлет Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c1f-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="e3c1f-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c1f-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="e3c1f-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="e3c1f-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
