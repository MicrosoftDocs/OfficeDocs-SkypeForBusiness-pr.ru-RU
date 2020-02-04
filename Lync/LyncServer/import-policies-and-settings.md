---
title: Импорт политик и параметров
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="4e92c-102">Импорт политик и параметров</span><span class="sxs-lookup"><span data-stu-id="4e92c-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e92c-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4e92c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4e92c-104">После того как вы объедините сведения о топологии Office Communications Server 2007 R2 с помощью проекта Lync Server 2013 для пилотного пула, необходимо запустить командлет командной консоли Lync Server 2013 для миграции политик и параметров конфигурации Office Communications Server 2007 R2 в состав пула Lync Server 2013 Pilot.</span><span class="sxs-lookup"><span data-stu-id="4e92c-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="4e92c-105">Командлет **Import-кслегациконфигуратион** импортирует политики, маршруты голосовой связи, абонентские группы, URL-адреса Communicator Web Access и номера доступа для телефонного подключения в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e92c-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="4e92c-106">Миграция политик и параметров</span><span class="sxs-lookup"><span data-stu-id="4e92c-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="4e92c-107">На сервере переднего плана Lync Server 2013 запустите командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4e92c-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4e92c-108">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4e92c-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="4e92c-109">После импорта политик воспользуйтесь приведенными ниже инструкциями, чтобы просмотреть импортированные политики на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e92c-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="4e92c-110">Просмотр импортированных политик</span><span class="sxs-lookup"><span data-stu-id="4e92c-110">To view imported policies</span></span>

1.  <span data-ttu-id="4e92c-111">Откройте панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e92c-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="4e92c-112">Нажмите кнопку **Маршрутизация голоса** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="4e92c-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="4e92c-113">Выберите **Конференц** -связь и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="4e92c-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="4e92c-114">Выберите пункт **Федерация и внешний доступ** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="4e92c-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="4e92c-115">Нажмите кнопку **мониторинг и архивация** и просмотрите импортированные политики.</span><span class="sxs-lookup"><span data-stu-id="4e92c-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

