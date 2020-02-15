---
title: 'Lync Server 2013: экспорт файла конфигурации маршрута голосовых вызовов'
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
ms.openlocfilehash: 4128dc1e2d3a300d0305336d87f36f0d6a06a055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="52d95-102">Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d95-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d95-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="52d95-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="52d95-104">Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="52d95-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="52d95-105">При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="52d95-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="52d95-106">Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.</span><span class="sxs-lookup"><span data-stu-id="52d95-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="52d95-107">Если вы внесли какие-либо незафиксированные изменения параметров на любую страницу в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="52d95-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="52d95-108">Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов перед публикацией изменений.</span><span class="sxs-lookup"><span data-stu-id="52d95-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="52d95-109">Экспорт конфигурации маршрутизации голосовых данных</span><span class="sxs-lookup"><span data-stu-id="52d95-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="52d95-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="52d95-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="52d95-111">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="52d95-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="52d95-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52d95-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52d95-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52d95-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52d95-114">В левой панели навигации щелкните элемент **Маршрутизация голосовых данных**.</span><span class="sxs-lookup"><span data-stu-id="52d95-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="52d95-115">В меню **Действия** щелкните пункт **Экспорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="52d95-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="52d95-116">Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="52d95-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52d95-117">См. также</span><span class="sxs-lookup"><span data-stu-id="52d95-117">See Also</span></span>


[<span data-ttu-id="52d95-118">Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52d95-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

