---
title: Перемещение одного пользователя в пилотный пул
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно переместить пользователя из устаревшего пула в вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server. В следующем примере, в столбец пул регистратора pool01.contoso.net является устаревшего пула и все шесть из этих пользователей подключения в этот пул. Используйте следующие процедуры для перехода пользователя к вашей Скайп для пула Business Server 2019, с помощью Скайп для панели управления 2019 Business Server и Скайп для консоли Business Server.
ms.openlocfilehash: 6742c5fc00c9d53030ac32ee698686bb8b11fa07
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372747"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="f86dc-105">Перемещение одного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="f86dc-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="f86dc-106">Можно переместить пользователя из устаревшего пула в вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="f86dc-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="f86dc-107">В следующем примере, в столбце **пул регистратора** **pool01.contoso.net** является устаревшего пула и все шесть из этих пользователей подключения в этот пул.</span><span class="sxs-lookup"><span data-stu-id="f86dc-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="f86dc-108">Используйте следующие процедуры для перехода пользователя к вашей Скайп для пула Business Server 2019, с помощью Скайп для панели управления 2019 Business Server и Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="f86dc-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f86dc-109">Перемещение пользователя с помощью Скайп для панели управления 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="f86dc-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="f86dc-110">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f86dc-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f86dc-111">Откройте **Скайп для панели управления Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f86dc-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="f86dc-112">Щелкните элемент **Пользователи**, щелкните **Поиск**и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="f86dc-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="f86dc-113">Выберите пользователя, который требуется переместить в Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f86dc-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f86dc-114">В этом примере мы будет переместить пользователя пользователя Валентины.</span><span class="sxs-lookup"><span data-stu-id="f86dc-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="f86dc-115">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="f86dc-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="f86dc-116">В раскрывающемся списке выберите Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f86dc-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="f86dc-117">Щелкните **Действие**и выберите команду **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="f86dc-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="f86dc-118">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f86dc-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="f86dc-119">Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит Скайп для пула Business Server 2019, это означает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="f86dc-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f86dc-120">Перемещение пользователя с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="f86dc-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="f86dc-121">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="f86dc-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f86dc-122">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f86dc-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="f86dc-123">После этого в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f86dc-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="f86dc-124">Идентификатор **RegistrarPool** теперь указывает на Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f86dc-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f86dc-125">Наличие это удостоверение подтверждает, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="f86dc-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f86dc-126">Для сведений о командлет **Get-CsUser** выполните следующую команду: **Get-Help Get-CsUser-подробные**</span><span class="sxs-lookup"><span data-stu-id="f86dc-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

