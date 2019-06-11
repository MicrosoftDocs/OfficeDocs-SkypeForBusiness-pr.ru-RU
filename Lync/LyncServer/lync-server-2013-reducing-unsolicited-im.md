---
title: 'Lync Server 2013: уменьшение количества нежелательных мгновенных сообщений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="604c8-102">Уменьшение количества нежелательных мгновенных сообщений для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604c8-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="604c8-103">_**Тема последнего изменения:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="604c8-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="604c8-104">Интеллектуальный фильтр для обмена мгновенными сообщениями помогает защитить развертывание Microsoft Lync Server 2013 от наиболее распространенных вирусов с минимальным снижением качества взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="604c8-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="604c8-105">Интеллектуальный фильтр мгновенных сообщений предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="604c8-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="604c8-106">Улучшенная фильтрация URL-адресов</span><span class="sxs-lookup"><span data-stu-id="604c8-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="604c8-107">Улучшенная фильтрация передачи файлов</span><span class="sxs-lookup"><span data-stu-id="604c8-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="604c8-108">Используйте интеллектуальный фильтр мгновенных сообщений для настройки фильтров, чтобы блокировать непредусмотренные или потенциально опасные мгновенные сообщения от неизвестных конечных точек за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="604c8-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="604c8-109">Вы можете настроить фильтры, указав условия, которые будут использоваться для определения того, что следует блокировать (например, мгновенные сообщения, содержащие гиперссылки и файлы с определенными расширениями).</span><span class="sxs-lookup"><span data-stu-id="604c8-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="604c8-110">Перед развертыванием приложения для фильтрации сообщений в чате вы должны понять, как применяются параметры фильтрации, когда сообщения пересылаются с одного сервера Lync Server 2013 на другой.</span><span class="sxs-lookup"><span data-stu-id="604c8-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="604c8-111">Способ применения этих параметров фильтрации одинаков, независимо от того, находятся ли серверы в одной организации или на разных организационных границах.</span><span class="sxs-lookup"><span data-stu-id="604c8-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="604c8-112">Это соответствие распространяется на то, как настроенные уведомления и тексты предупреждаются в сообщениях и отправляются между серверами.</span><span class="sxs-lookup"><span data-stu-id="604c8-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="604c8-113">Рекомендуемым вариантом фильтрации является разрешение мгновенных сообщений с гиперссылками, но для отключения ссылки путем вставки знака подчеркивания перед ним требуется интеллектуальный фильтр сообщений.</span><span class="sxs-lookup"><span data-stu-id="604c8-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="604c8-114">Если выбрать этот параметр, у вас есть дополнительный параметр создания уведомления для пользователей, которые отображаются в начале каждого мгновенного сообщения, содержащего гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="604c8-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="604c8-115">Второй вариант фильтрации — разрешить мгновенные сообщения с неизмененными гиперссылками.</span><span class="sxs-lookup"><span data-stu-id="604c8-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="604c8-116">Если выбрать этот параметр, у вас есть дополнительный параметр (рекомендуется) для составления предупреждений для пользователей, которые вставляются в каждое сообщение.</span><span class="sxs-lookup"><span data-stu-id="604c8-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="604c8-117">Третьим вариантом является блокировка всех мгновенных сообщений, содержащих гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="604c8-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="604c8-118">Если выбрать этот параметр, сервер отправляет предупреждение пользователю.</span><span class="sxs-lookup"><span data-stu-id="604c8-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="604c8-119">Это предупреждение необходимо написать.</span><span class="sxs-lookup"><span data-stu-id="604c8-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

