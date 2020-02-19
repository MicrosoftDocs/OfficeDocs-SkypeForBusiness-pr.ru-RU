---
title: 'Lync Server 2013: контрольный список развертывания для E9 — 1 — 1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38e2cffcaa54df8d9a7bc3715d609ac4bc7d7b8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="d69c3-102">Контрольный список развертывания для E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d69c3-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d69c3-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d69c3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d69c3-104">Чтобы разработать эффективный план для Enhanced 9-1-1 (E9-1-1), обязательно включите в него следующие требования по развертыванию:</span><span class="sxs-lookup"><span data-stu-id="d69c3-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="d69c3-105">необходимые компоненты для развертывания E9-1-1;</span><span class="sxs-lookup"><span data-stu-id="d69c3-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="d69c3-106">шаги, необходимые для развертывания E9-1-1;</span><span class="sxs-lookup"><span data-stu-id="d69c3-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="d69c3-107">Необходимые компоненты для развертывания E9-1-1</span><span class="sxs-lookup"><span data-stu-id="d69c3-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="d69c3-108">Перед развертыванием E9-1-1 необходимо развернуть внутренние серверы Lync Server, в том числе центральное хранилище управления, интерфейсный пул или сервер Standard Edition, один или несколько серверов-посредников или пулов серверов-посредников, а также клиентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d69c3-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="d69c3-109">Кроме того, для развертывания E9-1-1 требуется SIP-магистраль до квалифицированного поставщика услуг E9-1-1 или шлюз ELIN до телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="d69c3-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="d69c3-110">Lync Server поддерживает использование поставщиков услуг E9 – 1 – 1 только в США.</span><span class="sxs-lookup"><span data-stu-id="d69c3-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="d69c3-111">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="d69c3-111">Deployment Process</span></span>

<span data-ttu-id="d69c3-112">В следующей таблице представлен обзор процесса развертывания E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d69c3-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="d69c3-113">Дополнительные сведения о действиях по развертыванию можно найти в статье [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d69c3-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d69c3-114">Этап</span><span class="sxs-lookup"><span data-stu-id="d69c3-114">Phase</span></span></th>
<th><span data-ttu-id="d69c3-115">Шаги</span><span class="sxs-lookup"><span data-stu-id="d69c3-115">Steps</span></span></th>
<th><span data-ttu-id="d69c3-116">Роли</span><span class="sxs-lookup"><span data-stu-id="d69c3-116">Roles</span></span></th>
<th><span data-ttu-id="d69c3-117">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="d69c3-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d69c3-118">Настройка использования, маршрутов и конфигурации магистрали для голосовой связи</span><span class="sxs-lookup"><span data-stu-id="d69c3-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d69c3-p103">Создайте новую запись об использовании ТСОП. Ее имя совпадает с именем, которое используется для параметра в <strong>Использование ТСОП</strong> в политики расположения.</span><span class="sxs-lookup"><span data-stu-id="d69c3-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-121">Создайте или назначьте голосовой маршрут в записи использования ТСОП, созданную на предыдущем шаге, а затем укажите в атрибуте шлюза SIP-магистраль E9-1-1 или шлюз ELIN.</span><span class="sxs-lookup"><span data-stu-id="d69c3-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-122">Для поставщика услуг E9-1-1 SIP-магистрали установите магистраль, которая будет обрабатывать вызовы E9-1-1 в SIP для передачи данных PIDF-LO, используя командлет <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</span><span class="sxs-lookup"><span data-stu-id="d69c3-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-p104">При необходимости для поставщика услуг E9-1-1 SIP-магистрали создайте или назначьте локальный маршрут PSTN для вызовов, которые не обрабатываются SIP-магистралью поставщика услуг E9-1-1. Этот маршрут будет использоваться, если связь с поставщиком услуг E9-1-1 недоступна. Если это поддерживается поставщиком услуг E9-1-1, назначьте правило конфигурации магистрали шлюзу, который преобразует строку набора 911 в номер DID национальной или региональной экстренной службы (ECRC).</span><span class="sxs-lookup"><span data-stu-id="d69c3-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d69c3-126">ксвоицеадмин</span><span class="sxs-lookup"><span data-stu-id="d69c3-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="d69c3-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Настройка маршрута голосовой связи E9 – 1 – 1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69c3-128">Создайте политики местоположения и назначьте их пользователям и подсетям</span><span class="sxs-lookup"><span data-stu-id="d69c3-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d69c3-129">Изучите глобальную политику расположения.</span><span class="sxs-lookup"><span data-stu-id="d69c3-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-130">Создайте политику расположения в области на уровне пользователя; или, если в организации несколько узлов с различными способами использования экстренных вызовов, создайте политику расположения в области на уровне сети.</span><span class="sxs-lookup"><span data-stu-id="d69c3-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-131">Назначьте политику расположения сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="d69c3-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-132">Добавьте соответствующие подсети к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="d69c3-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-133">(Необязательно) Назначьте политику расположения политикам пользователя.</span><span class="sxs-lookup"><span data-stu-id="d69c3-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d69c3-134">ксвоицеадмин</span><span class="sxs-lookup"><span data-stu-id="d69c3-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="d69c3-135">CSLocationAdmin (кроме создания политик расположения)</span><span class="sxs-lookup"><span data-stu-id="d69c3-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="d69c3-136"><a href="lync-server-2013-create-location-policies.md">Создание политик расположения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d69c3-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Добавление политики расположения к сетевому сайту в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d69c3-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Связывание подсетей с сетевыми сайтами для E9-1-1 в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d69c3-139">Настройка базы данных расположения</span><span class="sxs-lookup"><span data-stu-id="d69c3-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d69c3-140">Заполните базу данных с сопоставлением сетевых элементов местоположениям.</span><span class="sxs-lookup"><span data-stu-id="d69c3-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-141">Для шлюзов ELIN добавьте Elin в столбец &lt;CompanyName.&gt;</span><span class="sxs-lookup"><span data-stu-id="d69c3-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-142">Настройте подключение к поставщику услуг E9-1-1 для проверки адресов.</span><span class="sxs-lookup"><span data-stu-id="d69c3-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-143">Сверьте адреса у поставщика услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d69c3-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-144">Опубликуйте обновленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-145">Для шлюзов ELIN загрузите ELIN в базу данных ALI вашего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="d69c3-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d69c3-146">ксвоицеадмин</span><span class="sxs-lookup"><span data-stu-id="d69c3-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="d69c3-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="d69c3-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="d69c3-148"><a href="lync-server-2013-configure-the-location-database.md">Настройка базы данных местоположений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d69c3-149">(Необязательно) Настройка дополнительных функций</span><span class="sxs-lookup"><span data-stu-id="d69c3-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d69c3-150">Настройте URL-адрес для приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="d69c3-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="d69c3-151">Настройте URL-адрес расположения службы дополнительных сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="d69c3-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d69c3-152">ксвоицеадмин</span><span class="sxs-lookup"><span data-stu-id="d69c3-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="d69c3-153"><a href="lync-server-2013-configure-an-snmp-application.md">Настройка приложения SNMP в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d69c3-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Настройка службы сведений о дополнительном местоположении в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d69c3-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

