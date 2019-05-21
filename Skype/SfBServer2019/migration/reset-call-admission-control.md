---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если в устаревшем пуле переднего плана размещается управление допуском звонков (CAC), перед удалением устаревшего пула переднего плана необходимо переместить сервер CAC в пул 2019 в Skype для бизнеса Server.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307100"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="492c0-103">Сброс контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="492c0-103">Reset call admission control</span></span>

<span data-ttu-id="492c0-104">Если в устаревшем пуле переднего плана размещается управление допуском звонков (CAC), перед удалением устаревшего пула переднего плана необходимо переместить сервер CAC в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="492c0-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="492c0-105">Чтобы сбросить параметры CAC</span><span class="sxs-lookup"><span data-stu-id="492c0-105">To reset CAC</span></span>

1. <span data-ttu-id="492c0-106">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="492c0-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="492c0-107">Щелкните правой кнопкой мыши узел сайта и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="492c0-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="492c0-108">Убедитесь, что в разделе **параметр управления**допуском звонков установлен флажок **включить управление допуском звонков** .</span><span class="sxs-lookup"><span data-stu-id="492c0-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="492c0-109">В разделе **пул переднего плана, чтобы запустить управление допуском звонков (CAC)**, выберите пул 2019 Skype для бизнеса Server, на котором размещается CAC, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="492c0-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="492c0-110">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="492c0-110">Publish the topology.</span></span>
    

