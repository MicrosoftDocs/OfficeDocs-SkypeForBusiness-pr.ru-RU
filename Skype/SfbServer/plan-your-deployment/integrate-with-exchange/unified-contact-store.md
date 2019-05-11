---
title: Планирование единое хранилище контактов в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: 'Сводка: Изучите раздел при планировании интеграции Скайп для Business Server с Exchange 2013.'
ms.openlocfilehash: c69e4990a77ec56ec74f1a1ac8d37c0c25872696
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907203"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="dbecb-103">План для единого хранилища контактов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dbecb-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dbecb-104">**Сводка:** Просмотрите этот раздел при планировании интеграции Скайп для Business Server с Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="dbecb-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="dbecb-105">Единое хранилище контактов обеспечивает согласованность контакта в разных продуктов Microsoft Office и позволяет пользователям хранить все контактные данные в Exchange 2013, но обеспечивает сведения будут доступны глобально в Скайп для бизнеса, Exchange, Outlook и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="dbecb-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="dbecb-106">Требования к единому хранилищу контактов</span><span class="sxs-lookup"><span data-stu-id="dbecb-106">Requirements for unified contact store</span></span>

<span data-ttu-id="dbecb-107">Для реализации единого хранилища контактов в Скайп для Business Server:</span><span class="sxs-lookup"><span data-stu-id="dbecb-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="dbecb-108">Вы должны работать под управлением Скайп Business Server и Exchange 2013 или 2016.</span><span class="sxs-lookup"><span data-stu-id="dbecb-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="dbecb-109">Пользователи должны использовать для переноса свои контакты из Скайп для сервера Exchange 2013 или 2016 Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dbecb-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="dbecb-110">Почтовые ящики пользователей необходимо перенести в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="dbecb-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="dbecb-111">Необходимо настроить между Скайп Business Server и Exchange 2013 или 2016 проверки подлинности сервер сервер.</span><span class="sxs-lookup"><span data-stu-id="dbecb-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dbecb-112">Подробное описание требований о настройке проверки подлинности между Скайп Business Server и Exchange 2013 или 2016 содержатся в разделе [Управление проверки подлинности сервер сервер (OAuth) и партнерских приложений в Скайп для Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) операций Документация по.</span><span class="sxs-lookup"><span data-stu-id="dbecb-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dbecb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dbecb-113">See also</span></span>

[<span data-ttu-id="dbecb-114">Развертывание единого хранилища контактов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dbecb-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
