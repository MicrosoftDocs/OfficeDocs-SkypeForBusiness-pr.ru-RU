---
title: Управление учетными записями системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: В этом разделе описывается управление учетными записями системы комнат Skype.
ms.openlocfilehash: 2a45fc8507b9b09b777e6aa91c47fff2b3dfc3d2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234075"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="6ca3e-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="6ca3e-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="6ca3e-104">В этом разделе описывается управление учетными записями системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="6ca3e-105">Комнаты Microsoft Teams — это другой продукт с разными зависимостями и процедурами развертывания.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="6ca3e-106">Сведения о комнатах Microsoft Teams можно найти в разделе [Общие сведения об управлении](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="6ca3e-107">Перемещение учетной записи системы комнаты Skype между пулами</span><span class="sxs-lookup"><span data-stu-id="6ca3e-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="6ca3e-108">Если вам нужно перенести учетную запись системы комнаты Skype из одного пула серверов Skype для бизнеса в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы для помещения в Skype.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="6ca3e-109">Отключение учетной записи системы комнаты Skype для служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6ca3e-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="6ca3e-110">Если вам нужно отключить существующую учетную запись комнаты Skype для служб Skype для бизнеса в пуле сервера Skype для бизнеса, используйте следующую команду для отключения учетной записи:</span><span class="sxs-lookup"><span data-stu-id="6ca3e-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="6ca3e-111">Необязательно: создание группы администраторов комнатной комнаты Skype в службе каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ca3e-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="6ca3e-112">Каждый клиент системы комнаты Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами локального администратора на компьютере с системой управления комнатой Skype на устройстве.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="6ca3e-113">Таким образом, вы можете создать группу выделенных администраторов в службе каталогов Active Directory и предоставить этой группе права администратора во время настройки нового компьютера с операционной системой комнаты для Skype.</span><span class="sxs-lookup"><span data-stu-id="6ca3e-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

