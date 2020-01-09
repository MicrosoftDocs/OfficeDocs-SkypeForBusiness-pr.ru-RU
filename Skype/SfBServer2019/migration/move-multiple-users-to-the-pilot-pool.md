---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете переместить нескольких пользователей из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.
ms.openlocfilehash: abaffea04ff190b2ae99639484f63b564fd7784a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988954"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="42496-103">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="42496-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="42496-104">Вы можете переместить нескольких пользователей из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42496-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="42496-105">**В этой статье**</span><span class="sxs-lookup"><span data-stu-id="42496-105">**In this article**</span></span>
  
[<span data-ttu-id="42496-106">Перемещение нескольких пользователей с помощью панели управления "Skype для бизнеса Server 2019"</span><span class="sxs-lookup"><span data-stu-id="42496-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="42496-107">Перемещение нескольких пользователей с помощью управляющей оболочки Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="42496-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="42496-108">Перемещение всех пользователей одновременно с помощью управляющей оболочки Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="42496-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="42496-109">Перемещение нескольких пользователей с помощью панели управления "Skype для бизнеса Server 2019"</span><span class="sxs-lookup"><span data-stu-id="42496-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="42496-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="42496-110"></span></span>

1. <span data-ttu-id="42496-111">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42496-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="42496-112">Нажмите кнопку **Пользователи**, нажмите **Поиск**, а затем — **найти**.</span><span class="sxs-lookup"><span data-stu-id="42496-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="42496-113">Выберите двух пользователей, которых вы хотите переместить в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42496-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="42496-114">В этом примере мы перейдем пользователей Чена Маслов и предложения Хансен.</span><span class="sxs-lookup"><span data-stu-id="42496-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Перемещение пользователей в определенную группу регистров](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="42496-116">В меню **действия** выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="42496-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="42496-117">В раскрывающемся списке выберите пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42496-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="42496-118">Нажмите кнопку **действие**и выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="42496-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="42496-119">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="42496-119">Click **OK**.</span></span>
    
     ![Перемещение пользователей, диалоговое окно «пул конечных регистраторов»](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="42496-121">Убедитесь в том, что столбец **пула регистратора** для пользователей теперь содержит пул Skype для бизнеса Server 2019, указывающий на то, что пользователи успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="42496-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="42496-122">Перемещение нескольких пользователей с помощью управляющей оболочки Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="42496-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="42496-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="42496-123"></span></span>

1. <span data-ttu-id="42496-124">Откройте консоль управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42496-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="42496-125">В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** именами пользователей, которых вы хотите переместить, и замените **pool_FQDN** именем целевого пула.</span><span class="sxs-lookup"><span data-stu-id="42496-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="42496-126">В этом примере мы перейдем пользователей Хао Чен и Katie Иордания.</span><span class="sxs-lookup"><span data-stu-id="42496-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример командлета Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="42496-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42496-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="42496-129">Удостоверение **пула регистратора** теперь должно указывать на пул, который вы указали, как **pool_FQDN** на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="42496-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="42496-130">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="42496-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="42496-131">Повторите действия, чтобы убедиться, что **Пользователь2** перемещен.</span><span class="sxs-lookup"><span data-stu-id="42496-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Вывод командлета PowerShell Get-Усусер-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="42496-133">Перемещение всех пользователей одновременно с помощью управляющей оболочки Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="42496-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="42496-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="42496-134"></span></span>

<span data-ttu-id="42496-135">В этом примере все пользователи возвращены в пул устаревших версий (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="42496-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="42496-136">С помощью командной консоли Skype для бизнеса Server 2019 все пользователи одновременно будут переноситься в пул "Skype для бизнеса Server 2019" (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="42496-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="42496-137">Откройте консоль управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42496-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="42496-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42496-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Командлет PowerShell и результаты в командной консоли](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="42496-140">Запустите **Get-CsUser** для одного из пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="42496-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="42496-141">Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный в предыдущем действии, **pool_FQDN** .</span><span class="sxs-lookup"><span data-stu-id="42496-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="42496-142">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="42496-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="42496-143">Кроме того, мы можем просмотреть список пользователей на панели управления Skype для бизнеса Server 2019 и убедиться, что значение пула регистратора теперь указывает на пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="42496-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Список пользователей панели управления Skype для бизнеса Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

