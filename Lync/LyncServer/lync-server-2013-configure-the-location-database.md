---
title: 'Lync Server 2013: Настройка базы данных местоположений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="b0583-102">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0583-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0583-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="b0583-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="b0583-104">Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="b0583-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="b0583-105">Если вы не настраиваете базу данных местоположений и для **расположения, требуемого** в политике расположения, задано значение **Да** или **отказ**, пользователю будет предложено ввести расположение вручную.</span><span class="sxs-lookup"><span data-stu-id="b0583-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="b0583-106">Чтобы настроить базу данных местоположений, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b0583-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="b0583-107">Заполните базу данных с сопоставлением сетевых элементов местоположениям.</span><span class="sxs-lookup"><span data-stu-id="b0583-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="b0583-108">При использовании шлюза идентификационный номер места для экстренного реагирования (Елин) необходимо добавить Елин в поле \<CompanyName\> .</span><span class="sxs-lookup"><span data-stu-id="b0583-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="b0583-109">Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b0583-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="b0583-110">Опубликуйте обновленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="b0583-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0583-111">Кроме того, вы можете определить вспомогательную базу данных расположения, которую можно использовать при размещении базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="b0583-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="b0583-112">Подробности можно найти <A href="lync-server-2013-configure-a-secondary-location-information-service.md">в разделе Настройка дополнительной службы сведений о расположении в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b0583-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b0583-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="b0583-113">In This Section</span></span>

  - [<span data-ttu-id="b0583-114">Заполнение базы данных местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0583-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="b0583-115">Проверка адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0583-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="b0583-116">Публикация базы данных местоположений из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0583-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

