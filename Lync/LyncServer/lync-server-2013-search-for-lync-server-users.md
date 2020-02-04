---
title: 'Lync Server 2013: Поиск пользователей Lync Server'
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
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="fbbb8-102">Поиск пользователей Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbbb8-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbbb8-103">_**Тема последнего изменения:** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="fbbb8-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="fbbb8-104">С помощью результатов поискового запроса можно настроить пользователей для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="fbbb8-105">Для поиска пользователей можно использовать отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности (SAM), адрес SIP или универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="fbbb8-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="fbbb8-106">Найти пользователей можно с помощью панели управления Lync Server или оснастки "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="fbbb8-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="fbbb8-107">Ниже описана процедура поиска пользователей с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbbb8-108">В среде с центральным топологией леса результаты поиска могут быть неточными при поиске пользователя по адресу электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="fbbb8-109">Вместо этого вы можете найти пользователей, указав префикс адреса SIP, например SIP: Name, добавьте фильтр поиска и выберите адрес SIP, содержащий частичный адрес электронной почты, или используйте командлет <STRONG>Get-CSUser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="fbbb8-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="fbbb8-110">Поиск одного или нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="fbbb8-110">To search for one or more users</span></span>

1.  <span data-ttu-id="fbbb8-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbbb8-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbbb8-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbbb8-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbbb8-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fbbb8-115">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, имя учетной записи SAM, адрес SIP или строку URI для учетной записи пользователя, которую вы хотите найти, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="fbbb8-116">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="fbbb8-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fbbb8-117">Нажмите кнопку со стрелкой "развернуть" в правом верхнем углу экрана над **результатами поиска**и выберите команду " **Добавить фильтр**".</span><span class="sxs-lookup"><span data-stu-id="fbbb8-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fbbb8-118">Введите свойство User, введя его или щелкнув стрелку в раскрывающемся списке для выбора свойства пользователя.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="fbbb8-119">В списке " **равно** " выберите **значение равно** или **не равно**.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="fbbb8-120">В текстовом поле введите условия поиска, которые нужно использовать, чтобы отфильтровать результаты поиска, и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="fbbb8-121">Результаты поиска выводятся в разделе **Результаты поиска**.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="fbbb8-122">Вы можете выбрать одного или всех пользователей из списка и выполнить задачи по настройке выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fbbb8-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbbb8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fbbb8-123">See Also</span></span>


[<span data-ttu-id="fbbb8-124">Просмотр сведений об учетных записях пользователей, включенных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbbb8-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="fbbb8-125">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbbb8-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

