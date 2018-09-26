---
title: Сброс контроля допуска звонков
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если устаревшего пула переднего плана размещен контроль допуска звонков (CAC), необходимо переместить контроль допуска звонков размещения для Скайп для пула Business Server 2019, прежде чем удалять устаревшие пула переднего плана.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027321"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="783b0-103">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="783b0-103">Reset call admission control</span></span>

<span data-ttu-id="783b0-104">Если устаревшего пула переднего плана размещен контроль допуска звонков (CAC), необходимо переместить контроль допуска звонков размещения для Скайп для пула Business Server 2019, прежде чем удалять устаревшие пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="783b0-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="783b0-105">Чтобы сбросить контроль допуска звонков</span><span class="sxs-lookup"><span data-stu-id="783b0-105">To reset CAC</span></span>

1. <span data-ttu-id="783b0-106">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="783b0-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="783b0-107">Щелкните правой кнопкой мыши узел сайта и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="783b0-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="783b0-108">В разделе **Параметры контроля допуска звонков**убедитесь в том, что выбран параметр **Включить контроль допуска звонков** .</span><span class="sxs-lookup"><span data-stu-id="783b0-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="783b0-109">В разделе **пул переднего плана для запуска контроля допуска звонков (CAC)** выберите Скайп для Business Server 2019 пула, который должен размещаться контроля допуска звонков и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="783b0-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="783b0-110">Публикация топологии.</span><span class="sxs-lookup"><span data-stu-id="783b0-110">Publish the topology.</span></span>
    

