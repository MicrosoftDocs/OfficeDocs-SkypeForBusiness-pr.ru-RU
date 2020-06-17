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
description: Если в устаревшем интерфейсном пуле размещается контроль допуска звонков (CAC), необходимо переместить размещение CAC в пул Skype для бизнеса Server 2019, прежде чем можно будет удалить устаревший интерфейсный пул.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753301"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="0b6ba-103">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0b6ba-103">Reset call admission control</span></span>

<span data-ttu-id="0b6ba-104">Если в устаревшем интерфейсном пуле размещается контроль допуска звонков (CAC), необходимо переместить размещение CAC в пул Skype для бизнеса Server 2019, прежде чем можно будет удалить устаревший интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="0b6ba-105">Чтобы сбросить контроль допуска звонков</span><span class="sxs-lookup"><span data-stu-id="0b6ba-105">To reset CAC</span></span>

1. <span data-ttu-id="0b6ba-106">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0b6ba-107">Щелкните правой кнопкой мыши узел сайта, затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0b6ba-108">Убедитесь, что в разделе **Параметры контроля допуска звонков** выбран параметр **Включить контроль допуска звонков**.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="0b6ba-109">В разделе **пул переднего плана для запуска контроля допуска звонков (CAC)** выберите пул Skype для бизнеса Server 2019, на котором размещается CAC, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="0b6ba-110">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="0b6ba-110">Publish the topology.</span></span>
    

