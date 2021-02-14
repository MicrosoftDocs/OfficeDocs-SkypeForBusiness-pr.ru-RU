---
title: Развертывание роли сервера VIS в Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: Сводка. Развертывание роли сервера видеосвязи (VIS) в Skype для бизнеса Server.
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801969"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="d43e1-103">Развертывание роли сервера VIS в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d43e1-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="d43e1-104">**Сводка:** Развертывание роли сервера видеосвязи (VIS) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d43e1-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="d43e1-105">Чтобы настроить службу VIS на сервере, только что созданном в построите топологий, запустите мастер развертывания Skype для бизнеса Server, нажмите кнопку "Установить" или "Обновить систему Skype для бизнеса **Server"** и выполните следующие действия в мастере:</span><span class="sxs-lookup"><span data-stu-id="d43e1-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="d43e1-106">Выберите **"Установить локальное хранилище конфигурации".**</span><span class="sxs-lookup"><span data-stu-id="d43e1-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="d43e1-107">Выберите **"Установка" или "Удалить компоненты Skype для бизнеса Server".**</span><span class="sxs-lookup"><span data-stu-id="d43e1-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="d43e1-108">Выберите **"Запрос", "Установить" или "Назначить сертификаты".**</span><span class="sxs-lookup"><span data-stu-id="d43e1-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="d43e1-109">Выберите **"Запустить службы".**</span><span class="sxs-lookup"><span data-stu-id="d43e1-109">Select **Start services**.</span></span>
    
<span data-ttu-id="d43e1-110">Программное обеспечение для этой службы теперь установлено и запущено.</span><span class="sxs-lookup"><span data-stu-id="d43e1-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="d43e1-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span><span class="sxs-lookup"><span data-stu-id="d43e1-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="d43e1-112">Далее необходимо настроить сервер или пул СЕРВЕРА VIS.</span><span class="sxs-lookup"><span data-stu-id="d43e1-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="d43e1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d43e1-113">See also</span></span>

[<span data-ttu-id="d43e1-114">Настройка сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d43e1-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
