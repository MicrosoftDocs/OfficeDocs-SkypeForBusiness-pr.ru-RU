---
title: Развертывание VIS серверной роли в Скайп for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Сводка: Разверните роль сервера взаимодействия видео (VIS) в Скайп для Business Server.'
ms.openlocfilehash: 7919b9c02001f0851b3662baa989b0eed0b20225
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219711"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="65624-103">Развертывание VIS серверной роли в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="65624-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="65624-104">**Сводка:** Разверните роль сервера взаимодействия видео (VIS) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="65624-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="65624-105">Чтобы настроить службу VIS на сервере, созданного в построителе топологий, запустите Скайп для мастера развертывания Business Server, нажмите клавишу **Установка или обновление Скайп для бизнес-системе сервера** и выполните следующие действия в мастере:</span><span class="sxs-lookup"><span data-stu-id="65624-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="65624-106">Выберите **Установка локального хранилища конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="65624-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="65624-107">Выберите **Установка или удаление Скайп для бизнеса серверных компонентов**.</span><span class="sxs-lookup"><span data-stu-id="65624-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="65624-108">Выберите **Запросить, установить или назначить сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="65624-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="65624-109">Выберите **Запустить службы**.</span><span class="sxs-lookup"><span data-stu-id="65624-109">Select **Start services**.</span></span>
    
<span data-ttu-id="65624-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="65624-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="65624-111">Можно открыть средством mmc служб, чтобы проверить, установлена ли служба **Скайп для видео взаимодействия Business Server Server** вместе с другими Скайп для служб Business Server.</span><span class="sxs-lookup"><span data-stu-id="65624-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="65624-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="65624-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="65624-113">См. также</span><span class="sxs-lookup"><span data-stu-id="65624-113">See also</span></span>

[<span data-ttu-id="65624-114">Настройка видео взаимодействия сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="65624-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
