---
title: 'Lync Server 2013: включение парковки вызовов для пользователей'
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
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528786"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="9a572-102">Включение парковки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a572-102">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a572-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9a572-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9a572-104">Пользователи не могут приостанавливать вызовы и получать приостановленные звонки до тех пор, пока они не будут включены в политику голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="9a572-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a572-105">По умолчанию парковки вызовов отключен для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a572-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="9a572-106">Можно включить приостановку вызовов в глобальной области, на уровне сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a572-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9a572-107">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="9a572-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9a572-108">Если у вас есть несколько политик голосовой связи, ознакомьтесь со всеми политиками, чтобы включить приостановку вызовов, а не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="9a572-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9a572-109">Использование панели управления Lync Server для включения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a572-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="9a572-110">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="9a572-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="9a572-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a572-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a572-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9a572-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a572-113">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="9a572-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="9a572-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="9a572-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="9a572-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="9a572-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="9a572-116">В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="9a572-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="9a572-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9a572-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9a572-118">Использование командлетов для включения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a572-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="9a572-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9a572-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="9a572-120">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a572-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a572-121">Выполняем</span><span class="sxs-lookup"><span data-stu-id="9a572-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="9a572-122">Например, чтобы включить приостановку вызовов для глобальной политики голосовой связи по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="9a572-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a572-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9a572-123">See Also</span></span>


[<span data-ttu-id="9a572-124">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a572-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

