---
title: 'Lync Server 2013: Поиск пользователей Lync Server'
description: 'Lync Server 2013: Поиск пользователей Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0c4860b7b89ad13b3a0003c5666a320172dad6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557085"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="abc34-103">Поиск пользователей Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc34-103">Search for Lync Server users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc34-104">_**Последнее изменение темы:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="abc34-104">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="abc34-105">Результаты поискового запроса можно использовать для настройки пользователей для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abc34-105">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="abc34-106">Пользователей можно искать по отображаемому имени, имени, фамилии, имени учетной записи диспетчера защищенных учетных записей (SAM), SIP-адресу или строке URI.</span><span class="sxs-lookup"><span data-stu-id="abc34-106">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="abc34-107">Пользователей можно искать с помощью панели управления Lync Server или оснастки "Пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="abc34-107">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="abc34-108">В следующей процедуре описывается, как использовать панель управления Lync Server для поиска пользователей.</span><span class="sxs-lookup"><span data-stu-id="abc34-108">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="abc34-109">При поиске пользователя по его адресу электронной почты в среде с топологией с центральным лесом результаты могут быть неточными.</span><span class="sxs-lookup"><span data-stu-id="abc34-109">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="abc34-110">Вместо этого вы можете выполнить поиск пользователей, указав префикс SIP-адреса, например, sip:имя, добавить фильтр поиска и выбрать SIP-адрес с частичным адресом электронной почты, а также воспользоваться командлетом <STRONG>Get-CSUser</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="abc34-110">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="abc34-111">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="abc34-111">To search for one or more users</span></span>

1.  <span data-ttu-id="abc34-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="abc34-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="abc34-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="abc34-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="abc34-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="abc34-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="abc34-115">В левой панели навигации щелкните элемент **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="abc34-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="abc34-116">В поле **Search users** (Поиск пользователей) полностью или частично введите отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности, SIP-адрес или URI искомой учетной записи пользователя Active Directory, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="abc34-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="abc34-117">(Необязательно) Укажите дополнительные условия поиска, чтобы уменьшить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="abc34-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="abc34-118">Нажмите кнопку со стрелкой развертывания в верхнем правом углу экрана над элементом **Search results** (Результаты поиска) и нажмите кнопку **Add Filter** (Добавить фильтр).</span><span class="sxs-lookup"><span data-stu-id="abc34-118">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="abc34-119">Укажите свойство пользователя, введя его вручную или щелкнув стрелку в раскрывающемся списке и выбрав свойство в этом списке.</span><span class="sxs-lookup"><span data-stu-id="abc34-119">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="abc34-120">В списке **Equal to** (Равно) щелкните элемент **Equal to** (Равно) или **Not equal to** (Не равно).</span><span class="sxs-lookup"><span data-stu-id="abc34-120">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="abc34-121">В текстовом поле введите требуемые условия поиска для фильтрации результатов, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="abc34-121">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="abc34-p105">Результаты поиска отображаются под элементом **Search Results** (Результаты поиска). Вы можете выбрать любых или всех пользователей в списке и выполнить для них задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="abc34-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abc34-124">См. также</span><span class="sxs-lookup"><span data-stu-id="abc34-124">See Also</span></span>


[<span data-ttu-id="abc34-125">Просмотр сведений об учетных записях пользователей, включенных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc34-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="abc34-126">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc34-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

