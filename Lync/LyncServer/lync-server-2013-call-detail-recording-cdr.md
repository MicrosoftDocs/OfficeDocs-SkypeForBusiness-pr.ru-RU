---
title: 'Lync Server 2013: запись сведений о вызовах (CDR)'
description: 'Lync Server 2013: запись сведений о вызовах (CDR).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590f99fd0b8649ffb3c4df039488dc54a8f3b7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561795"
---
# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="efc95-103">Регистрация вызовов (CDR) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-103">Call detail recording (CDR) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efc95-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="efc95-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="efc95-105">Записи регистрации вызовов (CDR) и диагностическая информация об одноранговой активности, включая мгновенные сообщения, VoIP-вызовы, общий доступ к приложениям, передачу файлов и собрания.</span><span class="sxs-lookup"><span data-stu-id="efc95-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="efc95-106">Данные об использовании могут применяться для расчета окупаемости инвестиций, а данные диагностики — для устранения неполадок, связанных с одноранговой активностью и собраниями.</span><span class="sxs-lookup"><span data-stu-id="efc95-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="efc95-107">При установке Lync Server 2013 Вы также устанавливаете предварительно определенную коллекцию глобальных параметров конфигурации для CDR.</span><span class="sxs-lookup"><span data-stu-id="efc95-107">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="efc95-108">Используйте темы этого раздела для настройки регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="efc95-108">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efc95-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="efc95-109">In This Section</span></span>

  - [<span data-ttu-id="efc95-110">Просмотр сведений о конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-110">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="efc95-111">Включение регистрации вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-111">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="efc95-112">Создание или изменение коллекции параметров конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-112">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="efc95-113">Удаление существующей коллекции параметров конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-113">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="efc95-114">Ручное удаление баз данных регистрации вызовов и качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-114">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efc95-115">См. также</span><span class="sxs-lookup"><span data-stu-id="efc95-115">See Also</span></span>


[<span data-ttu-id="efc95-116">Настройка записи сведений о вызовах и параметров качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efc95-116">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

