---
title: Управление учетными записями системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: В этом разделе описывается управление учетными записями системы комнат Skype.
ms.openlocfilehash: 4d3535c9583481273f7a511143244b511cdb5819
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927790"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="c7ab1-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="c7ab1-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="c7ab1-104">В этом разделе описывается управление учетными записями системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="c7ab1-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="c7ab1-105">Версии 2 Скайп комнаты систем — это разные продукт с другой зависимости и процедуры развертывания.</span><span class="sxs-lookup"><span data-stu-id="c7ab1-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="c7ab1-106">Сведения о версии 2 Скайп комнаты систем содержатся v2 систем комнаты Скайп [Общие сведения об управлении](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c7ab1-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="c7ab1-107">Перемещение между пулами Скайп комнаты системной учетной записи</span><span class="sxs-lookup"><span data-stu-id="c7ab1-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="c7ab1-108">Если необходимо переместить Скайп комнаты системную учетную запись из одной Скайп для пула сервера на другой (например, во время обновления), используйте следующую команду для перемещения Скайп комнаты системной учетной записи группы:</span><span class="sxs-lookup"><span data-stu-id="c7ab1-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="c7ab1-109">Отключение Скайп комнаты системную учетную запись для Скайп для бизнес-служб</span><span class="sxs-lookup"><span data-stu-id="c7ab1-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="c7ab1-110">Если требуется отключить существующей системы комнаты Скайп учетной записи из Скайп для бизнес-служб на Скайп для пула Business Server, используйте следующую команду для отключения учетной записи:</span><span class="sxs-lookup"><span data-stu-id="c7ab1-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="c7ab1-111">Необязательно: Создание группы администраторов системы комнаты Скайп в Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7ab1-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="c7ab1-112">Каждый клиент Скайп комнаты системы, который присоединен к домену управляемые пользователем домена с правами локального администратора на устройство системы комнаты Скайп ПК.</span><span class="sxs-lookup"><span data-stu-id="c7ab1-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="c7ab1-113">Таким образом можно создать группу выделенного администраторов в Active Directory и обеспечить административные права этой группы во время set up нового Скайп комнаты системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="c7ab1-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

