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
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="a0fcf-103">Управление учетными записями системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="a0fcf-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="a0fcf-104">В этом разделе описывается управление учетными записями системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="a0fcf-105">Перемещение между пулами Скайп комнаты системной учетной записи</span><span class="sxs-lookup"><span data-stu-id="a0fcf-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="a0fcf-106">Если необходимо переместить Скайп комнаты системную учетную запись из одной Скайп для пула сервера на другой (например, во время обновления), используйте следующую команду для перемещения Скайп комнаты системной учетной записи группы:</span><span class="sxs-lookup"><span data-stu-id="a0fcf-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="a0fcf-107">Отключение Скайп комнаты системную учетную запись для Скайп для бизнес-служб</span><span class="sxs-lookup"><span data-stu-id="a0fcf-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="a0fcf-108">Если требуется отключить существующей системы комнаты Скайп учетной записи из Скайп для бизнес-служб на Скайп для пула Business Server, используйте следующую команду для отключения учетной записи:</span><span class="sxs-lookup"><span data-stu-id="a0fcf-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="a0fcf-109">Необязательно: Создание группы администраторов системы комнаты Скайп в Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0fcf-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="a0fcf-110">Каждый клиент Скайп комнаты системы, который присоединен к домену управляемые пользователем домена с правами локального администратора на устройство системы комнаты Скайп ПК.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="a0fcf-111">Таким образом можно создать группу выделенного администраторов в Active Directory и обеспечить административные права этой группы во время set up нового Скайп комнаты системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

