---
title: 'Lync Server 2013: Включение или отключение конференц-связи с телефонным подключением для собраний'
description: 'Lync Server 2013: Включение или отключение конференц-связи с телефонным подключением для собраний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3caa7b8cee14ca8471e7b7e42af7f7398e3b6c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552454"
---
# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="cc439-103">Включение или отключение конференц-связи с телефонным подключением для собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc439-103">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc439-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc439-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc439-105">Следующая процедура описывает, как разрешить пользователю присоединяться к собраниям по телефону</span><span class="sxs-lookup"><span data-stu-id="cc439-105">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="cc439-106">Включение или отключение конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="cc439-106">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="cc439-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cc439-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cc439-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc439-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cc439-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cc439-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cc439-110">В левой панели навигации щелкните **Конференция**, а затем выберите **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="cc439-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="cc439-111">В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="cc439-111">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cc439-p102">Чтобы разрешить пользователям присоединяться к собранием по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="cc439-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="cc439-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc439-114">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

