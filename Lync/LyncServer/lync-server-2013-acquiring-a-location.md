---
title: 'Lync Server 2013: получение расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e726424e9e24c223bc7e75346bd0c2188f29ee7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="2d1c3-102">Получение расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d1c3-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d1c3-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2d1c3-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2d1c3-104">В развертывании Lync Server 2013 E9 – 1 – Каждый внутренний подключенный клиент Lync или Lync Phone Edition активно получает свое расположение.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="2d1c3-105">После регистрации SIP клиент помещает все сведения о сетевом подключении, которые он знает, в запросе расположения в службу сведений о расположении, которая является веб-службой, созданной реплицированной базой данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="2d1c3-106">Каждый пул центрального сайта имеет службу сведений о местоположении, которая использует сведения о сети для отправки запросов к записям для соответствующего расположения.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="2d1c3-107">Если найдено соответствующее значение, Служба сведений о местоположении возвращает расположение клиенту.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="2d1c3-108">Если соответствие отсутствует, пользователю может быть предложено ввести местоположение вручную (в зависимости от параметров политики определения местоположения).</span><span class="sxs-lookup"><span data-stu-id="2d1c3-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="2d1c3-109">Данные о местоположении передаются клиенту в XML-формате стандарта IETF, называемом Presence Information Data Format Location Object (PIDF-LO).</span><span class="sxs-lookup"><span data-stu-id="2d1c3-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="2d1c3-110">Клиент Lync Server включает данные PIDF в экстренном вызове, и эти данные используются поставщиком услуг E9-1-1 для определения соответствующего PSAP и маршрутизации вызова к этому PSAP вместе с правильным ЕСКК, что позволяет диспетчеру PSAP получить Местоположение вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="2d1c3-111">На следующей схеме показано, как клиент Lync Server получает расположение (за исключением метода расположения на основе MAC-адреса стороннего клиента).</span><span class="sxs-lookup"><span data-stu-id="2d1c3-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="2d1c3-112">![Получение схемы расположения клиентом](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Получение схемы расположения клиентом")</span><span class="sxs-lookup"><span data-stu-id="2d1c3-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="2d1c3-113">Чтобы клиент мог получить местоположение, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="2d1c3-114">Администратор заполняет базу данных службы сведений о местоположении сетевым карты географических соответствий (таблицами, которые сопоставляют различные типы сетевых адресов с соответствующими расположениями аварийного ответа (ERL)).</span><span class="sxs-lookup"><span data-stu-id="2d1c3-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="2d1c3-p102">Если используется поставщик службы E9-1-1 с магистралью SIP, администратор проверяет физические адреса в ERL по базе данных основного справочника адресов (MSAG), поддерживаемой поставщиком службы E9-1-1. Если используется шлюз ELIN, администратор проверяет, что оператор ТСОП отправляет данные ELIN в базу данных автоматического определения местоположения (ALI).</span><span class="sxs-lookup"><span data-stu-id="2d1c3-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="2d1c3-117">Во время регистрации или при каждом изменении сети клиент с внутренним подключением отправляет запрос о расположении, содержащий обнаруженные сетевые адреса клиента в службу сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="2d1c3-118">Служба сведений о местоположении запрашивает опубликованные записи для расположения и, если найдено, возвращает Пэр клиенту в формате PIDF.</span><span class="sxs-lookup"><span data-stu-id="2d1c3-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

