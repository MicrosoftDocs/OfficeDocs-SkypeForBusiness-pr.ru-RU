---
title: 'Lync Server 2013: включение парковки вызовов для пользователей'
description: 'Lync Server 2013: включение парковки вызовов для пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f9ab23b9fa71943efafd588b8c57a2af781b08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561035"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="3dd35-103">Включение парковки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd35-103">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dd35-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="3dd35-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="3dd35-105">Пользователи не могут приостанавливать вызовы и получать приостановленные звонки до тех пор, пока они не будут включены в политику голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="3dd35-105">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3dd35-106">По умолчанию парковки вызовов отключен для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="3dd35-106">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="3dd35-107">Можно включить приостановку вызовов в глобальной области, на уровне сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="3dd35-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="3dd35-108">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="3dd35-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="3dd35-109">Если у вас есть несколько политик голосовой связи, ознакомьтесь со всеми политиками, чтобы включить приостановку вызовов, а не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="3dd35-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="3dd35-110">Использование панели управления Lync Server для включения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="3dd35-110">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="3dd35-111">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="3dd35-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dd35-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3dd35-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3dd35-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3dd35-114">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="3dd35-115">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-115">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="3dd35-116">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-116">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="3dd35-117">В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-117">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="3dd35-118">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-118">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="3dd35-119">Использование командлетов для включения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="3dd35-119">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="3dd35-120">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3dd35-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3dd35-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3dd35-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3dd35-122">Выполняем</span><span class="sxs-lookup"><span data-stu-id="3dd35-122">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="3dd35-123">Например, чтобы включить приостановку вызовов для глобальной политики голосовой связи по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="3dd35-123">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3dd35-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3dd35-124">See Also</span></span>


[<span data-ttu-id="3dd35-125">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd35-125">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

