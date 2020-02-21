---
title: 'Lync Server 2013: Удаление политики расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc554d24bc93b81969832c9d8d2b034d071760bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="325f6-102">Удаление политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="325f6-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="325f6-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="325f6-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="325f6-104">В Lync Server 2013 вы можете использовать политику расположения для применения параметров, относящихся к расширенным функциям 9-1-1 (E9-1-1), а также к параметрам расположения для пользователей или контактов.</span><span class="sxs-lookup"><span data-stu-id="325f6-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="325f6-105">Политика расположения определяет, активирована ли для пользователя функция E9-1-1 и, если да, то в каком режиме выполняются экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="325f6-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="325f6-106">Например, можно использовать политику расположения, чтобы определить номер экстренного вызова (911 в США), а также должен ли автоматически оповещаться отдел корпоративной безопасности и как маршрутизировать вызов.</span><span class="sxs-lookup"><span data-stu-id="325f6-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="325f6-107">Политики расположения можно настроить из группы **конфигурации сети** в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="325f6-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="325f6-108">В панели управления Lync Server вы можете просматривать, создавать, изменять и удалять политики расположения.</span><span class="sxs-lookup"><span data-stu-id="325f6-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="325f6-109">Используйте следующие процедуры, чтобы удалить политику расположения.</span><span class="sxs-lookup"><span data-stu-id="325f6-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="325f6-110">Подробнее о создании или изменении политик расположения можно узнать [в статье Создание или изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="325f6-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="325f6-111">Удаление политики расположения</span><span class="sxs-lookup"><span data-stu-id="325f6-111">To delete a location policy</span></span>

1.  <span data-ttu-id="325f6-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="325f6-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="325f6-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="325f6-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="325f6-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="325f6-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="325f6-115">На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="325f6-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="325f6-116">На странице **Политика расположения** щелкните политику расположения, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="325f6-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="325f6-p104">За один раз вы можете удалить несколько политик расположения. Для этого нажмите клавишу CTRL и, удерживая ее, выберите несколько политик. Чтобы выбрать все политики, щелкните пункт <STRONG>Выбрать</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="325f6-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="325f6-120">В меню **Изменить** нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="325f6-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="325f6-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="325f6-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="325f6-p105">Вы не можете удалить глобальную политику расположения. Если попытаться удалить глобальную политику, отображается предупреждение, а для политики будут восстановлены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="325f6-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="325f6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="325f6-124">See Also</span></span>


[<span data-ttu-id="325f6-125">Создание или изменение политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="325f6-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="325f6-126">Просмотр сведений о политике расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="325f6-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

