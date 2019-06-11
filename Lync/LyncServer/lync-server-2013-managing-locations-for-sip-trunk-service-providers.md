---
title: 'Lync Server 2013: Управление расположением для провайдеров услуг магистральной магистрали SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="c3f7d-102">Управление расположением для поставщиков услуг магистральной магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3f7d-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3f7d-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c3f7d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c3f7d-104">Чтобы настроить Lync Server для автоматического обнаружения клиентов в сети, необходимо либо заполнить базу данных службы сведений о расположении с помощью сети виремап и опубликовать расположения, либо создать ссылку на внешнюю базу данных, которая уже находится в нужном месте. сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="c3f7d-105">В ходе этого процесса вам нужно проверить, какие из них можно проверяются с помощью поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="c3f7d-106">Подробности можно найти [в разделе Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c3f7d-107">Добавьте в базу данных службы информирования о местонахождении местоположение для аварийного реагирования (ERL), которое состоит из почтового адреса и точного местоположения в здании.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="c3f7d-108">Поле **расположения** службы сведений о расположении, которое является конкретным расположением в здании, содержит не более 20 символов (включая пробелы).</span><span class="sxs-lookup"><span data-stu-id="c3f7d-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="c3f7d-109">Учитывая это ограничение, в поле рекомендуется включить следующие данные.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="c3f7d-p103">Понятное имя, идентифицирующее расположение звонящего в аварийную службу, которое позволит агенту аварийной службы быстрее находить указанное расположение в момент прибытия по физическому адресу. Имя расположения может включать номер здания, номер этажа, обозначение корпусов, номер квартиры и т. д. Избегайте употребления сокращенных названий, известных только сотрудникам, что может привести к направлению аварийной службы по неправильному адресу.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="c3f7d-113">Идентификатор места, с помощью которого пользователи смогут легко видеть, что клиент Lync берет на себя нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="c3f7d-114">Клиент Lync автоматически объединяет и отображает обнаруженные поля " **место** " и " **город** " в заголовке.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="c3f7d-115">Рекомендуется добавить почтовый адрес здания в каждый идентификатор местоположения (например, "номер \<\>улицы первого этажа").</span><span class="sxs-lookup"><span data-stu-id="c3f7d-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="c3f7d-116">Без почтового адреса общий идентификатор расположения, такой как "1‑й этаж" может применяться к любому зданию в городе.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="c3f7d-117">Если расположение определяется приблизительно, например по точке беспроводного доступа, можно добавить слово Near (например, "примерно 1-й этаж 1234").</span><span class="sxs-lookup"><span data-stu-id="c3f7d-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3f7d-118">Расположения, добавленные в центральную базу данных, недоступно для клиента, пока они не опубликованы с помощью команды командной консоли Lync Server и реплицируются в локальные магазины пула.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="c3f7d-119">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-the-location-database.md">Публикация базы данных местоположений из Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c3f7d-120">В следующих разделах рассматриваются аспекты, которые следует учитывать при заполнении и обслуживании базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="c3f7d-121">Заполнение базы данных расположений</span><span class="sxs-lookup"><span data-stu-id="c3f7d-121">Populating the Location Database</span></span>

<span data-ttu-id="c3f7d-122">Ниже приведены вопросы, которые помогут определить порядок заполнения базы данных.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="c3f7d-123">**Какой процесс будет использоваться для заполнения базы данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="c3f7d-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="c3f7d-p106">Где хранятся данные и какие действия необходимо выполнить, чтобы преобразовать данные в формат, требуемый базой данных расположений? Будут ли расположения добавляться по отдельности или массово, используя CSV-файл?</span><span class="sxs-lookup"><span data-stu-id="c3f7d-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c3f7d-126">**Используется ли сторонняя база данных, которая уже содержит сопоставление расположений?**</span><span class="sxs-lookup"><span data-stu-id="c3f7d-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="c3f7d-127">С помощью параметра службы дополнительных сведений о расположении Lync Server для подключения к базе данных третьих лиц вы можете группировать и управлять ими с помощью автономной платформы.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="c3f7d-128">Преимущество этого метода заключается в том, что он позволяет связывать расположения не только с идентификаторами сети, но и с пользователями.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="c3f7d-129">Это означает, что служба сведений о расположении может возвращать несколько адресов, исходящих из дополнительной службы сведений о расположении, в клиенте Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="c3f7d-130">Пользователь затем может выбрать наиболее подходящее расположение.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="c3f7d-131">Для интеграции со службой сведений о расположении база данных стороннего поставщика должна следовать схеме запроса на расположение на сервере Lync Server/ответа.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="c3f7d-132">Подробные сведения можно найти в\[ <http://go.microsoft.com/fwlink/p/?linkid=213819>разделе "MS\]-E911WS: веб-служба поддержки протоколов E911".</span><span class="sxs-lookup"><span data-stu-id="c3f7d-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="c3f7d-133">Дополнительные сведения о развертывании дополнительной службы сведений о расположении можно найти [в разделе Настройка дополнительной службы сведений о расположении в Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c3f7d-134">Сведения о заполнении базы данных местоположений содержатся в разделе [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="c3f7d-135">Обслуживание базы данных расположений</span><span class="sxs-lookup"><span data-stu-id="c3f7d-135">Maintaining the Location Database</span></span>

<span data-ttu-id="c3f7d-p109">После заполнения базы данных необходимо разработать стратегию обновления базы данных по мере внесения изменений в конфигурацию сети. Ниже приведены вопросы, которые помогут определить порядок обслуживания базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="c3f7d-138">**Как будет обновляться база данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="c3f7d-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="c3f7d-p110">Есть несколько сценариев, которые требуют обновления базы данных расположений, включая добавление протоколов WAP, изменение разводки в офисе (в связи с разными назначениями коммутаторов) и расширение подсети. Будет ли выполняться прямое обновление каждого отдельного расположения или массовое обновление всех расположений с помощью CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="c3f7d-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c3f7d-141">**Будет ли использоваться для сопоставления MAC-адресов клиентов Lync с портами и идентификаторами коммутаторов приложение SNMP?**</span><span class="sxs-lookup"><span data-stu-id="c3f7d-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="c3f7d-142">При использовании приложения SNMP потребуется разработать ручную процедуру, которая позволит поддерживать согласованность данных о портах и корпусах коммутаторов между приложением SNMP и базой данных расположений.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="c3f7d-143">Если приложение SNMP возвращает IP-адрес или идентификатор порта, не включенный в базу данных, Служба сведений о расположении не сможет возвращать данные о расположении клиенту.</span><span class="sxs-lookup"><span data-stu-id="c3f7d-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

