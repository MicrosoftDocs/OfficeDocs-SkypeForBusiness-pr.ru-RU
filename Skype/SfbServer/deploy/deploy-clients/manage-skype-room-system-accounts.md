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
description: Ознакомьтесь с этой темой, чтобы узнать, как управлять учетной записью skype Room System.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093297"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="d7258-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="d7258-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="d7258-104">Ознакомьтесь с этой темой, чтобы узнать, как управлять учетной записью skype Room System.</span><span class="sxs-lookup"><span data-stu-id="d7258-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7258-105">Microsoft Teams Rooms — это другой продукт с различными зависимостями и процедурами развертывания.</span><span class="sxs-lookup"><span data-stu-id="d7258-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="d7258-106">Сведения о комнатах Microsoft Teams см. в обзоре управления Microsoft Teams [Rooms.](/microsoftteams/rooms/rooms-manage)</span><span class="sxs-lookup"><span data-stu-id="d7258-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="d7258-107">Перемещение учетной записи Skype Room System между пулами</span><span class="sxs-lookup"><span data-stu-id="d7258-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="d7258-108">Если вам необходимо переместить учетную запись системы Skype Room System из одного пула Skype для бизнес-сервера в другую (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы номеров Skype:</span><span class="sxs-lookup"><span data-stu-id="d7258-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="d7258-109">Отключение учетной записи skype Room System для служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d7258-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="d7258-110">Если вам необходимо отключить существующую учетную запись Skype Room System из служб Skype для бизнеса в пуле Skype для бизнеса Server, используйте следующую команду, чтобы отключить учетную запись:</span><span class="sxs-lookup"><span data-stu-id="d7258-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="d7258-111">Необязательный вариант: создайте группу администратора системы номеров Skype в Active Directory</span><span class="sxs-lookup"><span data-stu-id="d7258-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="d7258-112">Каждый клиент системы номеров Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами местного администратора на компьютере устройства Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="d7258-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="d7258-113">Таким образом, вы можете создать группу выделенных администраторов в Active Directory и предоставить этой группе административные права во время создания нового компьютера системы номеров Skype.</span><span class="sxs-lookup"><span data-stu-id="d7258-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
