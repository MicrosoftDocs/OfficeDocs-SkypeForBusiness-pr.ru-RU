---
title: 'Lync Server 2013: экспорт файла конфигурации маршрута голосовых вызовов'
description: 'Lync Server 2013: экспорт файла конфигурации маршрута голосовых вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564795"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="c2b5b-103">Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b5b-103">Export a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b5b-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c2b5b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c2b5b-105">Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="c2b5b-106">При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="c2b5b-107">Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="c2b5b-108">Если вы внесли какие-либо незафиксированные изменения параметров на любую страницу в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="c2b5b-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="c2b5b-109">Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов перед публикацией изменений.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="c2b5b-110">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="c2b5b-110">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="c2b5b-111">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c2b5b-112">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c2b5b-112">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c2b5b-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2b5b-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2b5b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2b5b-115">В левой панели навигации щелкните элемент **Маршрутизация голосовых данных**.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-115">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="c2b5b-116">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-116">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="c2b5b-117">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2b5b-117">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2b5b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c2b5b-118">See Also</span></span>


[<span data-ttu-id="c2b5b-119">Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b5b-119">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

