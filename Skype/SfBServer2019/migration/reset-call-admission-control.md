---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753301"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="bd694-103">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="bd694-103">Reset call admission control</span></span>

<span data-ttu-id="bd694-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span><span class="sxs-lookup"><span data-stu-id="bd694-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="bd694-105">Чтобы сбросить контроль допуска звонков</span><span class="sxs-lookup"><span data-stu-id="bd694-105">To reset CAC</span></span>

1. <span data-ttu-id="bd694-106">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="bd694-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="bd694-107">Щелкните правой кнопкой мыши узел сайта, затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bd694-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="bd694-108">Убедитесь, что в разделе **Параметры контроля допуска звонков** выбран параметр **Включить контроль допуска звонков**.</span><span class="sxs-lookup"><span data-stu-id="bd694-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="bd694-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd694-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="bd694-110">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="bd694-110">Publish the topology.</span></span>
    

