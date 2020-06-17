---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете переместить нескольких пользователей из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753431"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="5aa9e-103">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="5aa9e-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="5aa9e-104">Вы можете переместить нескольких пользователей из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="5aa9e-105">**Содержание**</span><span class="sxs-lookup"><span data-stu-id="5aa9e-105">**In this article**</span></span>
  
[<span data-ttu-id="5aa9e-106">Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="5aa9e-107">Перемещение нескольких пользователей с помощью командной консоли Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="5aa9e-108">Перемещение всех пользователей одновременно с помощью командной консоли Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="5aa9e-109">Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="5aa9e-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="5aa9e-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="5aa9e-111">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5aa9e-112">Нажмите кнопку **Пользователи**, выберите **Поиск**, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="5aa9e-113">Выберите двух пользователей, которых нужно переместить в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="5aa9e-114">В этом примере мы переместим пользователей Chen Yang и Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Перемещение пользователей в определенный пул регистров](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="5aa9e-116">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="5aa9e-117">В раскрывающемся списке выберите пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="5aa9e-118">В меню **действие**выберите команду **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="5aa9e-119">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-119">Click **OK**.</span></span>
    
     ![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="5aa9e-121">Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит пул Skype для бизнеса Server 2019, указывающий, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="5aa9e-122">Перемещение нескольких пользователей с помощью командной консоли Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="5aa9e-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="5aa9e-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="5aa9e-124">Откройте консоль управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="5aa9e-125">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** на конкретные имена пользователей, которые требуется переместить, и замените **pool_FQDN** именем конечного пула.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="5aa9e-126">В этом примере мы переместим пользователей Hao Chen и Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример командлета PowerShell Get — CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="5aa9e-128">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5aa9e-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="5aa9e-129">Удостоверение **Пул регистратора** должно сейчас указывать на пул, заданный на предыдущем шаге как **pool_FQDN**.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="5aa9e-130">Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="5aa9e-131">Повторите шаг, чтобы убедиться, что перемещается **Пользователь2** .</span><span class="sxs-lookup"><span data-stu-id="5aa9e-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Выходные данные командлета PowerShell Get – Усусер — Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="5aa9e-133">Перемещение всех пользователей одновременно с помощью командной консоли Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="5aa9e-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="5aa9e-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="5aa9e-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="5aa9e-135">В этом примере все пользователи были возвращены в пул устаревших версий (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="5aa9e-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="5aa9e-136">С помощью командной консоли Skype для бизнеса Server 2019 все пользователи будут перемещены одновременно в пул Skype для бизнеса Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="5aa9e-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="5aa9e-137">Откройте консоль управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="5aa9e-138">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5aa9e-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Командлет PowerShell и результаты в командной консоли](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="5aa9e-140">Выполните командлет **Get – CsUser** для одного из пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="5aa9e-141">Удостоверение **пула регистратора** для каждого пользователя теперь указывает на пул, указанный как **pool_FQDN** на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="5aa9e-142">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="5aa9e-143">Кроме того, можно просмотреть список пользователей в панели управления Skype для бизнеса Server 2019 и проверить, что значение пула регистратора теперь указывает на пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5aa9e-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Список пользователей панели управления Skype для бизнеса Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

