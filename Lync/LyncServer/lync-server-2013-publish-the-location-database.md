---
title: 'Lync Server 2013: публикация базы данных расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="07652-102">Публикация базы данных местоположений из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07652-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07652-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="07652-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="07652-104">Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.</span><span class="sxs-lookup"><span data-stu-id="07652-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="07652-105">Подробности можно найти в документации по оболочке управления Lync Server для следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="07652-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="07652-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="07652-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="07652-107">Если вы используете шлюзы ELIN, необходимо также загрузить номера ELIN в базу данных автоматического определения расположения (ALI) сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="07652-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="07652-108">Оператор ТСОП может потребовать использования определенного формата для записей ELIN.</span><span class="sxs-lookup"><span data-stu-id="07652-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="07652-109">Обратитесь к оператору ТСОП для получения более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="07652-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="07652-110">Вы можете экспортировать записи из базы данных службы сведений о расположении и отформатировать их в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="07652-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="07652-111">Публикация базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="07652-111">To publish the location database</span></span>

  - <span data-ttu-id="07652-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="07652-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="07652-113">Чтобы опубликовать базу данных местоположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="07652-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

