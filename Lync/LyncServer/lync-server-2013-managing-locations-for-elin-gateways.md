---
title: 'Lync Server 2013: Управление расположением для шлюзов Елин'
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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="80182-102">Управление расположением для шлюзов Елин в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80182-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80182-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="80182-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="80182-104">Чтобы сервер Lync Server автоматически предоставил вам расположение для клиентов в сети, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="80182-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="80182-105">Заполните базу данных службы сведений о расположении с помощью сети виремап и включите в поле CompanyName идентификационные номера расположения для экстренного реагирования (Елинс).</span><span class="sxs-lookup"><span data-stu-id="80182-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="80182-106">Опубликовать расположения, чтобы они были доступны клиентам в сети.</span><span class="sxs-lookup"><span data-stu-id="80182-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="80182-107">Отправить номера ELIN в базу данных автоматического определения расположения (ALI) поставщика PSTN.</span><span class="sxs-lookup"><span data-stu-id="80182-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="80182-108">Подробнее о том, как выполнять эти задачи, можно найти [в статье Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="80182-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80182-109">Расположения, добавленные в центральную базу данных, недоступно для клиента, пока они не опубликованы с помощью команды командной консоли Lync Server и реплицируются в локальные магазины пула.</span><span class="sxs-lookup"><span data-stu-id="80182-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="80182-110">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-the-location-database.md">Публикация базы данных местоположений из Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="80182-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="80182-111">В данном разделе описываются вопросы, которые необходимо рассмотреть во время планирования обновления и поддержки базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="80182-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="80182-112">Планирование сведений о расположении для экстренных служб</span><span class="sxs-lookup"><span data-stu-id="80182-112">Planning Emergency Locations</span></span>

<span data-ttu-id="80182-113">При использовании Елин Gateways вы заполняете базу данных сведений о расположении на административный адрес, определенное расположение в здании и по крайней мере один Елин для каждого места.</span><span class="sxs-lookup"><span data-stu-id="80182-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="80182-114">Во время этапа планирования рекомендуется решить вопрос о присвоении имен расположений и определить способ назначения номеров ELIN.</span><span class="sxs-lookup"><span data-stu-id="80182-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="80182-115">Планирование имен расположений</span><span class="sxs-lookup"><span data-stu-id="80182-115">Planning Location Names</span></span>

<span data-ttu-id="80182-116">В поле " **Расположение** службы сведений о расположении", которое содержит конкретное расположение в здании, имеет максимальную длину 20 символов (включая пробелы).</span><span class="sxs-lookup"><span data-stu-id="80182-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="80182-117">Учитывая это ограничение, в поле рекомендуется включить следующие данные.</span><span class="sxs-lookup"><span data-stu-id="80182-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="80182-p104">Понятное имя, идентифицирующее расположение звонящего в аварийную службу, которое позволит агентам аварийной службы быстрее находить указанное расположение в момент прибытия по адресу. Это имя расположения может включать номер здания, номер этажа, обозначение корпусов, номер комнаты и т. д. Избегайте употребления неявных сокращенных названий, известных только сотрудникам, что может привести к направлению аварийной службы по неправильному адресу.</span><span class="sxs-lookup"><span data-stu-id="80182-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="80182-121">Идентификатор места, с помощью которого пользователи смогут легко видеть, что клиент Lync берет на себя нужное расположение.</span><span class="sxs-lookup"><span data-stu-id="80182-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="80182-122">Клиент Lync автоматически объединяет и отображает обнаруженные поля " **место** " и " **город** " в заголовке.</span><span class="sxs-lookup"><span data-stu-id="80182-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="80182-123">Рекомендуется добавить почтовый адрес здания в каждый идентификатор местоположения (например, "номер \<\>улицы первого этажа").</span><span class="sxs-lookup"><span data-stu-id="80182-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="80182-124">Без почтового адреса общий идентификатор расположения, такой как "1‑й этаж" может применяться к любому зданию в городе.</span><span class="sxs-lookup"><span data-stu-id="80182-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="80182-125">Если расположение определяется приблизительно, например по точке беспроводного доступа, можно добавить слово Near (например, "примерно 1-й этаж 1234").</span><span class="sxs-lookup"><span data-stu-id="80182-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="80182-126">Планирование номеров ELIN</span><span class="sxs-lookup"><span data-stu-id="80182-126">Planning ELINs</span></span>

<span data-ttu-id="80182-p106">После того как вы определите, каким образом следует разделить строение на расположения, необходимо решить, сколько номеров ELIN следует назначить каждому расположению. Например, в здании с несколькими этажами или корпусами различным областям можно назначить разные аварийные зоны. Обычно каждый этаж в здании считается отдельным расположением. Каждому расположению затем назначается один или несколько номеров ELIN, которые используются в качестве номеров вызова во время экстренных звонков. Обратитесь к поставщику PSTN, чтобы получить телефонные номера, которые можно использовать для ELIN. В следующей таблице представлен пример расположений для определенного почтового адреса.</span><span class="sxs-lookup"><span data-stu-id="80182-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="80182-133">Пример назначений расположений и ELIN</span><span class="sxs-lookup"><span data-stu-id="80182-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80182-134">Область здания</span><span class="sxs-lookup"><span data-stu-id="80182-134">Building Area</span></span></th>
<th><span data-ttu-id="80182-135">Расположение</span><span class="sxs-lookup"><span data-stu-id="80182-135">Location</span></span></th>
<th><span data-ttu-id="80182-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="80182-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80182-137">Первый этаж</span><span class="sxs-lookup"><span data-stu-id="80182-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="80182-138">1</span><span class="sxs-lookup"><span data-stu-id="80182-138">1</span></span></p></td>
<td><p><span data-ttu-id="80182-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="80182-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80182-140">Второй этаж</span><span class="sxs-lookup"><span data-stu-id="80182-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="80182-141">2</span><span class="sxs-lookup"><span data-stu-id="80182-141">2</span></span></p></td>
<td><p><span data-ttu-id="80182-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="80182-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80182-143">Третий этаж</span><span class="sxs-lookup"><span data-stu-id="80182-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="80182-144">3</span><span class="sxs-lookup"><span data-stu-id="80182-144">3</span></span></p></td>
<td><p><span data-ttu-id="80182-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="80182-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80182-146">Задаваемые расположения должны удовлетворять следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="80182-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="80182-147">Соответствовать местным и общегосударственным правилам в отношении максимальной области для расположения и числа расположений на каждый почтовый адрес.</span><span class="sxs-lookup"><span data-stu-id="80182-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="80182-148">Быть достаточно конкретными, чтобы можно было легко определить местонахождение абонента, совершающего экстренный вызов.</span><span class="sxs-lookup"><span data-stu-id="80182-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="80182-149">Заполнение базы данных расположений</span><span class="sxs-lookup"><span data-stu-id="80182-149">Populating the Location Database</span></span>

<span data-ttu-id="80182-150">Ниже приведены вопросы, которые помогут определить порядок заполнения базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="80182-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="80182-151">**Какой процесс будет использоваться для заполнения базы данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="80182-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="80182-p107">Где хранятся данные и какие действия необходимо выполнить, чтобы преобразовать данные в формат, требуемый базой данных расположений? Будут ли расположения добавляться по отдельности или массово, используя CSV-файл?</span><span class="sxs-lookup"><span data-stu-id="80182-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="80182-154">**Используется ли сторонняя база данных, которая уже содержит сопоставление расположений?**</span><span class="sxs-lookup"><span data-stu-id="80182-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="80182-155">С помощью параметра службы дополнительных сведений о расположении Lync Server для подключения к базе данных третьих лиц вы можете группировать и управлять ими с помощью автономной платформы.</span><span class="sxs-lookup"><span data-stu-id="80182-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="80182-156">Преимущество этого метода заключается в том, что он позволяет связывать расположения не только с идентификаторами сети, но и с пользователями.</span><span class="sxs-lookup"><span data-stu-id="80182-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="80182-157">Это означает, что служба сведений о расположении может возвращать несколько адресов, исходящих из дополнительной службы сведений о расположении, в клиенте Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80182-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="80182-158">Пользователь затем может выбрать наиболее подходящее расположение.</span><span class="sxs-lookup"><span data-stu-id="80182-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="80182-159">Для интеграции со службой сведений о расположении база данных стороннего поставщика должна следовать схеме запроса на расположение на сервере Lync Server/ответа.</span><span class="sxs-lookup"><span data-stu-id="80182-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="80182-160">Подробности можно найти в <http://go.microsoft.com/fwlink/p/?linkid=213819>разделе.</span><span class="sxs-lookup"><span data-stu-id="80182-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="80182-161">Дополнительные сведения о развертывании дополнительной службы сведений о расположении можно найти [в разделе Настройка дополнительной службы сведений о расположении в Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="80182-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="80182-162">Сведения о заполнении базы данных местоположений содержатся в разделе [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="80182-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="80182-163">Обслуживание базы данных расположений</span><span class="sxs-lookup"><span data-stu-id="80182-163">Maintaining the Location Database</span></span>

<span data-ttu-id="80182-p110">После заполнения базы данных необходимо разработать стратегию обновления базы данных по мере внесения изменений в конфигурацию сети. Ниже приведены вопросы, которые помогут определить порядок обслуживания базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="80182-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="80182-166">**Как будет обновляться база данных расположений?**</span><span class="sxs-lookup"><span data-stu-id="80182-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="80182-p111">Существует несколько сценариев, которые требуют обновления базы данных расположений, включая добавление протоколов WAP, изменение разводки в офисе (в связи с разными назначениями коммутаторов) и расширение подсети. Будет ли выполняться прямое обновление каждого отдельного расположения или массовое обновление всех расположений с помощью CSV-файла?</span><span class="sxs-lookup"><span data-stu-id="80182-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="80182-169">**Будет ли использоваться для сопоставления MAC-адресов клиентов Lync с портами и идентификаторами коммутаторов приложение SNMP?**</span><span class="sxs-lookup"><span data-stu-id="80182-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="80182-170">При использовании приложения SNMP потребуется разработать ручную процедуру, которая позволит поддерживать согласованность данных о портах и корпусах коммутаторов между приложением SNMP и базой данных расположений.</span><span class="sxs-lookup"><span data-stu-id="80182-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="80182-171">Если приложение SNMP возвращает IP-адрес или идентификатор порта, не включенный в базу данных, Служба сведений о расположении не сможет возвращать данные о расположении клиенту.</span><span class="sxs-lookup"><span data-stu-id="80182-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

