---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно переместить несколько пользователей из устаревшего пула для вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server.
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888303"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="57861-103">Перемещение нескольких пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="57861-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="57861-104">Можно переместить несколько пользователей из устаревшего пула для вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="57861-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="57861-105">**В этой статье**</span><span class="sxs-lookup"><span data-stu-id="57861-105">**In this article**</span></span>
  
[<span data-ttu-id="57861-106">Перемещение нескольких пользователей с помощью Скайп для панели управления 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="57861-107">Перемещение нескольких пользователей с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="57861-108">Перемещение всех пользователей в то же время с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="57861-109">Перемещение нескольких пользователей с помощью Скайп для панели управления 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="57861-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="57861-110"></span></span>

1. <span data-ttu-id="57861-111">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="57861-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="57861-112">Щелкните элемент **Пользователи**, щелкните **Поиск**и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="57861-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="57861-113">Выберите два пользователя, которые необходимо переместить в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57861-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="57861-114">В этом примере мы будут перемещаться Янг Чен и Клаус Хансен пользователей.</span><span class="sxs-lookup"><span data-stu-id="57861-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Перемещение пользователей в пул регистра](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="57861-116">В меню **Действие** выберите **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="57861-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="57861-117">В раскрывающемся списке выберите Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57861-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="57861-118">Щелкните **Действие**и выберите команду **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="57861-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="57861-119">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57861-119">Click **OK**.</span></span>
    
     ![Перемещение пользователей, диалоговое окно пул регистратора назначения](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="57861-121">Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит Скайп для пула Business Server 2019, это означает, что пользователи были успешно перемещены.</span><span class="sxs-lookup"><span data-stu-id="57861-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="57861-122">Перемещение нескольких пользователей с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="57861-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="57861-123"></span></span>

1. <span data-ttu-id="57861-124">Откройте Скайп для консоли Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57861-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="57861-125">В командной строке введите следующую команду и **User1** и **Пользователь2** заменить имена определенного пользователя, которую требуется переместить и замените **pool_FQDN** имя пула, назначения.</span><span class="sxs-lookup"><span data-stu-id="57861-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="57861-126">В этом примере мы будут перемещаться Чен Хао и Екатериной Иордания пользователей.</span><span class="sxs-lookup"><span data-stu-id="57861-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример командлет PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="57861-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="57861-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="57861-129">Удостоверение **Пула регистратора** теперь должны указывать в пул, указанное в качестве **pool_FQDN** на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="57861-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="57861-130">Наличие это удостоверение подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="57861-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="57861-131">Повторите шаг, чтобы убедиться, что **Пользователь2** был перемещен.</span><span class="sxs-lookup"><span data-stu-id="57861-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Выходные данные PowerShell Get-UsUser-Identity командлета](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="57861-133">Перемещение всех пользователей в то же время с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="57861-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="57861-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="57861-134"></span></span>

<span data-ttu-id="57861-135">В этом примере все пользователи были возвращены в устаревшем пуле (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="57861-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="57861-136">Использование Скайп для консоли 2019 Business Server, мы будет переместить всех пользователей в то же время в Скайп для пула Business Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="57861-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="57861-137">Откройте Скайп для консоли Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57861-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="57861-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="57861-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Командлет PowerShell и результатов в командной консоли](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="57861-140">Выполните **Командлет Get-CsUser** для одного из пробных пользователей.</span><span class="sxs-lookup"><span data-stu-id="57861-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="57861-141">Удостоверение **Пула регистратора** для каждого пользователя теперь указывает на пул, указанное в качестве **pool_FQDN** на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="57861-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="57861-142">Наличие это удостоверение подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="57861-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="57861-143">Кроме того мы можно просмотреть список пользователей в Скайп для панели управления 2019 Business Server и убедитесь, что пул регистратора значение указывает на Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="57861-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Скайп для списка пользователей панели управления 2019 Business Server](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

