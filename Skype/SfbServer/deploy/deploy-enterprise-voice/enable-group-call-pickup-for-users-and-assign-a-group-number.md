---
title: Включение отправки группового звонка для пользователей и назначение номера группы в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Предоставление пользователям возможности отправки группового звонка в Skype для бизнеса Server Enterprise и назначение номера группы.
ms.openlocfilehash: 14f17d3e217fa9ea44cc81db4d8fa6bf12644894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291583"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="07ca3-103">Включение отправки группового звонка для пользователей и назначение номера группы в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="07ca3-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="07ca3-104">Предоставление пользователям возможности отправки группового звонка в Skype для бизнеса Server Enterprise и назначение номера группы.</span><span class="sxs-lookup"><span data-stu-id="07ca3-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="07ca3-105">После добавления номеров групп для отправки звонков в таблицу "приостановить Звонок" вы можете использовать средство Сефаутил, чтобы назначить номера групп пользователям и включить для них функцию отправки групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="07ca3-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="07ca3-106">В гибридном развертывании не назначайте группу отправки группового звонка пользователям, которые находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="07ca3-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="07ca3-107">Пользователи, которые подключены к сети, не могут принимать участие в расправке групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="07ca3-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="07ca3-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span><span class="sxs-lookup"><span data-stu-id="07ca3-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="07ca3-109">Назначение номера группы и включение отправки группового звонка для пользователя</span><span class="sxs-lookup"><span data-stu-id="07ca3-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="07ca3-110">Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="07ca3-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="07ca3-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ca3-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="07ca3-112">Например, чтобы назначить пользователю групповой номер 199, введите:</span><span class="sxs-lookup"><span data-stu-id="07ca3-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="07ca3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="07ca3-113">See also</span></span>

[<span data-ttu-id="07ca3-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="07ca3-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

