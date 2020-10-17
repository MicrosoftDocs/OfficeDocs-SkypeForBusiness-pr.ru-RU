---
title: 'Lync Server 2013: Управление расположениями для поставщиков услуг магистрали SIP'
description: 'Lync Server 2013: Управление расположениями для поставщиков услуг магистрали SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062c55f6e8484121c91b28f4926e37f85a25c0a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545195"
---
# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="c2bf7-103">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2bf7-103">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2bf7-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c2bf7-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c2bf7-105">Чтобы настроить Lync Server для автоматического обнаружения клиентов в сети, необходимо либо заполнить базу данных службы сведений о расположениях с помощью сети карты географических соответствий и опубликовать расположения, либо создать ссылку на внешнюю базу данных, которая уже содержит соответствующие сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-105">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="c2bf7-106">В ходе этого процесса необходимо проверить работу с административными адресами в поставщике услуг E9 – 1 – 1.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="c2bf7-107">Дополнительные сведения: [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-107">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c2bf7-108">Добавьте в базу данных службы Location Information местоположение для аварийного реагирования (Emergency Response Location — ERL), которое состоит из почтового адреса и точного местоположения в здании.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="c2bf7-109">Поле **расположения** службы информационных данных о местонахождении, которое является определенным расположением в здании, имеет максимальную длину 20 символов (включая пробелы).</span><span class="sxs-lookup"><span data-stu-id="c2bf7-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="c2bf7-110">Учитывая это ограничение, в поле рекомендуется включить следующие данные:</span><span class="sxs-lookup"><span data-stu-id="c2bf7-110">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="c2bf7-p103">Понятное имя, идентифицирующее расположение звонящего в аварийную службу, которое позволит агенту аварийной службы быстрее находить указанное расположение в момент прибытия по гражданскому адресу. Имя расположения может включать номер здания, номер этажа, обозначение корпусов, номер квартиры и т. д. Избегайте употребления сокращенный названий, известных только сотрудникам, что может привести к направлению аварийной службы по неправильному адресу.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="c2bf7-114">Идентификатор расположения, который позволяет пользователям быстро оценить, правильно ли клиент Lync выбрал расположение.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-114">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="c2bf7-115">Клиент Lync автоматически объединяет и отображает обнаруженные поля **Location** и **City** в заголовке.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-115">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="c2bf7-116">Рекомендуется добавить почтовый адрес здания в каждый идентификатор расположения (например, "1-й этаж \<street number\> ").</span><span class="sxs-lookup"><span data-stu-id="c2bf7-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="c2bf7-117">Без почтового адреса общий идентификатор расположения, такой как "1-ый этаж", может применяться к любому зданию в городе.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="c2bf7-118">Если расположение определяется приблизительно, например по точке беспроводного доступа, можно добавить слово Near (например, "примерно 1-ый этаж 1234").</span><span class="sxs-lookup"><span data-stu-id="c2bf7-118">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2bf7-119">Расположения, добавленные в базу данных центрального расположения, недоступны клиенту до тех пор, пока они не будут опубликованы с помощью команды командной консоли Lync Server и реплицируются в локальные хранилища пула.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-119">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="c2bf7-120">Для получения дополнительных сведений см. <A href="lync-server-2013-publish-the-location-database.md">Публикация базы данных местоположений из Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-120">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c2bf7-121">В следующих разделах рассматриваются аспекты, которые следует учитывать при заполнении и обслуживании базы данных расположения.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="c2bf7-122">Заполнение базы данных расположений</span><span class="sxs-lookup"><span data-stu-id="c2bf7-122">Populating the Location Database</span></span>

<span data-ttu-id="c2bf7-123">Ниже приведены вопросы, которые помогут определить порядок заполнения базы данных.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-123">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="c2bf7-124">**Какой процесс будет использоваться для заполнения базы данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="c2bf7-124">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="c2bf7-p106">Где хранятся данные и какие действия необходимо предпринять, чтобы преобразовать данные в формат, требуемый базой данных местоположений? Будут ли местоположения добавляться по-отдельности или массово с использованием CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="c2bf7-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c2bf7-127">**Используется ли сторонняя база данных, которая уже содержит сопоставление местоположений?**</span><span class="sxs-lookup"><span data-stu-id="c2bf7-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="c2bf7-128">С помощью параметра службы дополнительных сведений о расположении Lync Server для подключения к сторонней базе данных можно группировать и управлять ими с помощью автономной платформы.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-128">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="c2bf7-129">Преимущество этого подхода заключается в том, что дополнительно к связыванию местоположений с идентификаторами сети можно связать местоположения с пользователями.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="c2bf7-130">Это означает, что служба сведений о местоположении может вернуть несколько адресов, исходящих из дополнительной службы сведений о расположении, в клиент Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="c2bf7-131">Пользователь затем может выбрать наиболее подходящее местоположение.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-131">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="c2bf7-132">Для интеграции со службой сведений о местонахождении третья база данных должна соответствовать схеме запроса и ответа расположения Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="c2bf7-133">Для получения дополнительных сведений обратитесь к разделу " \[ MS-E911WS \] : веб-служба для протокола поддержки E911" в <https://go.microsoft.com/fwlink/p/?linkid=213819> .</span><span class="sxs-lookup"><span data-stu-id="c2bf7-133">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="c2bf7-134">Дополнительные сведения о развертывании дополнительной службы сведений о расположении можно узнать [в статье Настройка дополнительной службы сведений о местоположении в Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c2bf7-135">Сведения о заполнении базы данных местоположений приведены в статье [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-135">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="c2bf7-136">Обслуживание базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="c2bf7-136">Maintaining the Location Database</span></span>

<span data-ttu-id="c2bf7-p109">После заполнения базы данных необходимо разработать стратегию обновления базы данных по мере внесения изменений в конфигурацию сети. Ниже приведены вопросы, которые помогут определить порядок обслуживания базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="c2bf7-139">**Как будет обновляться база данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="c2bf7-139">**How will you update the location database?**</span></span>  
    <span data-ttu-id="c2bf7-p110">Есть несколько сценариев, которые требуют обновления базы данных расположений, включая добавление протоколов WAP, изменение разводки в офисе (в связи с разными назначениями коммутаторов) и расширение подсети. Будет ли выполняться прямое обновление каждого отдельного расположения или массовое обновление всех расположений с помощью CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="c2bf7-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="c2bf7-142">**Будет ли использоваться для сопоставления MAC-адресов клиентов Lync с портами и идентификаторами коммутаторов приложение SNMP?**</span><span class="sxs-lookup"><span data-stu-id="c2bf7-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="c2bf7-143">При использовании приложения SNMP потребуется разработать ручную процедуру, которая позволит поддерживать согласованность данных о портах и корпусах коммутаторов между приложением SNMP и базой данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="c2bf7-144">Если приложение SNMP возвращает IP-адрес или идентификатор порта, не включенный в базу данных, информационная служба расположения не сможет вернуть клиентскую папку.</span><span class="sxs-lookup"><span data-stu-id="c2bf7-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

