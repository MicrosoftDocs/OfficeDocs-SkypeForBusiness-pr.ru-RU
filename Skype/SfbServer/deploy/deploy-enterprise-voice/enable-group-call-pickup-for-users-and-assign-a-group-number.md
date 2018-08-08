---
title: Включение раскладки вызова группа для пользователей и назначение номер группы в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Предоставление пользователям для отправки вызовов группы в Скайп Business Server корпоративной голосовой связи и назначьте номер группы.
ms.openlocfilehash: 5a4173a16a40557742a7cdbd47edb917f89b4737
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006522"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="81271-103">Включение раскладки вызова группа для пользователей и назначение номер группы в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="81271-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span> 
 
<span data-ttu-id="81271-104">Предоставление пользователям для отправки вызовов группы в Скайп Business Server корпоративной голосовой связи и назначьте номер группы.</span><span class="sxs-lookup"><span data-stu-id="81271-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="81271-105">После добавления номеров раскладки групповой звонок в таблице орбит парковки вызовов воспользоваться средством SEFAUtil нумерации группы пользователей и включить раскладки вызывать группу для них.</span><span class="sxs-lookup"><span data-stu-id="81271-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81271-106">В гибридном развертывании не Назначение группы вызова раскладки группы пользователей, которые размещаются в Интернете.</span><span class="sxs-lookup"><span data-stu-id="81271-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="81271-107">Пользователи, которые размещаются в Интернете не может участвовать в группы вызова раскладки.</span><span class="sxs-lookup"><span data-stu-id="81271-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="81271-108">То есть другим пользователям не удается ответить на их звонки, и они не могут отвечать на звонки другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="81271-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="81271-109">Чтобы назначить номер группы и включения раскладки вызывать группу для пользователя</span><span class="sxs-lookup"><span data-stu-id="81271-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="81271-110">Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="81271-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="81271-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="81271-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="81271-112">Например, чтобы назначить пользователю групповой номер 199, введите:</span><span class="sxs-lookup"><span data-stu-id="81271-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="81271-113">См. также</span><span class="sxs-lookup"><span data-stu-id="81271-113">See also</span></span>

[<span data-ttu-id="81271-114">Отключить группы раскладки для пользователей</span><span class="sxs-lookup"><span data-stu-id="81271-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

