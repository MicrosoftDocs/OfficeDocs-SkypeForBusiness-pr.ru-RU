---
title: Перемещение одного пользователя в пилотный пул
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
description: Вы можете переместить пользователя из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019. В приведенном ниже примере в столбце пул регистратора pool01.contoso.net является устаревшим пулом, а все шесть этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и командной консоли Skype для бизнеса Server.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752511"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="f5f69-105">Перемещение одного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="f5f69-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="f5f69-106">Вы можете переместить пользователя из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5f69-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="f5f69-107">В приведенном ниже примере в столбце **пул регистратора** **pool01.contoso.NET** является устаревшим пулом, а все шесть этих пользователей подключены к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="f5f69-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="f5f69-108">Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f5f69-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f5f69-109">Перемещение пользователя с помощью панели управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="f5f69-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="f5f69-110">Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f5f69-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f5f69-111">Откройте **Панель управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="f5f69-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="f5f69-112">Нажмите кнопку **Пользователи**, выберите **Поиск**, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="f5f69-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="f5f69-113">Выберите пользователя, которого нужно переместить в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5f69-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f5f69-114">В данном примере мы перемещаем пользователя с именем Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="f5f69-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="f5f69-115">В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="f5f69-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="f5f69-116">В раскрывающемся списке выберите пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5f69-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="f5f69-117">В меню **действие**выберите команду **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="f5f69-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="f5f69-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5f69-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="f5f69-119">Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит пул Skype для бизнеса Server 2019, который указывает на успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5f69-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="f5f69-120">Перемещение пользователя с помощью командной консоли Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="f5f69-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="f5f69-121">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f5f69-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f5f69-122">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5f69-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="f5f69-123">Затем в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f5f69-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="f5f69-124">Удостоверение **RegistrarPool** теперь указывает на пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5f69-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f5f69-125">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="f5f69-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f5f69-126">Для получения сведений о командлете **Get – CsUser** выполните команду: **Get – Help Get – CsUser — Detailed**</span><span class="sxs-lookup"><span data-stu-id="f5f69-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

