---
title: Перемещение отдельного пользователя в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете переместить пользователя из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019. В приведенном ниже примере в столбце пула регистратора pool01.contoso.net — это пул устаревших данных, и все шесть этих пользователей подключены к этому пулу. Чтобы переместить пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и консоли управления Skype для бизнеса Server, выполните указанные ниже действия.
ms.openlocfilehash: cc8c657b5e8d9cea760472c80da28bad4cf21f2e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813307"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="36220-105">Перемещение отдельного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="36220-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="36220-106">Вы можете переместить пользователя из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="36220-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="36220-107">В приведенном ниже примере в столбце **пула регистратора** **pool01.contoso.NET** — это пул устаревших данных, и все шесть этих пользователей подключены к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="36220-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="36220-108">Чтобы переместить пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и консоли управления Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="36220-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="36220-109">Перемещение пользователя с помощью панели управления "Skype для бизнеса Server 2019"</span><span class="sxs-lookup"><span data-stu-id="36220-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="36220-110">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36220-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="36220-111">Откройте **Панель управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="36220-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="36220-112">Нажмите кнопку **Пользователи**, нажмите **Поиск**, а затем — **найти**.</span><span class="sxs-lookup"><span data-stu-id="36220-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="36220-113">Выберите пользователя, которого вы хотите переместить в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36220-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="36220-114">В данном примере мы будем перемещать пользователя Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="36220-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="36220-115">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="36220-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="36220-116">В раскрывающемся списке выберите пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36220-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="36220-117">Нажмите кнопку **действие**и выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="36220-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="36220-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="36220-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="36220-119">Убедитесь в том, что столбец **пула регистратора** для пользователя теперь содержит пул Skype для бизнеса Server 2019, указывающий на то, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="36220-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="36220-120">Перемещение пользователя с помощью управляющей оболочки Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="36220-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="36220-121">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36220-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="36220-122">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36220-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="36220-123">Затем в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="36220-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="36220-124">Идентификатор **регистрарпул** теперь указывает на пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36220-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="36220-125">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="36220-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="36220-126">Для получения подробных сведений о командлете **Get-CsUser** выполните следующие действия: **Get-Help Get-CsUser-Detailed**</span><span class="sxs-lookup"><span data-stu-id="36220-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

