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
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="992d7-102">Настройка базы данных местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="992d7-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="992d7-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="992d7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="992d7-p101">Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. Если не настроить эту базу данных и задать для параметра **Требуется местоположение** в политике местоположений значение **Да** или **Отказ**, пользователь получит запрос на ручной ввод местоположения.</span><span class="sxs-lookup"><span data-stu-id="992d7-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="992d7-106">Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="992d7-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="992d7-107">Заполните базу данных с сопоставлением сетевых элементов местоположениям.</span><span class="sxs-lookup"><span data-stu-id="992d7-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="992d7-108">Если вы используете шлюз с идентификационным номером расположения экстренной службы (ELIN), необходимо включить ELIN в поле \<CompanyName\> .</span><span class="sxs-lookup"><span data-stu-id="992d7-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="992d7-109">Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="992d7-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="992d7-110">Опубликуйте обновленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="992d7-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="992d7-111">Кроме того, можно определить дополнительную базу данных местоположений, которую можно использовать вместо базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="992d7-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="992d7-112">Дополнительные сведения: <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Настройка службы сведений о дополнительном местоположении в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="992d7-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="992d7-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="992d7-113">In This Section</span></span>

  - [<span data-ttu-id="992d7-114">Заполнение базы данных расположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="992d7-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="992d7-115">Проверка адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="992d7-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="992d7-116">Публикация базы данных местоположений из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="992d7-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

