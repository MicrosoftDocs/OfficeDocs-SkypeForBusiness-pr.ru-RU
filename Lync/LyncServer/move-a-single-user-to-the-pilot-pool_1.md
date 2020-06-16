---
title: Перемещение одного пользователя в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 200e929cb7dff4006ffe776504220618e5e7b570
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="aad55-102">Перемещение одного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="aad55-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad55-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="aad55-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="aad55-104">Вы можете переместить пользователя из пула Office Communications Server 2007 R2 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aad55-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="aad55-105">В приведенном ниже примере в столбце пул регистратора **\<Office Communications Server\>** используется пул Office Communications Server 2007 R2, а все шесть этих пользователей подключены к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="aad55-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="aad55-106">Используйте следующие процедуры для перемещения пользователя в пул Lync Server 2013 с помощью панели управления Lync Server 2013 и командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aad55-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="aad55-107">![Поиск пользователей OCS в панели управления Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Поиск пользователей OCS в панели управления Lync Server")</span><span class="sxs-lookup"><span data-stu-id="aad55-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="aad55-108">Перемещение пользователя с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad55-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="aad55-109">Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="aad55-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="aad55-110">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aad55-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="aad55-111">Щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="aad55-111">Click **Users**.</span></span>

4.  <span data-ttu-id="aad55-112">На вкладке **Поиск пользователей** щелкните кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="aad55-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="aad55-113">Затем щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="aad55-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="aad55-114">Создайте фильтр, в котором для параметра **Пользователь Office Communications Server** установлено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="aad55-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="aad55-115">Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aad55-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="aad55-116">![Поиск пользователей OCS в панели управления Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Поиск пользователей OCS в панели управления Lync Server")</span><span class="sxs-lookup"><span data-stu-id="aad55-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="aad55-117">Выберите пользователя, которого нужно переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aad55-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="aad55-118">В данном примере мы перемещаем пользователя с именем Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="aad55-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="aad55-119">В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="aad55-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="aad55-120">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aad55-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="aad55-121">Щелкните **Действие** и выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="aad55-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="aad55-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aad55-122">Click **OK**.</span></span>
    
    <span data-ttu-id="aad55-123">![Настройка конечного пула в диалоговом окне "перемещение пользователей"](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Настройка конечного пула в диалоговом окне "перемещение пользователей"")</span><span class="sxs-lookup"><span data-stu-id="aad55-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="aad55-124">Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит пул Lync Server 2013, указывающий, что пользователь успешно перемещен</span><span class="sxs-lookup"><span data-stu-id="aad55-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="aad55-125">Перемещение пользователя с помощью командной консоли Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad55-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="aad55-126">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aad55-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aad55-127">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aad55-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="aad55-128">Затем в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aad55-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="aad55-129">Удостоверение **RegistrarPool** теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aad55-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="aad55-130">Наличие этого идентификатора подтверждает успешное перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="aad55-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="aad55-131">![Выходные данные командлета Get – CsUser с фильтром Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Выходные данные командлета Get – CsUser с фильтром Identity")</span><span class="sxs-lookup"><span data-stu-id="aad55-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aad55-132">Для получения сведений о командлете <STRONG>Get-CsUser</STRONG> выполните следующую команду: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="aad55-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

