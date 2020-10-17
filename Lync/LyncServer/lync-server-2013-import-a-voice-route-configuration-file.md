---
title: 'Lync Server 2013: импорт файла конфигурации маршрута голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f9d13ee352ba344684deafe3d7a380beb7c8bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528106"
---
# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="4de28-102">Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de28-102">Import a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4de28-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4de28-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4de28-104">Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4de28-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="4de28-105">При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="4de28-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="4de28-106">Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.</span><span class="sxs-lookup"><span data-stu-id="4de28-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="4de28-107">Если вы внесли какие-либо незафиксированные изменения параметров на любую страницу в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="4de28-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="4de28-108">Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов перед публикацией изменений.</span><span class="sxs-lookup"><span data-stu-id="4de28-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="4de28-109">Импорт конфигурации маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="4de28-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="4de28-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4de28-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4de28-111">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4de28-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4de28-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4de28-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4de28-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4de28-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4de28-114">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="4de28-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="4de28-115">В меню **действия** выберите пункт **Импорт конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="4de28-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="4de28-116">Найдите файл конфигурации, который необходимо импортировать, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="4de28-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="4de28-117">Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="4de28-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4de28-118">При импорте файла конфигурации голосовой связи необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4de28-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4de28-119">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="4de28-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4de28-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4de28-120">See Also</span></span>


[<span data-ttu-id="4de28-121">Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de28-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="4de28-122">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de28-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

