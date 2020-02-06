---
title: Планирование единого магазина контактов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Аннотация: Изучите этот раздел, планируя интеграцию Skype для бизнеса Server с Exchange 2013.'
ms.openlocfilehash: fbc361dab4414ea2add286144be48b922a9d9247
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815877"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="3c59b-103">План для единого хранилища контактов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c59b-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c59b-104">**Сводка:** Ознакомьтесь с этим разделом в процессе планирования интеграции Skype для бизнеса Server с Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="3c59b-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="3c59b-105">Единое хранилище контактов обеспечивает согласованное взаимодействие между продуктами Microsoft Office и позволяет пользователям хранить все контактные данные в Exchange 2013, но обеспечивает возможность их глобального доступа в Skype для бизнеса, Exchange и Outlook. и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3c59b-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="3c59b-106">Требования к единому хранилищу контактов</span><span class="sxs-lookup"><span data-stu-id="3c59b-106">Requirements for unified contact store</span></span>

<span data-ttu-id="3c59b-107">Чтобы внедрить единое хранилище контактов в Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3c59b-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="3c59b-108">На вашем компьютере должны быть установлены Skype для бизнеса Server и Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="3c59b-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="3c59b-109">Пользователи должны использовать Skype для бизнеса для переноса контактов из Skype для бизнеса Server в Exchange 2013 и 2016.</span><span class="sxs-lookup"><span data-stu-id="3c59b-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="3c59b-110">Почтовые ящики пользователей должны быть перенесены в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3c59b-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="3c59b-111">Требуется проверка подлинности серверов в Skype для бизнеса Server и Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="3c59b-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c59b-112">Подробные сведения о настройке проверки подлинности между Skype для бизнеса Server и Exchange 2013 и 2016: [Управление приложениями для проверки подлинности серверов (OAuth) и партнерских программ в Skype для бизнеса Server](../../manage/authentication/server-to-server-and-partner-applications.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="3c59b-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c59b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3c59b-113">See also</span></span>

[<span data-ttu-id="3c59b-114">Развертывание единого магазина контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3c59b-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
