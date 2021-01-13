---
title: Enable Group Call Pickup for users and assign a group number in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Включить для пользователей групповой выбор звонков в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830969"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="32a06-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="32a06-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="32a06-104">Включить для пользователей групповой выбор звонков в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.</span><span class="sxs-lookup"><span data-stu-id="32a06-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="32a06-105">После того как вы добавите номера группы раздатки вызовов в таблицу орбит парковки вызовов, используйте средство SEFAUtil, чтобы назначить номера групп пользователям и включить для них групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="32a06-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="32a06-106">В гибридном развертывании не назначать группу группового вызова пользователям, которые размещены в Интернете.</span><span class="sxs-lookup"><span data-stu-id="32a06-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="32a06-107">Пользователи, которые находятся в Сети, не могут участвовать в групповом звоноке.</span><span class="sxs-lookup"><span data-stu-id="32a06-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="32a06-108">То есть другие пользователи не могут отвечать на их вызовы, а они не могут отвечать на вызовы других пользователей.</span><span class="sxs-lookup"><span data-stu-id="32a06-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="32a06-109">Назначение номера группы и включить групповой звонок для пользователя</span><span class="sxs-lookup"><span data-stu-id="32a06-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="32a06-110">Войдите на компьютер, на котором установлено средство SEFAUtil, с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="32a06-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="32a06-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="32a06-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="32a06-112">Например, чтобы назначить пользователю номер группы 199:</span><span class="sxs-lookup"><span data-stu-id="32a06-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="32a06-113">См. также</span><span class="sxs-lookup"><span data-stu-id="32a06-113">See also</span></span>

[<span data-ttu-id="32a06-114">Отключение группового разметки для пользователей</span><span class="sxs-lookup"><span data-stu-id="32a06-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

