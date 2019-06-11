---
title: 'Lync Server 2013: Удаление политики расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="c6ad6-102">Удаление политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6ad6-102">Deleting a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6ad6-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="c6ad6-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="c6ad6-104">В Lync Server 2013 вы можете использовать политику расположения для применения параметров, которые относятся к расширенным функциям 9-1-1 (E9-1-1), а также к параметрам расположения для пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="c6ad6-105">Политика расположения определяет, разрешено ли пользователю E9-1-1, и в каких случаях может происходить вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="c6ad6-106">Например, вы можете использовать политику расположения, чтобы определить, какой номер является вызовом экстренной помощи (например, 911 в США), следует ли автоматически уведомлять корпоративную безопасность, а также как перенаправлять этот звонок.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="c6ad6-107">Политики местоположений можно настроить в группе **Конфигурация сети** в Lync Server 2013 панели управления.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c6ad6-108">На панели управления Lync Server вы можете просматривать, создавать, изменять и удалять политики расположения.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="c6ad6-109">Используйте описанные ниже процедуры для удаления политики расположения.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-109">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="c6ad6-110">Дополнительные сведения о создании и изменении политик расположения можно найти [в разделе Создание и изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c6ad6-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="c6ad6-111">Удаление политики расположения</span><span class="sxs-lookup"><span data-stu-id="c6ad6-111">To delete a location policy</span></span>

1.  <span data-ttu-id="c6ad6-112">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c6ad6-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c6ad6-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c6ad6-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c6ad6-115">На панели навигации слева выберите пункт **Настройка сети** , а затем — **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="c6ad6-116">На странице " **Политика расположения** " выберите политику расположения, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-116">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6ad6-117">Вы можете удалить более одной политики расположения одновременно.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-117">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="c6ad6-118">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, выберите несколько политик.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-118">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="c6ad6-119">Кроме того, чтобы выбрать все политики, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c6ad6-119">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="c6ad6-120">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c6ad6-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-121">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c6ad6-122">Вы не можете удалить политику глобального расположения.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-122">You cannot delete the Global location policy.</span></span> <span data-ttu-id="c6ad6-123">При попытке удалить глобальную политику появится предупреждающее сообщение о том, что для политики будут восстановлены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c6ad6-123">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6ad6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ad6-124">See Also</span></span>


[<span data-ttu-id="c6ad6-125">Создание и изменение политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6ad6-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="c6ad6-126">Просмотр сведений о политике местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6ad6-126">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

