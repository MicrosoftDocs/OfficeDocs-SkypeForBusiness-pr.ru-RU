---
title: Включить управление приемом вызовов в Skype для бизнеса Server
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Включить управление приемом вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 2b8096a9223250cec88e57e68fdc201f5591fd92
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109865"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="29a25-103">Включить управление приемом вызовов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="29a25-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="29a25-104">Включить управление приемом вызовов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="29a25-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="29a25-105">Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).</span><span class="sxs-lookup"><span data-stu-id="29a25-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="29a25-106">Включить управление приемом вызовов с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="29a25-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="29a25-107">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="29a25-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="29a25-p101">Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:</span><span class="sxs-lookup"><span data-stu-id="29a25-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="29a25-110">Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="29a25-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="29a25-111">Включить управление приемом вызовов с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="29a25-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="29a25-112">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="29a25-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="29a25-113">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="29a25-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="29a25-114">Нажмите кнопку навигации **Global** (Глобальные).</span><span class="sxs-lookup"><span data-stu-id="29a25-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="29a25-115">Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="29a25-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="29a25-116">На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).</span><span class="sxs-lookup"><span data-stu-id="29a25-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29a25-117">Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="29a25-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="29a25-118">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="29a25-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="29a25-119">См. также</span><span class="sxs-lookup"><span data-stu-id="29a25-119">See also</span></span>

[<span data-ttu-id="29a25-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29a25-120">Get-CsNetworkConfiguration</span></span>](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="29a25-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29a25-121">Set-CsNetworkConfiguration</span></span>](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="29a25-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="29a25-122">Remove-CsNetworkConfiguration</span></span>](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)