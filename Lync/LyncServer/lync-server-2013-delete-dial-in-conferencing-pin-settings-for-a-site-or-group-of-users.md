---
title: Удаление параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей
description: Удаление параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a40168780d5ac5f37ceb33dfaacd25b492d6307a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564255"
---
# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="63b7b-103">Удаление параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63b7b-103">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b7b-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="63b7b-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="63b7b-105">Выполните следующие действия, чтобы удалить политику ПИН-кодов на уровне пользователя или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="63b7b-105">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="63b7b-106">Глобальную политику ПИН-кодов удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="63b7b-106">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="63b7b-107">Удаление политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="63b7b-107">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="63b7b-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63b7b-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="63b7b-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63b7b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63b7b-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63b7b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63b7b-111">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="63b7b-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="63b7b-112">На странице **политика ПИН-кодов** в поле Поиск введите полностью или частично имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="63b7b-112">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="63b7b-113">В списке политик выберите необходимую политику, щелкните **Правка** и затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="63b7b-113">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="63b7b-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="63b7b-114">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

