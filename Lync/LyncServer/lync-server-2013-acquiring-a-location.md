---
title: 'Lync Server 2013: получение сведений о местоположении'
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
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="e4d0d-102">Получение сведений о местоположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d0d-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d0d-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e4d0d-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e4d0d-104">В среде Lync Server 2013 E9-1-1 — Каждый внутренний подключаемый клиент Lync или Lync Phone Edition активно получает свое собственное расположение.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="e4d0d-105">После регистрации SIP клиент помещает все сведения о сетевом подключении, которые ему знают, в запрос расположения службе сведений о расположении, которая является веб-службой с помощью реплицированной базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="e4d0d-106">У каждого центрального пула сайтов есть служба сведений о расположении, которая использует сведения о сети для запроса записей для соответствующего местоположения.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="e4d0d-107">В случае соответствия служба сведений о расположении возвращает расположение клиенту.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="e4d0d-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span><span class="sxs-lookup"><span data-stu-id="e4d0d-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="e4d0d-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span><span class="sxs-lookup"><span data-stu-id="e4d0d-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="e4d0d-110">Клиент Lync Server включает данные из ПИДФ в процессе вызова экстренной помощи, и эти данные используются поставщиком услуг E9-1-1, чтобы определить соответствующие ПСАП и перенаправить вызов на этот ПСАП вместе с правильным ЕСКК, что позволяет диспетчеру ПСАП получить расположение вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="e4d0d-111">На приведенной ниже схеме показано, как клиент Lync Server получает расположение (за исключением метода расположения, основанного на сторонних MAC-адресах сторонних клиентов).</span><span class="sxs-lookup"><span data-stu-id="e4d0d-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="e4d0d-112">![Получение расположения клиентом (схема)](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Получение расположения клиентом (схема)")</span><span class="sxs-lookup"><span data-stu-id="e4d0d-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="e4d0d-113">Чтобы клиент мог получить местоположение, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="e4d0d-114">Администратор заполнит базу данных службы сведений о расположении, указав сетевые виремап (таблицы, которые сопоставляют различные типы сетевых адресов с соответствующими расположениями в службе аварийного реагирования (Ерлс)).</span><span class="sxs-lookup"><span data-stu-id="e4d0d-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="e4d0d-p102">Если используется поставщик службы E9-1-1 с магистралью SIP, администратор проверяет физические адреса в ERL по базе данных основного справочника адресов (MSAG), поддерживаемой поставщиком службы E9-1-1. Если используется шлюз ELIN, администратор проверяет, что оператор ТСОП отправляет данные ELIN в базу данных автоматического определения местоположения (ALI).</span><span class="sxs-lookup"><span data-stu-id="e4d0d-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="e4d0d-117">Во время регистрации или при каждом изменении сети внутренний подключаемый клиент отправляет запрос на расположение, содержащий обнаруженные сетевые адреса клиента, в службу сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="e4d0d-118">Служба сведений о расположении запрашивает опубликованные записи для местоположения и, если оно найдено, возвращает ЕРЛ клиенту в формате ПИДФ.</span><span class="sxs-lookup"><span data-stu-id="e4d0d-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

