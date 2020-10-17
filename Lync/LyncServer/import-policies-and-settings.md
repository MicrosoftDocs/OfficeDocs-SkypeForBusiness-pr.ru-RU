---
title: Импорт политик и параметров
description: Импорт политик и параметров.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569035"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="14082-103">Импорт политик и параметров</span><span class="sxs-lookup"><span data-stu-id="14082-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14082-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14082-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14082-105">После объединения информации о топологии Office Communications Server 2007 R2 с помощью пилотного пула Lync Server 2013 необходимо запустить командлет командной консоли Lync Server 2013, чтобы перенести политики и параметры конфигурации Office Communications Server 2007 R2 в пилотный пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14082-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="14082-106">Командлет **Import-CsLegacyConfiguration** импортирует политики, маршруты голосовых вызовов, абонентские группы, URL-адреса веб-клиента Communicator и номера доступа по телефонной линии в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14082-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="14082-107">Перенос политик и параметров</span><span class="sxs-lookup"><span data-stu-id="14082-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="14082-108">На сервере переднего плана Lync Server 2013 запустите командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14082-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="14082-109">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14082-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="14082-110">После импорта политик используйте приведенную ниже процедуру, чтобы просмотреть импортированные политики в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14082-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="14082-111">Просмотр импортированных политик</span><span class="sxs-lookup"><span data-stu-id="14082-111">To view imported policies</span></span>

1.  <span data-ttu-id="14082-112">Откройте панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14082-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="14082-113">Выберите пункт **Маршрутизация голосовой связи** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="14082-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="14082-114">Выберите пункт **Конференц-связь** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="14082-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="14082-115">Выберите пункт **Федерация и внешний доступ** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="14082-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="14082-116">Выберите пункт **Мониторинг и архивация** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="14082-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

