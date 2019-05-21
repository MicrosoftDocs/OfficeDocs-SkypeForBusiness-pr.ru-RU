---
title: Развертывание роли сервера ВИС в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Сводка: развертывание роли сервера видеосвязи (ВИС) в Skype для бизнеса Server.'
ms.openlocfilehash: 963c934846af2f791e7efde48f8b4ddd5be3dcb2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302723"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="79489-103">Развертывание роли сервера ВИС в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79489-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="79489-104">**Сводка:** Разверните роль сервера видеосвязи (ВИС) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="79489-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="79489-105">Чтобы настроить службу ВИС на сервере, который только что создан в построителе топологии, запустите мастер развертывания Skype для бизнеса Server, нажмите "установить" или "Обновить" в **системе Skype для бизнеса Server** , а затем выполните следующие действия в мастере.</span><span class="sxs-lookup"><span data-stu-id="79489-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="79489-106">Выберите **Установка локального хранилища конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="79489-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="79489-107">Выберите пункт **Настройка или удалите компоненты Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="79489-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="79489-108">Выберите **Запросить, установить или назначить сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="79489-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="79489-109">Выберите **Запустить службы**.</span><span class="sxs-lookup"><span data-stu-id="79489-109">Select **Start services**.</span></span>
    
<span data-ttu-id="79489-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="79489-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="79489-111">Вы можете открыть средство MMC "службы", чтобы узнать, работает ли служба сервера видеосвязи **Skype для бизнеса Server** с другими службами Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="79489-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="79489-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="79489-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="79489-113">См. также</span><span class="sxs-lookup"><span data-stu-id="79489-113">See also</span></span>

[<span data-ttu-id="79489-114">Настройка сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79489-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
