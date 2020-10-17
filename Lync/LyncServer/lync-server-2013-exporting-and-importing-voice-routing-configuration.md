---
title: 'Lync Server 2013: экспорт и импорт конфигурации маршрутизации голосовой связи'
description: 'Lync Server 2013: экспорт и импорт конфигурации маршрутизации голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564775"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="0d295-103">Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d295-103">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d295-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0d295-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0d295-105">Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0d295-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="0d295-106">При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="0d295-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="0d295-107">Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.</span><span class="sxs-lookup"><span data-stu-id="0d295-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d295-108">Если вы внесли какие-либо незафиксированные изменения параметров на любой странице в группе <STRONG>маршрутизации голосовых</STRONG> вызовов, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="0d295-108">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="0d295-109">Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов панели управления Lync Server перед публикацией изменений.</span><span class="sxs-lookup"><span data-stu-id="0d295-109">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d295-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="0d295-110">In This Section</span></span>

  - [<span data-ttu-id="0d295-111">Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d295-111">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="0d295-112">Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d295-112">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0d295-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0d295-113">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

