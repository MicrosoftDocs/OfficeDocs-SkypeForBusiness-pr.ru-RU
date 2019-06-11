---
title: Перемещение отдельного пользователя в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="21776-102">Перемещение отдельного пользователя в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="21776-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21776-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="21776-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="21776-104">Вы можете переместить пользователя из пула Office Communications Server 2007 R2 на сервер Lync Server 2013 для пилотного пула с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21776-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="21776-105">В приведенном ниже примере в столбце пула регистратора \*\* \<Office Communications Server\> \*\* является пулом Office Communications Server 2007 R2, и все шесть из этих пользователей подключены к этому пулу.</span><span class="sxs-lookup"><span data-stu-id="21776-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="21776-106">Используйте описанные ниже процедуры для перемещения пользователя в пул Lync Server 2013 с помощью панели управления Lync Server 2013 и командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="21776-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="21776-107">![Поиск пользователей OCS на панели управления Lync Server] (images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Поиск пользователей OCS на панели управления Lync Server")</span><span class="sxs-lookup"><span data-stu-id="21776-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="21776-108">Перемещение пользователя с помощью панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21776-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="21776-109">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="21776-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="21776-110">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21776-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="21776-111">Нажмите кнопку **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="21776-111">Click **Users**.</span></span>

4.  <span data-ttu-id="21776-112">На вкладке **Поиск пользователя** нажмите кнопку **Поиск** .</span><span class="sxs-lookup"><span data-stu-id="21776-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="21776-113">Затем нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="21776-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="21776-114">Создайте фильтр, в котором **пользователь Office Communications Server** равен **true**.</span><span class="sxs-lookup"><span data-stu-id="21776-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="21776-115">Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="21776-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="21776-116">![Поиск пользователей OCS на панели управления Lync Server] (images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Поиск пользователей OCS на панели управления Lync Server")</span><span class="sxs-lookup"><span data-stu-id="21776-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="21776-117">Выберите пользователя, которого вы хотите переместить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21776-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="21776-118">В данном примере мы будем перемещать пользователя Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="21776-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="21776-119">В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="21776-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="21776-120">В раскрывающемся списке выберите пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21776-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="21776-121">Нажмите **Макрокоманда** и затем **Переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="21776-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="21776-122">Нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="21776-122">Click **OK**.</span></span>
    
    <span data-ttu-id="21776-123">![Настройка целевого пула в диалоговом окне "перемещение пользователей] " (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Настройка целевого пула в диалоговом окне \"перемещение пользователей") "</span><span class="sxs-lookup"><span data-stu-id="21776-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="21776-124">Убедитесь в том, что столбец **пула регистратора** для пользователя теперь содержит пул Lync Server 2013, указывающий на то, что пользователь успешно переместился</span><span class="sxs-lookup"><span data-stu-id="21776-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="21776-125">Перемещение пользователя с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21776-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="21776-126">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="21776-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="21776-127">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="21776-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="21776-128">Затем в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="21776-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="21776-129">Идентификатор **регистрарпул** теперь указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21776-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="21776-130">Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.</span><span class="sxs-lookup"><span data-stu-id="21776-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="21776-131">![Вывод командлета Get-CsUser с фильтром идентификаторов] (images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Вывод командлета Get-CsUser с фильтром идентификаторов")</span><span class="sxs-lookup"><span data-stu-id="21776-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21776-132">Для получения подробных сведений о командлете <STRONG>Get-CsUser</STRONG> выполните следующие действия: <STRONG>Get-Help Get-CsUser-Details</STRONG></span><span class="sxs-lookup"><span data-stu-id="21776-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

