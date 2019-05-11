---
title: Развертывание VIS серверной роли в Скайп for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Сводка: Разверните роль сервера взаимодействия видео (VIS) в Скайп для Business Server.'
ms.openlocfilehash: 109992482490a300125cad7177cc3e6070f2d02a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894586"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="26d19-103">Развертывание VIS серверной роли в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="26d19-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="26d19-104">**Сводка:** Разверните роль сервера взаимодействия видео (VIS) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="26d19-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="26d19-105">Чтобы настроить службу VIS на сервере, созданного в построителе топологий, запустите Скайп для мастера развертывания Business Server, нажмите клавишу **Установка или обновление Скайп для бизнес-системе сервера** и выполните следующие действия в мастере:</span><span class="sxs-lookup"><span data-stu-id="26d19-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="26d19-106">Выберите **Установка локального хранилища конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="26d19-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="26d19-107">Выберите **Установка или удаление Скайп для бизнеса серверных компонентов**.</span><span class="sxs-lookup"><span data-stu-id="26d19-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="26d19-108">Выберите **Запросить, установить или назначить сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="26d19-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="26d19-109">Выберите **Запустить службы**.</span><span class="sxs-lookup"><span data-stu-id="26d19-109">Select **Start services**.</span></span>
    
<span data-ttu-id="26d19-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="26d19-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="26d19-111">Можно открыть средством mmc служб, чтобы проверить, установлена ли служба **Скайп для видео взаимодействия Business Server Server** вместе с другими Скайп для служб Business Server.</span><span class="sxs-lookup"><span data-stu-id="26d19-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="26d19-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="26d19-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="26d19-113">См. также</span><span class="sxs-lookup"><span data-stu-id="26d19-113">See also</span></span>

[<span data-ttu-id="26d19-114">Настройка видео взаимодействия сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="26d19-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
