---
title: Предоставление учетных записей Exchange и Skype для системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: В этих разделах содержатся сведения о предоставлении учетных записей Exchange и Skype для системы комнат Skype.
ms.openlocfilehash: 2da978d84ac763a27bba135e1899e83955b4fb53
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012556"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="39f94-103">Предоставление учетных записей Exchange и Skype для системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="39f94-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="39f94-104">В этих разделах содержатся сведения о предоставлении учетных записей Exchange и Skype для системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="39f94-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="39f94-105">Комнат группами Майкрософт — это разные продукт с другой зависимости и процедуры развертывания.</span><span class="sxs-lookup"><span data-stu-id="39f94-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="39f94-106">Сведения о комнат группы Microsoft содержатся [Общие сведения о развертывании](room-systems-v2.md)комнат группы Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39f94-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="39f94-107">Подготовка учетных записей системы комнаты Скайп зависит от типа topology в вашей организации есть.</span><span class="sxs-lookup"><span data-stu-id="39f94-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="39f94-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39f94-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="39f94-109">Подготовку комнаты Скайп системы Exchange &amp; Скайп для бизнес-партнеры</span><span class="sxs-lookup"><span data-stu-id="39f94-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="39f94-110">В следующих разделах содержатся инструкции о предоставлении и организации учетных записей Exchange и Skype для бизнеса с системой комнат Skype для следующего:</span><span class="sxs-lookup"><span data-stu-id="39f94-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="39f94-111">Развертывание одного локального леса</span><span class="sxs-lookup"><span data-stu-id="39f94-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="39f94-112">Развертывание нескольких локальных лесов</span><span class="sxs-lookup"><span data-stu-id="39f94-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="39f94-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="39f94-113">Office 365</span></span>
    
- <span data-ttu-id="39f94-114">Гибридное развертывание</span><span class="sxs-lookup"><span data-stu-id="39f94-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="39f94-115">Федеративные партнеры системы комнат Skype и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="39f94-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="39f94-116">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="39f94-116">Manage Skype Room System accounts</span></span>
    

