---
title: Управление учетными записями системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: В этом разделе описывается управление учетными записями системы комнат Skype.
ms.openlocfilehash: d1cd40b12da89eed651152dd3b7b91914826d62e
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268475"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="ed5f7-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="ed5f7-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="ed5f7-104">В этом разделе описывается управление учетными записями системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="ed5f7-105">Комнаты Microsoft Teams — это другой продукт с разными зависимостями и процедурами развертывания.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="ed5f7-106">Сведения о комнатах Microsoft Teams можно найти в разделе [Общие сведения об управлении](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="ed5f7-107">Перемещение учетной записи системы комнаты Skype между пулами</span><span class="sxs-lookup"><span data-stu-id="ed5f7-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="ed5f7-108">Если вам нужно перенести учетную запись системы комнаты Skype из одного пула серверов Skype для бизнеса в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы для помещения в Skype.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="ed5f7-109">Отключение учетной записи системы комнаты Skype для служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed5f7-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="ed5f7-110">Если вам нужно отключить существующую учетную запись комнаты Skype для служб Skype для бизнеса в пуле сервера Skype для бизнеса, используйте следующую команду для отключения учетной записи:</span><span class="sxs-lookup"><span data-stu-id="ed5f7-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="ed5f7-111">Необязательно: создание группы администраторов комнатной комнаты Skype в службе каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed5f7-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="ed5f7-112">Каждый клиент системы комнаты Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами локального администратора на компьютере с системой управления комнатой Skype на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="ed5f7-113">Таким образом, вы можете создать группу выделенных администраторов в службе каталогов Active Directory и предоставить этой группе права администратора во время настройки нового компьютера с операционной системой комнаты для Skype.</span><span class="sxs-lookup"><span data-stu-id="ed5f7-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

