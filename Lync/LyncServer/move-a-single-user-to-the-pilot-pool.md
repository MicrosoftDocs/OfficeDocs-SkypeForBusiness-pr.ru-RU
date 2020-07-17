---
title: Перемещение одного пользователя в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f3bd233f610d340c1854cf18337183e5f988426
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="98aa6-102">Перемещение одного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="98aa6-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98aa6-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="98aa6-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="98aa6-104">Вы можете переместить пользователя из пула Lync Server 2010 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98aa6-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="98aa6-105">В приведенном ниже примере в столбце пул регистратора **pool01.contoso.NET** — пул Lync Server 2010, а все шесть этих пользователей подключены к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="98aa6-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="98aa6-106">Используйте следующие процедуры для перемещения пользователя в пул Lync Server 2013 с помощью панели управления Lync Server 2013 и командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98aa6-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="98aa6-107">Перемещение пользователя с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98aa6-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="98aa6-108">**Список пользователей в панели управления Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="98aa6-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="98aa6-109">![Панель управления Lync Server, диалоговое окно перемещения пользователя](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Панель управления Lync Server, диалоговое окно перемещения пользователя")</span><span class="sxs-lookup"><span data-stu-id="98aa6-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="98aa6-110">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="98aa6-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="98aa6-111">Откройте **Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98aa6-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="98aa6-112">Щелкните **Пользователи**, затем выберите поиск и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="98aa6-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="98aa6-113">Выберите пользователя, которого нужно переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98aa6-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="98aa6-114">В данном примере мы перемещаем пользователя с именем Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="98aa6-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="98aa6-115">В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="98aa6-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="98aa6-116">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98aa6-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="98aa6-117">Щелкните **Действие** и выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="98aa6-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="98aa6-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="98aa6-118">Click **OK**.</span></span>
    
    <span data-ttu-id="98aa6-119">![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")</span><span class="sxs-lookup"><span data-stu-id="98aa6-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="98aa6-120">Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит пул Lync Server 2013, указывающий, что пользователь успешно перемещен.</span><span class="sxs-lookup"><span data-stu-id="98aa6-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="98aa6-121">Перемещение пользователя с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98aa6-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="98aa6-122">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98aa6-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="98aa6-123">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="98aa6-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="98aa6-124">Затем в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="98aa6-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="98aa6-125">Удостоверение **RegistrarPool** теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98aa6-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="98aa6-126">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="98aa6-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="98aa6-127">![Выходные данные командлета Get – CsUser с фильтром Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Выходные данные командлета Get – CsUser с фильтром Identity")</span><span class="sxs-lookup"><span data-stu-id="98aa6-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98aa6-128">Для получения сведений о командлете <STRONG>Get-CsUser</STRONG> выполните следующую команду: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="98aa6-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

