---
title: Планирование единого хранения контактов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: Сводка. Просмотрите этот раздел при планировании интеграции Skype для бизнеса Server с Exchange 2013.
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816259"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="a9e3f-103">Планирование единого хранения контактов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a9e3f-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a9e3f-104">**Сводка:** Просмотрите этот раздел при планировании интеграции Skype для бизнеса Server с Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="a9e3f-105">Единое хранилище контактов обеспечивает единое контактное отношение к продуктам Microsoft Office и позволяет пользователям хранить все контактные данные в Exchange 2013, но позволяет им быть доступными глобально в Skype для бизнеса, Exchange, Outlook и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="a9e3f-106">Требования для единого хранения контактов</span><span class="sxs-lookup"><span data-stu-id="a9e3f-106">Requirements for unified contact store</span></span>

<span data-ttu-id="a9e3f-107">Чтобы реализовать единое хранилище контактов в Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="a9e3f-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="a9e3f-108">Необходимо использовать Skype для бизнеса Server и Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="a9e3f-109">Пользователи должны использовать Skype для бизнеса для переноса контактов из Skype для бизнеса Server в Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="a9e3f-110">Почтовые ящики пользователей необходимо перенести в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="a9e3f-111">Между Skype для бизнеса Server и Exchange 2013 или 2016 должна быть настроена проверка подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="a9e3f-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9e3f-112">Подробные требования по настройке проверки подлинности между Skype для бизнеса Server и Exchange 2013 или 2016 см. в документации по управлению проверкой подлинности ["сервер-сервер" (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) и партнерскими приложениями в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a9e3f-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9e3f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a9e3f-113">See also</span></span>

[<span data-ttu-id="a9e3f-114">Развертывание единого хранения контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a9e3f-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
