---
title: 'Lync Server 2013: экспорт и импорт конфигурации маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb02759cb4fa7cf9c979ef06b594f78a6b253c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="3d5e0-102">Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d5e0-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d5e0-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d5e0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d5e0-104">Если вы хотите сохранить конфигурацию голосовой связи, не публикуя ее, выполните указанные ниже действия, чтобы использовать команды экспорта и импорта на панели управления Lync Server, чтобы сохранить и извлечь снимок конфигурации голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3d5e0-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="3d5e0-105">При импорте файла конфигурации голосовой маршрутизации (. вкфг) изменения, внесенные в конфигурацию голосовой маршрутизации на сервере, будут указывать на то, что в группе " **Маршрутизация** голосовых сообщений" на панели управления Lync Server есть незафиксированные изменения маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3d5e0-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="3d5e0-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span><span class="sxs-lookup"><span data-stu-id="3d5e0-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d5e0-107">Если вы внесли какие-либо незафиксированные изменения параметров на любой странице в группе " <STRONG>Маршрутизация голосовой связи</STRONG> ", изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг).</span><span class="sxs-lookup"><span data-stu-id="3d5e0-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="3d5e0-108">Это позволит вам вносить изменения в конфигурацию голосовой маршрутизации во время нескольких сеансов панели управления Lync Server, прежде чем публиковать изменения.</span><span class="sxs-lookup"><span data-stu-id="3d5e0-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3d5e0-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="3d5e0-109">In This Section</span></span>

  - [<span data-ttu-id="3d5e0-110">Экспорт файла конфигурации голосового маршрута в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d5e0-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="3d5e0-111">Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d5e0-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3d5e0-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3d5e0-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

