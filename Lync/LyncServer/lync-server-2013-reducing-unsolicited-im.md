---
title: 'Lync Server 2013: уменьшение количества нежелательных мгновенных сообщений'
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
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a><span data-ttu-id="4d33d-102">Сокращение числа нежелательных мгновенных сообщений для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d33d-102">Reducing unsolicited IM for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d33d-103">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="4d33d-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="4d33d-104">Приложение интеллектуального фильтра мгновенных сообщений помогает защитить развертывание Microsoft Lync Server 2013 от наиболее распространенных вирусов с минимальным снижением качества взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="4d33d-104">The Intelligent IM Filter application helps protect your Microsoft Lync Server 2013 deployment against the most common viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="4d33d-105">Интеллектуальный фильтр обмена мгновенными сообщениями предоставляет следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="4d33d-105">The Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="4d33d-106">Фильтрация расширенных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="4d33d-106">Enhanced URL filtering</span></span>

  - <span data-ttu-id="4d33d-107">Расширенная фильтрация передачи файлов</span><span class="sxs-lookup"><span data-stu-id="4d33d-107">Enhanced file transfer filtering</span></span>

<span data-ttu-id="4d33d-108">Используйте Intelligent IM Filter, чтобы настроить фильтры для блокировки потенциально вредоносных мгновенных сообщений от неизвестных конечных точек за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="4d33d-108">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="4d33d-109">Фильтры настраиваются путем определения критериев, которые необходимо использовать для определения того, что должно быть заблокировано, например мгновенные сообщения, содержащие гиперссылки и файлы с определенными расширениями.</span><span class="sxs-lookup"><span data-stu-id="4d33d-109">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks and files with specific extensions.</span></span>

<span data-ttu-id="4d33d-110">Прежде чем развертывать интеллектуальное приложение для фильтрации сообщений IM, необходимо знать, как применяются параметры фильтрации при маршрутизации сообщений с одного сервера Lync Server 2013 на другой.</span><span class="sxs-lookup"><span data-stu-id="4d33d-110">Before you deploy the Intelligent IM Message Filter application, you should understand how filtering options are applied when messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="4d33d-111">Параметры фильтрации применяются последовательно, независимо от расположения серверов, будь то пределы одной организации или обмен данными между несколькими организациями.</span><span class="sxs-lookup"><span data-stu-id="4d33d-111">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="4d33d-112">Такая согласованность применяется к тому способу, в котором сообщения и тексты предупреждений вставляются в сообщения и отправляются между серверами.</span><span class="sxs-lookup"><span data-stu-id="4d33d-112">This consistency applies to the way that the customized notice, and warning texts are inserted into messages and sent across servers.</span></span>

<span data-ttu-id="4d33d-113">Рекомендуемый вариант фильтрации заключается в том, чтобы разрешить мгновенные сообщения с гиперссылками, но для отключения ссылки вставьте подчеркивание перед этой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="4d33d-113">The recommended filtering option is to allow instant messages with hyperlinks but require the Intelligent IM Filter to disable the link by inserting an underscore before it.</span></span> <span data-ttu-id="4d33d-114">При выборе этого варианта у вас будет дополнительный параметр создания уведомления для пользователей, которые отображаются в начале каждого мгновенного сообщения, содержащего гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="4d33d-114">If you choose this option, you have the additional option of composing a notice to users that appears at the beginning of each instant message that contains a hyperlink.</span></span>

<span data-ttu-id="4d33d-115">Второй вариант фильтрации состоит в том, чтобы разрешить мгновенные сообщения с неизмененными гиперссылками.</span><span class="sxs-lookup"><span data-stu-id="4d33d-115">A second filtering option is to allow instant messages with unmodified hyperlinks.</span></span> <span data-ttu-id="4d33d-116">При выборе этого параметра у вас будет дополнительный параметр (рекомендуется) для составления предупреждения для пользователей, которые вставляются в каждое сообщение.</span><span class="sxs-lookup"><span data-stu-id="4d33d-116">If you choose this option, you have the additional option (recommended) of composing a warning to users that is inserted in each message.</span></span>

<span data-ttu-id="4d33d-117">Третий вариант заключается в блокировании всех мгновенных сообщений, содержащих гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="4d33d-117">A third option is to block all instant messages that contain hyperlinks.</span></span> <span data-ttu-id="4d33d-118">При выборе этого параметра сервер отправляет пользователю предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d33d-118">If you choose this option, the server sends a warning to the user.</span></span> <span data-ttu-id="4d33d-119">Необходимо написать это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d33d-119">You must write this warning.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

