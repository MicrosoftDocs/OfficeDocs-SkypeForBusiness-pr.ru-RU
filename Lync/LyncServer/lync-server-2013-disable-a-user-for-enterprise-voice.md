---
title: 'Lync Server 2013: отключение пользователя для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdcc6f69280357730e34f987f3c197db6950c285
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f77b5-102">Отключение пользователя для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77b5-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f77b5-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f77b5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f77b5-104">Используйте следующую процедуру, чтобы отключить корпоративную голосовую связь для учетной записи пользователя, для которой включена Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f77b5-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f77b5-105">Отключение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f77b5-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="f77b5-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f77b5-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f77b5-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f77b5-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f77b5-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f77b5-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f77b5-109">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f77b5-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f77b5-110">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="f77b5-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="f77b5-111">В таблице щелкните учетную запись пользователя, для которой необходимо включить поддержку корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f77b5-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="f77b5-112">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="f77b5-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="f77b5-113">На странице **Изменение пользователя Lync Server** в разделе **Телефония** щелкните любой параметр, кроме **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="f77b5-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f77b5-114">Чтобы запретить пользователю совершать аудио-и видеовызовы с помощью Lync, в разделе <STRONG>телефония</STRONG>нажмите кнопку <STRONG>аудио/видео отключена</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f77b5-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="f77b5-115">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f77b5-115">Click **Commit**.</span></span>

<span data-ttu-id="f77b5-116">Теперь пользователь не может использовать функцию корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f77b5-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f77b5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f77b5-117">See Also</span></span>


[<span data-ttu-id="f77b5-118">Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77b5-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="f77b5-119">Управление корпоративной голосовой связью для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f77b5-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="f77b5-120">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="f77b5-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

