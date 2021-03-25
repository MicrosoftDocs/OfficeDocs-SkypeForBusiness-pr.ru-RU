---
title: Включить групповую подбираемую группу для пользователей и назначить номер группы в Skype для бизнеса
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
description: Включить пользователей для группового вызова в Skype для бизнеса server Корпоративная голосовая связь и назначить номер группы.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111835"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="44690-103">Включить групповую подбираемую группу для пользователей и назначить номер группы в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="44690-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="44690-104">Включить пользователей для группового вызова в Skype для бизнеса server Корпоративная голосовая связь и назначить номер группы.</span><span class="sxs-lookup"><span data-stu-id="44690-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="44690-105">После добавления номеров групп вызова в таблицу орбиты парка вызовов используется средство SEFAUtil, чтобы назначить групповые номера пользователям и включить для них групповую группу вызова.</span><span class="sxs-lookup"><span data-stu-id="44690-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="44690-106">В гибридном развертывании не назначать группу группового вызова пользователям, которые размещены в Интернете.</span><span class="sxs-lookup"><span data-stu-id="44690-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="44690-107">Пользователи, которые находятся в сети, не могут участвовать в групповом вызове.</span><span class="sxs-lookup"><span data-stu-id="44690-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="44690-108">То есть другие пользователи не могут отвечать на их звонки, а другие пользователи не могут отвечать на звонки.</span><span class="sxs-lookup"><span data-stu-id="44690-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="44690-109">Назначение группового номера и возможность группового вызова для пользователя</span><span class="sxs-lookup"><span data-stu-id="44690-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="44690-110">Войдите на компьютер, на котором установлен инструмент SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="44690-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="44690-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="44690-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="44690-112">Например, назначить пользователю номер группы 199:</span><span class="sxs-lookup"><span data-stu-id="44690-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="44690-113">См. также</span><span class="sxs-lookup"><span data-stu-id="44690-113">See also</span></span>

[<span data-ttu-id="44690-114">Отключение группового пикапа для пользователей</span><span class="sxs-lookup"><span data-stu-id="44690-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)