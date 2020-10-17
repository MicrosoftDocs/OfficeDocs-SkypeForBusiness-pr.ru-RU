---
title: 'Lync Server 2013: Управление расположениями для шлюзов ELIN'
description: 'Lync Server 2013: Управление расположениями для шлюзов ELIN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557485"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="20952-103">Управление расположениями для шлюзов ELIN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20952-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20952-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="20952-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="20952-105">Чтобы Lync Server автоматически предоставил расположения клиентам в сети, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="20952-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="20952-106">Заполните базу данных службы сведений о расположениях с помощью сети карты географических соответствий и включите в поле CompanyName идентификационные номера расположения для экстренной связи (Elin).</span><span class="sxs-lookup"><span data-stu-id="20952-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="20952-107">Опубликовать местоположения, чтобы они были доступны клиентам в сети.</span><span class="sxs-lookup"><span data-stu-id="20952-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="20952-108">Отправить номера ELIN в базу данных автоматического определения местоположения (ALI) поставщика PSTN.</span><span class="sxs-lookup"><span data-stu-id="20952-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="20952-109">Для получения дополнительных сведений о выполнении этих задач обратитесь к разделу [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20952-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20952-110">Расположения, добавленные в базу данных центрального расположения, недоступны клиенту до тех пор, пока они не будут опубликованы с помощью команды командной консоли Lync Server и реплицируются в локальные хранилища пула.</span><span class="sxs-lookup"><span data-stu-id="20952-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="20952-111">Для получения дополнительных сведений см. <A href="lync-server-2013-publish-the-location-database.md">Публикация базы данных местоположений из Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20952-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="20952-112">В данном разделе описываются вопросы, которые необходимо рассмотреть во время планирования обновления и поддержки базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="20952-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="20952-113">Планирование сведений о местоположении для экстренных служб</span><span class="sxs-lookup"><span data-stu-id="20952-113">Planning Emergency Locations</span></span>

<span data-ttu-id="20952-114">При использовании шлюзов ELIN вы заполняете базу данных службы сведений о местоположении на административный адрес, конкретное расположение в здании и по крайней мере один ELIN для каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="20952-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="20952-115">Во время этапа планирования рекомендуется решить вопрос о присвоении имен местоположений и определить способ назначения номеров ELIN.</span><span class="sxs-lookup"><span data-stu-id="20952-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="20952-116">Планирование имен местоположений</span><span class="sxs-lookup"><span data-stu-id="20952-116">Planning Location Names</span></span>

<span data-ttu-id="20952-117">Поле **расположения** службы информационных данных о местонахождении, которое содержит конкретное расположение в здании, имеет максимальную длину 20 символов (включая пробелы).</span><span class="sxs-lookup"><span data-stu-id="20952-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="20952-118">Учитывая это ограничение, в поле рекомендуется включить следующие данные.</span><span class="sxs-lookup"><span data-stu-id="20952-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="20952-p104">Понятное имя, идентифицирующее расположение звонящего в аварийную службу, которое позволит агентам аварийной службы быстрее находить указанное расположение в момент прибытия по адресу. Это имя расположения может включать номер здания, номер этажа, обозначение корпусов, номер комнаты и т. д. Избегайте употребления неявных сокращенных названий, известных только сотрудникам, что может привести к направлению аварийной службы по неправильному адресу.</span><span class="sxs-lookup"><span data-stu-id="20952-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="20952-122">Идентификатор расположения, который позволяет пользователям быстро оценить, правильно ли клиент Lync выбрал расположение.</span><span class="sxs-lookup"><span data-stu-id="20952-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="20952-123">Клиент Lync автоматически объединяет и отображает обнаруженные поля **Location** и **City** в заголовке.</span><span class="sxs-lookup"><span data-stu-id="20952-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="20952-124">Рекомендуется добавить почтовый адрес здания в каждый идентификатор расположения (например, "1-й этаж \<street number\> ").</span><span class="sxs-lookup"><span data-stu-id="20952-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="20952-125">Без почтового адреса общий идентификатор расположения, такой как "1-ый этаж", может применяться к любому зданию в городе.</span><span class="sxs-lookup"><span data-stu-id="20952-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="20952-126">Если расположение определяется приблизительно, например по точке беспроводного доступа, можно добавить слово  Near (например, "примерно 1-ый этаж 1234").</span><span class="sxs-lookup"><span data-stu-id="20952-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="20952-127">Планирование номеров ELIN</span><span class="sxs-lookup"><span data-stu-id="20952-127">Planning ELINs</span></span>

<span data-ttu-id="20952-p106">После того как вы определите, каким образом следует разделить строение на местоположения, необходимо решить, сколько номеров ELIN следует назначить каждому местоположению. Например, в здании с несколькими этажами или корпусами различным областям можно назначить разные аварийные зоны. Обычно каждый этаж в здании считается отдельным местоположением. Каждому местоположению затем назначается один или несколько номеров ELIN, которые используются в качестве номеров вызова во время экстренных звонков. Обратитесь к поставщику PSTN, чтобы получить телефонные номера, которые можно использовать для ELIN. В следующей таблице представлен пример местоположений для определенного почтового адреса.</span><span class="sxs-lookup"><span data-stu-id="20952-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="20952-134">Пример назначений местоположений и ELIN</span><span class="sxs-lookup"><span data-stu-id="20952-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20952-135">Область здания</span><span class="sxs-lookup"><span data-stu-id="20952-135">Building Area</span></span></th>
<th><span data-ttu-id="20952-136">Расположение</span><span class="sxs-lookup"><span data-stu-id="20952-136">Location</span></span></th>
<th><span data-ttu-id="20952-137">ELIN</span><span class="sxs-lookup"><span data-stu-id="20952-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20952-138">Первый этаж</span><span class="sxs-lookup"><span data-stu-id="20952-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="20952-139">1,1</span><span class="sxs-lookup"><span data-stu-id="20952-139">1</span></span></p></td>
<td><p><span data-ttu-id="20952-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="20952-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20952-141">Второй этаж</span><span class="sxs-lookup"><span data-stu-id="20952-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="20952-142">2</span><span class="sxs-lookup"><span data-stu-id="20952-142">2</span></span></p></td>
<td><p><span data-ttu-id="20952-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="20952-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20952-144">Третий этаж</span><span class="sxs-lookup"><span data-stu-id="20952-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="20952-145">4</span><span class="sxs-lookup"><span data-stu-id="20952-145">3</span></span></p></td>
<td><p><span data-ttu-id="20952-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="20952-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20952-147">Задаваемые местоположения должны удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="20952-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="20952-148">Соответствовать местным и общегосударственным правилам в отношении максимальной области для местоположения и числа местоположений на каждый почтовый адрес.</span><span class="sxs-lookup"><span data-stu-id="20952-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="20952-149">Быть достаточно конкретными, чтобы можно было легко определить местонахождение абонента, совершающего экстренный вызов.</span><span class="sxs-lookup"><span data-stu-id="20952-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="20952-150">Заполнение базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="20952-150">Populating the Location Database</span></span>

<span data-ttu-id="20952-151">Ниже приведены вопросы, которые помогут определить порядок заполнения базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="20952-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="20952-152">**Какой процесс будет использоваться для заполнения базы данных местоположений?**</span><span class="sxs-lookup"><span data-stu-id="20952-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="20952-p107">Где хранятся данные и какие действия необходимо предпринять, чтобы преобразовать данные в формат, требуемый базой данных местоположений? Будут ли местоположения добавляться по-отдельности или массово с использованием CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="20952-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="20952-155">**Используется ли сторонняя база данных, которая уже содержит сопоставление местоположений?**</span><span class="sxs-lookup"><span data-stu-id="20952-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="20952-156">С помощью параметра службы дополнительных сведений о расположении Lync Server для подключения к сторонней базе данных можно группировать и управлять ими с помощью автономной платформы.</span><span class="sxs-lookup"><span data-stu-id="20952-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="20952-157">Преимущество этого подхода заключается в том, что дополнительно к связыванию местоположений с идентификаторами сети можно связать местоположения с пользователями.</span><span class="sxs-lookup"><span data-stu-id="20952-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="20952-158">Это означает, что служба сведений о местоположении может вернуть несколько адресов, исходящих из дополнительной службы сведений о расположении, в клиент Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20952-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="20952-159">Пользователь затем может выбрать наиболее подходящее местоположение.</span><span class="sxs-lookup"><span data-stu-id="20952-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="20952-160">Для интеграции со службой сведений о местонахождении третья база данных должна соответствовать схеме запроса и ответа расположения Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20952-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="20952-161">Дополнительные сведения см <https://go.microsoft.com/fwlink/p/?linkid=213819> .</span><span class="sxs-lookup"><span data-stu-id="20952-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="20952-162">Дополнительные сведения о развертывании дополнительной службы сведений о расположении можно узнать [в статье Настройка дополнительной службы сведений о местоположении в Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20952-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="20952-163">Сведения о заполнении базы данных местоположений приведены в статье [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="20952-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="20952-164">Обслуживание базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="20952-164">Maintaining the Location Database</span></span>

<span data-ttu-id="20952-p110">После заполнения базы данных необходимо разработать стратегию обновления базы данных по мере внесения изменений в конфигурацию сети. Ниже приведены вопросы, которые помогут определить порядок обслуживания базы данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="20952-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="20952-167">**Как будет обновляться база данных местоположений?**</span><span class="sxs-lookup"><span data-stu-id="20952-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="20952-p111">Существует несколько сценариев, которые требуют обновления базы данных местоположений, включая добавление протоколов WAP, изменение разводки в офисе (в связи с разными назначениями коммутаторов) и расширение подсети. Будет ли выполняться прямое обновление каждого отдельного местоположения или массовое обновление всех местоположений с помощью CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="20952-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="20952-170">**Будет ли использоваться для сопоставления MAC-адресов клиентов Lync с портами и идентификаторами коммутаторов приложение SNMP?**</span><span class="sxs-lookup"><span data-stu-id="20952-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="20952-171">При использовании приложения SNMP потребуется разработать ручную процедуру, которая позволит поддерживать согласованность данных о портах и корпусах коммутаторов между приложением SNMP и базой данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="20952-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="20952-172">Если приложение SNMP возвращает IP-адрес или идентификатор порта, не включенный в базу данных, информационная служба расположения не сможет вернуть клиентскую папку.</span><span class="sxs-lookup"><span data-stu-id="20952-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

