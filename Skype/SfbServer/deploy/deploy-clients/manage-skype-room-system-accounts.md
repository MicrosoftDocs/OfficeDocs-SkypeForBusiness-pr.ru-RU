---
title: Управление учетными записями системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: В этом разделе вы узнаете, как управлять учетной записью системы комнат Skype.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805559"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="040e1-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="040e1-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="040e1-104">В этом разделе вы узнаете, как управлять учетной записью системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="040e1-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="040e1-105">Комнаты Microsoft Teams — это другой продукт с разными зависимостями и процедурами развертывания.</span><span class="sxs-lookup"><span data-stu-id="040e1-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="040e1-106">Сведения о комнатах Microsoft Teams см. в обзоре управления комнатами Microsoft [Teams.](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)</span><span class="sxs-lookup"><span data-stu-id="040e1-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="040e1-107">Перемещение учетной записи системы комнат Skype между пулами</span><span class="sxs-lookup"><span data-stu-id="040e1-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="040e1-108">Если необходимо переместить учетную запись системы комнат Skype из одного пула Skype для бизнеса Server в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы комнат Skype:</span><span class="sxs-lookup"><span data-stu-id="040e1-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="040e1-109">Отключение учетной записи системы комнат Skype для служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="040e1-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="040e1-110">Чтобы отключить существующую учетную запись системы комнат Skype для бизнеса в пуле Skype для бизнеса Server, используйте следующую команду для отключения учетной записи:</span><span class="sxs-lookup"><span data-stu-id="040e1-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="040e1-111">Необязательно: создание группы администраторов системы комнат Skype в Active Directory</span><span class="sxs-lookup"><span data-stu-id="040e1-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="040e1-112">Каждый клиент системы комнат Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами локального администратора на компьютере устройства системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="040e1-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="040e1-113">Таким образом, вы можете создать выделенную группу администраторов в Active Directory и предоставить ей права администратора во время создания нового компьютера системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="040e1-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

