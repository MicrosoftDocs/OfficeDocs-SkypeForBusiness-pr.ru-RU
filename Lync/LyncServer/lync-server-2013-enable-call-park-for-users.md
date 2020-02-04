---
title: 'Lync Server 2013: включение приостановки звонков для пользователей'
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
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="a6dfd-102">Включение приостановки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6dfd-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6dfd-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="a6dfd-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="a6dfd-104">Пользователи не могут приостановить звонки или получить припаркованные звонки, пока они не будут включены в политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6dfd-105">По умолчанию приостановление звонков для всех пользователей отключено.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="a6dfd-106">Вы можете включить приостановку звонков в глобальной области или в области действия сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="a6dfd-107">Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь – перед глобальным уровнем.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="a6dfd-108">Если у вас несколько политик голосовой связи, проверьте все политики, чтобы включить приостановку звонков, а не только глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="a6dfd-109">Использование панели управления Lync Server для поддержки приостановки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="a6dfd-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="a6dfd-110">Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="a6dfd-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6dfd-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a6dfd-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6dfd-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="a6dfd-114">Перейдите на вкладку **Политика голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="a6dfd-115">Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="a6dfd-116">В разделе **Функции звонков** установите флажок **Разрешить парковку вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="a6dfd-117">Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="a6dfd-118">Использование командлетов для поддержки приостановки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="a6dfd-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="a6dfd-119">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="a6dfd-120">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a6dfd-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a6dfd-121">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a6dfd-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="a6dfd-122">Например, чтобы включить приостановку звонков для глобальной политики голосовой связи по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="a6dfd-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6dfd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a6dfd-123">See Also</span></span>


[<span data-ttu-id="a6dfd-124">Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6dfd-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

