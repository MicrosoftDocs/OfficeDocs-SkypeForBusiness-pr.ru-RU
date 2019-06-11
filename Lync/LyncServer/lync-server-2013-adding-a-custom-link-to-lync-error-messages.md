---
title: 'Lync Server 2013: добавление настраиваемой ссылки в сообщения об ошибках Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="aac7d-102">Добавление настраиваемой ссылки в сообщения об ошибках Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aac7d-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aac7d-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="aac7d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="aac7d-104">Настройка сообщений об ошибках Lync 2013 путем добавления ссылки на сведения о поиске и устранении неполадок в службе поддержки.</span><span class="sxs-lookup"><span data-stu-id="aac7d-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="aac7d-105">Для этого используйте командлеты командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром кустомлинкинеррормессажес.</span><span class="sxs-lookup"><span data-stu-id="aac7d-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="aac7d-106">Текст настраиваемой ссылки: "щелкните здесь, чтобы найти разделы поддержки от администратора", и его нельзя настроить.</span><span class="sxs-lookup"><span data-stu-id="aac7d-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="aac7d-107">Например, следующая команда приводит к появлению настраиваемой ссылки в области сносок каждого сообщения об ошибке Lync 2013 и задает для конечной ссылки значениеhttp://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="aac7d-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="aac7d-108">С помощью **Grant-CSClientPolicy** можно назначить пользователям новую политику.</span><span class="sxs-lookup"><span data-stu-id="aac7d-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="aac7d-109">Подробные сведения можно найти в разделе **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aac7d-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

