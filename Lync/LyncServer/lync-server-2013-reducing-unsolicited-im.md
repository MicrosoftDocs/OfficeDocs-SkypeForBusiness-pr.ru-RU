---
title: 'Lync Server 2013: уменьшение количества нежелательных мгновенных сообщений'
description: 'Lync Server 2013: уменьшение количества нежелательных мгновенных сообщений.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 294c53a6b82b4dc345fbb9afcf9983d5bd35893a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559115"
---
# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="86dfb-103">Сокращение числа нежелательных мгновенных сообщений для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86dfb-103">Reducing unsolicited IM for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86dfb-104">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="86dfb-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="86dfb-105">Приложение интеллектуального фильтра мгновенных сообщений помогает защитить развертывание Microsoft Lync Server 2013 от наиболее распространенных вирусов с минимальным снижением качества взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="86dfb-105">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="86dfb-106">Интеллектуальный фильтр обмена мгновенными сообщениями предоставляет следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="86dfb-106">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="86dfb-107">Фильтрация расширенных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="86dfb-107">Enhanced URL filtering</span></span>

  - <span data-ttu-id="86dfb-108">Расширенная фильтрация передачи файлов</span><span class="sxs-lookup"><span data-stu-id="86dfb-108">Enhanced file transfer filtering</span></span>

<span data-ttu-id="86dfb-109">Используйте Intelligent IM Filter, чтобы настроить фильтры для блокировки потенциально вредоносных мгновенных сообщений от неизвестных конечных точек за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="86dfb-109">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="86dfb-110">Фильтры настраиваются путем определения критериев, которые необходимо использовать для определения того, что должно быть заблокировано, например мгновенные сообщения, содержащие гиперссылки и файлы с определенными расширениями.</span><span class="sxs-lookup"><span data-stu-id="86dfb-110">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="86dfb-111">Прежде чем развертывать интеллектуальное приложение для фильтрации сообщений IM, необходимо знать, как применяются параметры фильтрации при маршрутизации сообщений с одного сервера Lync Server 2013 на другой.</span><span class="sxs-lookup"><span data-stu-id="86dfb-111">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="86dfb-112">Параметры фильтрации применяются последовательно, независимо от расположения серверов, будь то пределы одной организации или обмен данными между несколькими организациями.</span><span class="sxs-lookup"><span data-stu-id="86dfb-112">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="86dfb-113">Такая согласованность применяется к тому способу, в котором сообщения и тексты предупреждений вставляются в сообщения и отправляются между серверами.</span><span class="sxs-lookup"><span data-stu-id="86dfb-113">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="86dfb-114">Рекомендуемый вариант фильтрации заключается в том, чтобы разрешить мгновенные сообщения с гиперссылками, но для отключения ссылки вставьте подчеркивание перед этой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="86dfb-114">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="86dfb-115">При выборе этого варианта у вас будет дополнительный параметр создания уведомления для пользователей, которые отображаются в начале каждого мгновенного сообщения, содержащего гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="86dfb-115">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="86dfb-116">Второй вариант фильтрации состоит в том, чтобы разрешить мгновенные сообщения с неизмененными гиперссылками.</span><span class="sxs-lookup"><span data-stu-id="86dfb-116">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="86dfb-117">При выборе этого параметра у вас будет дополнительный параметр (рекомендуется) для составления предупреждения для пользователей, которые вставляются в каждое сообщение.</span><span class="sxs-lookup"><span data-stu-id="86dfb-117">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="86dfb-118">Третий вариант заключается в блокировании всех мгновенных сообщений, содержащих гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="86dfb-118">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="86dfb-119">При выборе этого параметра сервер отправляет пользователю предупреждение.</span><span class="sxs-lookup"><span data-stu-id="86dfb-119">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="86dfb-120">Необходимо написать это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="86dfb-120">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

