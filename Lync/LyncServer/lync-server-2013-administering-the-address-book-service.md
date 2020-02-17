---
title: 'Lync Server 2013: Администрирование службы адресной книги'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ea7a68d77acd7bbaf3de43fce38c0e85c02dad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="f19c1-102">Администрирование службы адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19c1-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f19c1-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f19c1-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f19c1-104">При развертывании сервера Lync Server, Enterprise Edition или Standard Edition служба адресной книги устанавливается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f19c1-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="f19c1-105">База данных, используемая службой адресной книги — RTCab — создается на сервере SQL Server (для Enterprise Edition это внутренний SQL-сервер; для сервера Standard Edition, совместно размещенного сервера SQL Server).</span><span class="sxs-lookup"><span data-stu-id="f19c1-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f19c1-106">Сведения об использовании команды <STRONG>Редактирование ADSI</STRONG> для изменения атрибутов объекта доменных служб Active Directory см в разделе <A href="http://go.microsoft.com/fwlink/?linkid=330427">Редактирование ADSI</A>.</span><span class="sxs-lookup"><span data-stu-id="f19c1-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="f19c1-107">Сведения о средстве из набора ресурсов, предназначенном для службы адресной книги, можно найти в <A href="http://go.microsoft.com/fwlink/?linkid=330429">статье Microsoft Lync Server 2013 Resource Kit Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="f19c1-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="f19c1-108">Нормализация номеров телефонов сервера адресной книги</span><span class="sxs-lookup"><span data-stu-id="f19c1-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="f19c1-109">Lync Server требует стандартизованные телефонные номера RFC 3966/E. 164.</span><span class="sxs-lookup"><span data-stu-id="f19c1-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="f19c1-110">Чтобы использовать неструктурированные или несогласованные номера телефонов, Lync Server использует сервер адресной книги для предварительной обработки телефонных номеров, прежде чем они передаются в правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="f19c1-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="f19c1-111">Если в адресной книге используется номер телефона, а применяется правило нормализации, то клиенты, такие как Lync Phone Edition и Lync Mobile, могут использовать эти нормализованные номера.</span><span class="sxs-lookup"><span data-stu-id="f19c1-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="f19c1-p104">Правила нормализации, которые использовались в предыдущих версиях, могут работать неправильно без некоторых настроек. Поскольку пробел и необязательные символы удаляются перед применением правил нормализации, если регулярное выражение ищет дефис или другой символ, который был удален, правило нормализации может завершиться с ошибкой. Следует проверить правила нормализации и убедиться, что они не ищут эти необязательные символы или что это правило может завершиться с ошибкой и продолжить работу, если символ не будет обнаружен там, где он ожидается.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="f19c1-115">Репликатор пользователей и сервер адресной книги</span><span class="sxs-lookup"><span data-stu-id="f19c1-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="f19c1-116">Сервер адресной книги использует данные репликатора пользователей для обновления информации, которую он изначально получает из глобального списка адресов (GAL).</span><span class="sxs-lookup"><span data-stu-id="f19c1-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="f19c1-117">Репликатор пользователей записывает атрибуты доменных служб Active Directory для каждого пользователя, контакта и группы в таблицу Абусерентри базы данных, а сервер адресной книги синхронизирует данные пользователей из базы данных с файлами в хранилище файлов сервера адресной книги и в базу данных адресной книги RTCab.</span><span class="sxs-lookup"><span data-stu-id="f19c1-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="f19c1-118">Схема таблицы AbUserEntry использует два столбца **UserGuid** и **UserData**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="f19c1-119">**Усергуид** — это столбец индекса и содержит 16-БАЙТОВЫЙ идентификатор GUID объекта Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f19c1-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="f19c1-120">**UserData** — это столбец изображения, который содержит все ранее упомянутые атрибуты доменных служб Active Directory для этого контакта.</span><span class="sxs-lookup"><span data-stu-id="f19c1-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="f19c1-121">Репликатор пользователей определяет, какие атрибуты Active Directory необходимо записать, читая таблицу конфигурации, находящуюся в том же экземпляре SQL Server, что и таблица Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="f19c1-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="f19c1-122">Таблица AbAttribute содержит три столбца: **Код**, **Имя**, **Флаги** и **Включение**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="f19c1-123">Эта таблица создается во время настройки базы данных.</span><span class="sxs-lookup"><span data-stu-id="f19c1-123">The table is created during database setup.</span></span> <span data-ttu-id="f19c1-124">Если таблица AbAttribute пуста, репликатор пользователей пропускает логику обработки таблицы AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f19c1-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="f19c1-125">Атрибуты сервера адресной книги являются динамическими и загружаются из таблицы AbAttribute, которые изначально записываются сервером адресной книги при его активации.</span><span class="sxs-lookup"><span data-stu-id="f19c1-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="f19c1-126">Активация сервера адресной книги заполняет таблицу Абаттрибуте значениями, приведенными в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f19c1-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f19c1-127">ИД</span><span class="sxs-lookup"><span data-stu-id="f19c1-127">ID</span></span></th>
<th><span data-ttu-id="f19c1-128">Имя</span><span class="sxs-lookup"><span data-stu-id="f19c1-128">Name</span></span></th>
<th><span data-ttu-id="f19c1-129">Flags</span><span class="sxs-lookup"><span data-stu-id="f19c1-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-130">1 </span><span class="sxs-lookup"><span data-stu-id="f19c1-130">1</span></span></p></td>
<td><p><span data-ttu-id="f19c1-131">givenName</span><span class="sxs-lookup"><span data-stu-id="f19c1-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="f19c1-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="f19c1-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-133">2 </span><span class="sxs-lookup"><span data-stu-id="f19c1-133">2</span></span></p></td>
<td><p><span data-ttu-id="f19c1-134">Программа</span><span class="sxs-lookup"><span data-stu-id="f19c1-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="f19c1-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="f19c1-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-136">3 </span><span class="sxs-lookup"><span data-stu-id="f19c1-136">3</span></span></p></td>
<td><p><span data-ttu-id="f19c1-137">displayName</span><span class="sxs-lookup"><span data-stu-id="f19c1-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="f19c1-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="f19c1-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-139">4 </span><span class="sxs-lookup"><span data-stu-id="f19c1-139">4</span></span></p></td>
<td><p><span data-ttu-id="f19c1-140">Должность</span><span class="sxs-lookup"><span data-stu-id="f19c1-140">Title</span></span></p></td>
<td><p><span data-ttu-id="f19c1-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="f19c1-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-142">5 </span><span class="sxs-lookup"><span data-stu-id="f19c1-142">5</span></span></p></td>
<td><p><span data-ttu-id="f19c1-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="f19c1-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="f19c1-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="f19c1-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-145">6 </span><span class="sxs-lookup"><span data-stu-id="f19c1-145">6</span></span></p></td>
<td><p><span data-ttu-id="f19c1-146">Company</span><span class="sxs-lookup"><span data-stu-id="f19c1-146">Company</span></span></p></td>
<td><p><span data-ttu-id="f19c1-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="f19c1-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-148">7 </span><span class="sxs-lookup"><span data-stu-id="f19c1-148">7</span></span></p></td>
<td><p><span data-ttu-id="f19c1-149">фисикалделиверйоффиценаме</span><span class="sxs-lookup"><span data-stu-id="f19c1-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="f19c1-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="f19c1-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-151">8 </span><span class="sxs-lookup"><span data-stu-id="f19c1-151">8</span></span></p></td>
<td><p><span data-ttu-id="f19c1-152">msRTCSIP — PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="f19c1-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="f19c1-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="f19c1-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-154">9 </span><span class="sxs-lookup"><span data-stu-id="f19c1-154">9</span></span></p></td>
<td><p><span data-ttu-id="f19c1-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f19c1-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="f19c1-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="f19c1-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-157">10 </span><span class="sxs-lookup"><span data-stu-id="f19c1-157">10</span></span></p></td>
<td><p><span data-ttu-id="f19c1-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="f19c1-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="f19c1-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="f19c1-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-160">11 </span><span class="sxs-lookup"><span data-stu-id="f19c1-160">11</span></span></p></td>
<td><p><span data-ttu-id="f19c1-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="f19c1-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="f19c1-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="f19c1-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-163">12</span><span class="sxs-lookup"><span data-stu-id="f19c1-163">12</span></span></p></td>
<td><p><span data-ttu-id="f19c1-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="f19c1-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="f19c1-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="f19c1-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-166">13</span><span class="sxs-lookup"><span data-stu-id="f19c1-166">13</span></span></p></td>
<td><p><span data-ttu-id="f19c1-167">ипфоне</span><span class="sxs-lookup"><span data-stu-id="f19c1-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="f19c1-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="f19c1-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-169">14 </span><span class="sxs-lookup"><span data-stu-id="f19c1-169">14</span></span></p></td>
<td><p><span data-ttu-id="f19c1-170">Почта</span><span class="sxs-lookup"><span data-stu-id="f19c1-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="f19c1-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="f19c1-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-172">15 </span><span class="sxs-lookup"><span data-stu-id="f19c1-172">15</span></span></p></td>
<td><p><span data-ttu-id="f19c1-173">groupType</span><span class="sxs-lookup"><span data-stu-id="f19c1-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="f19c1-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="f19c1-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-175">16 </span><span class="sxs-lookup"><span data-stu-id="f19c1-175">16</span></span></p></td>
<td><p><span data-ttu-id="f19c1-176">Отдел</span><span class="sxs-lookup"><span data-stu-id="f19c1-176">Department</span></span></p></td>
<td><p><span data-ttu-id="f19c1-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="f19c1-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-178">17 </span><span class="sxs-lookup"><span data-stu-id="f19c1-178">17</span></span></p></td>
<td><p><span data-ttu-id="f19c1-179">Описание</span><span class="sxs-lookup"><span data-stu-id="f19c1-179">Description</span></span></p></td>
<td><p><span data-ttu-id="f19c1-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="f19c1-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-181">18 </span><span class="sxs-lookup"><span data-stu-id="f19c1-181">18</span></span></p></td>
<td><p><span data-ttu-id="f19c1-182">Директор</span><span class="sxs-lookup"><span data-stu-id="f19c1-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="f19c1-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="f19c1-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-184">19</span><span class="sxs-lookup"><span data-stu-id="f19c1-184">19</span></span></p></td>
<td><p><span data-ttu-id="f19c1-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="f19c1-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="f19c1-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="f19c1-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-187">двадцать</span><span class="sxs-lookup"><span data-stu-id="f19c1-187">20</span></span></p></td>
<td><p><span data-ttu-id="f19c1-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="f19c1-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="f19c1-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="f19c1-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-190">99</span><span class="sxs-lookup"><span data-stu-id="f19c1-190">99</span></span></p></td>
<td><p><span data-ttu-id="f19c1-191">Код</span><span class="sxs-lookup"><span data-stu-id="f19c1-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="f19c1-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="f19c1-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f19c1-193">Числа в столбце **Код** должны быть уникальными и не должны использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="f19c1-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="f19c1-194">Кроме того, если значения кода не превышают 256, это позволяет экономить место в выходных файлах, записанных сервером адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f19c1-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="f19c1-195">Однако максимальное значение кода равно 65535.</span><span class="sxs-lookup"><span data-stu-id="f19c1-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="f19c1-196">Столбец **имя** соответствует атрибуту Active Directory, который репликатор пользователей должен поместить в таблицу абусерентри для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="f19c1-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="f19c1-197">Значение столбца **Флаги** используется для определения типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="f19c1-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="f19c1-198">Следующие типы атрибутов сервера адресной книги распознаются репликатором пользователей, что указано в младшем байте значения в столбце **Флаги**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f19c1-199">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f19c1-199">Attribute</span></span></th>
<th><span data-ttu-id="f19c1-200">Описание</span><span class="sxs-lookup"><span data-stu-id="f19c1-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-201">0x0</span><span class="sxs-lookup"><span data-stu-id="f19c1-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p108">Строковый атрибут. Репликатор пользователей преобразует этот тип в UTF-8 перед сохранением в таблице AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-204">0x1</span><span class="sxs-lookup"><span data-stu-id="f19c1-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p109">Двоичный атрибут. Репликатор пользователей сохраняет его в BLOB-объекте без преобразования.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-207">0x2</span><span class="sxs-lookup"><span data-stu-id="f19c1-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="f19c1-208">Строковый атрибут, который включается, только если значение атрибута начинается с &quot;Tel:&quot;.</span><span class="sxs-lookup"><span data-stu-id="f19c1-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="f19c1-209">Это прежде всего требуется для многозначных строковых атрибутов, в частности <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="f19c1-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="f19c1-210">В этом случае сервер адресной книги нужен только в записях <strong>proxyAddresses</strong> , начинающихся с &quot;Tel:&quot;.</span><span class="sxs-lookup"><span data-stu-id="f19c1-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="f19c1-211">Таким образом, в интересах экономии места репликаторы пользователей хранят только записи, начинающиеся с &quot;Tel:.&quot;</span><span class="sxs-lookup"><span data-stu-id="f19c1-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-212">0x3</span><span class="sxs-lookup"><span data-stu-id="f19c1-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p111">Логический строковый атрибут: если его значение равно TRUE, репликатор пользователей не включает этот контакт в таблицу AbUserEntry. Если значение атрибута равно FALSE, репликатор включает атрибуты данного контакта в таблицу AbUserEntry (но не определенный атрибут с этим флагом). Это еще один особый тип, который прежде всего предназначен для атрибута <strong>msExchHideFromAddressLists</strong>.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-216">0x4</span><span class="sxs-lookup"><span data-stu-id="f19c1-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="f19c1-217">Строковый атрибут, который включается, только если значение атрибута начинается с &quot;SMTP:&quot; и содержит &quot; @ &quot; символ.</span><span class="sxs-lookup"><span data-stu-id="f19c1-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-218">0x5</span><span class="sxs-lookup"><span data-stu-id="f19c1-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="f19c1-219">Строковый атрибут, который включается, только если значение атрибута начинается с " &quot;Tel"&quot; или &quot;"SMTP&quot; ", а &quot; @ &quot; также содержит символ.</span><span class="sxs-lookup"><span data-stu-id="f19c1-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-220">0x100</span><span class="sxs-lookup"><span data-stu-id="f19c1-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="f19c1-221">Если этот параметр установлен, это многозначный атрибут, который может использоваться несколько раз для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="f19c1-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-222">0x400</span><span class="sxs-lookup"><span data-stu-id="f19c1-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p112">Если этот параметр установлен, этот атрибут идентифицирует атрибут имени учетной записи электронной почты пользователя для контакта. Сервер адресной книги использует этот флаг, чтобы определить, какое значение атрибута будет показано в записи журнала событий нормализации телефона.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-225">0x800</span><span class="sxs-lookup"><span data-stu-id="f19c1-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p113">Если этот параметр задан, этот обязательный атрибут определяет для контакта. Сервер адресной книги добавляет пользователя в таблицу AbUserEntry только при наличии значения этого атрибута в Active Directory. Если существует несколько обязательных атрибутов, только у одного из них должно быть значение, чтобы пользователя был включен в таблицу AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="f19c1-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-230">Если этот параметр установлен, сервер адресной книги всегда нормализует значение этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f19c1-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="f19c1-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-232">Если этот параметр установлен, сервер адресной книги использует нормализованный номер из <strong>proxyAddresses</strong>, если параметр CMS <strong>UseNormalizationRules</strong> имеет значение False; в противном случае сервер действует оно ведет себя так же, как и при бите флага равном 0x1000.</span><span class="sxs-lookup"><span data-stu-id="f19c1-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="f19c1-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p114">Если этот параметр установлен, сервер адресной книги не включает в таблицу AbUserEntry объекты, содержащие это значение для заданного атрибута. Например, если в атрибуте <strong>msRTCSIP-PrimaryUserAddress</strong> задан этот бит флага. контакты с этим атрибутом не записываются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="f19c1-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p115">Если этот параметр установлен, сервер адресной книги не включает в таблицу AbUserEntry объекты без этого значения для указанного атрибута. Если для объекта установлены оба битовых флажка 0x4000 и 0x8000, атрибут со значением флаг 0x4000 имеет приоритет, а объект исключается из таблицы AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="f19c1-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p116">Если этот параметр задан, данный объект представляет собой объект группы. Репликатор пользователей использует этот флаг для включения контактов с атрибутом <strong>groupType</strong>, наличие которого указывает на группу (например, список рассылки или группу безопасности).</span><span class="sxs-lookup"><span data-stu-id="f19c1-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="f19c1-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-243">Если этот параметр задан, репликатор пользователей использует этот флаг для включения этого атрибута в файлы сервера адресной книги определенного устройства (то есть DABS-файлы).</span><span class="sxs-lookup"><span data-stu-id="f19c1-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f19c1-244">В предыдущих версиях Lync Server при внесении изменений в Active Directory администратору потребуется выполнить командлеты Windows PowerShell **Update-ксусердатабасе** и Update- **CSAddressBook** , чтобы немедленно оставить изменения в базе данных пользователей Lync Server и базе данных RTCab.</span><span class="sxs-lookup"><span data-stu-id="f19c1-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="f19c1-245">В Lync Server 2013 служба репликации пользователей Lync Server выберет изменения из Active Directory и обновляет базу данных пользователей Lync Server в соответствии с заданным интервалом.</span><span class="sxs-lookup"><span data-stu-id="f19c1-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="f19c1-246">Служба Replicator пользователей Lync Server также будет быстро распространять изменения базы данных RTCab, не требуя от администратора выполнять командлет Update – CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="f19c1-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="f19c1-247">Если веб-запрос адресной книги включен, изменения будут отражены в результатах поиска клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="f19c1-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="f19c1-248">Администраторы должны будут запустить Update -CSAddressBook только в случае, когда включена загрузка файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f19c1-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f19c1-249">По умолчанию репликатор пользователей Lync Server выполняется автоматически каждые 5 минут.</span><span class="sxs-lookup"><span data-stu-id="f19c1-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="f19c1-250">Этот интервал можно настроить с помощью Set – CSUserReplicatorConfiguration — Репликатионциклеинтервал &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="f19c1-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="f19c1-251">Фильтрование адресной книги</span><span class="sxs-lookup"><span data-stu-id="f19c1-251">Filtering the Address Book</span></span>

<span data-ttu-id="f19c1-252">Пользователи, заполненные в файлах сервера адресной книги, можно контролировать на основе определенных атрибутов доменных служб Active Directory, перечисленных в таблице Абаттрибуте.</span><span class="sxs-lookup"><span data-stu-id="f19c1-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="f19c1-253">Один такой атрибут используется для фильтрации — атрибут **мсексчанжехидефромаддрессбук** .</span><span class="sxs-lookup"><span data-stu-id="f19c1-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="f19c1-254">Это атрибут пользователя, добавленный в схеме Exchange.</span><span class="sxs-lookup"><span data-stu-id="f19c1-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="f19c1-255">Если значение этого атрибута равно TRUE, Exchange Server использует этот атрибут для скрытия контакта в глобальном списке адресов Outlook (GAL).</span><span class="sxs-lookup"><span data-stu-id="f19c1-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="f19c1-256">Аналогично, если значение этого атрибута равно TRUE, Replicator пользователя не включает этого пользователя в таблицу Абусерентри, и этот пользователь не будет находиться в файлах сервера адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f19c1-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="f19c1-p120">Вы можете использовать некоторые флаги для определения фильтра, который будет использоваться для атрибутов сервера адресной книги. Например, наличие определенных флагов может идентифицировать атрибут как включаемый или исключаемый. Репликатор пользователей фильтрует контакты, которые содержат атрибут исключения и фильтрует содержимое без атрибута включения.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f19c1-260">Дополнительные сведения о фильтрации адресной книги см <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">в разделе Командлеты сервера адресной книги в Lync Server 2013</A>и <A href="http://go.microsoft.com/fwlink/?linkid=330430">Фильтрация адресной книги Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="f19c1-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="f19c1-p121">В настоящее время существует три разных фильтров, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f19c1-263">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f19c1-263">Attribute</span></span></th>
<th><span data-ttu-id="f19c1-264">Описание</span><span class="sxs-lookup"><span data-stu-id="f19c1-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-265">0x800</span><span class="sxs-lookup"><span data-stu-id="f19c1-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p122">Если этот параметр задан, он определяет обязательный атрибут для контакта. Репликатор пользователей применяет этот флаг, чтобы фильтровать контакты, которые не содержат по крайней мере один необходимый атрибут. OuPathId является обязательным атрибутом, который всегда устанавливается. Также необходимо задать по крайней мере один из других обязательных атрибутов. В противном случае контакт (то есть значение обязательного атрибута OuPathId) по-прежнему не будет записано в базу данных. Например, если <strong>telephoneNumber</strong> и <strong> HomePhone </strong> определены как обязательные атрибуты, только контакты, у которых есть хотя бы один из этих атрибутов, будут записаны в базу данных.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f19c1-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="f19c1-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p123">Если этот атрибут задан, он определяет атрибут исключения. Репликатор пользователей использует этот флаг для фильтрация контактов, содержащих этот атрибут. Например, если <strong>msRTCSIP-PrimaryUserAddress</strong> определен как атрибут исключения, контакты с этим атрибутом не записываются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f19c1-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="f19c1-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="f19c1-p124">Если этот атрибут задан, он определяет атрибут включения. Репликатор пользователей использует этот флаг для фильтрация контактов, не содержащих этот атрибут. Например, если <strong>msRTCSIP-PrimaryUserAddress</strong> определен как атрибут включения, только контакты с этим атрибутом записываются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f19c1-280">Если оба флага 0x4000 (атрибут исключения) и 0x8000 (атрибут включения) установлены, бит 0x4000 переопределяет бит 0x8000, а контакт исключается.</span><span class="sxs-lookup"><span data-stu-id="f19c1-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="f19c1-p125">Хотя вы можете фильтровать адресную книгу так, чтобы включить только определенных пользователей, ограничение записей не ограничивает возможностей других пользователей для связи с отфильтрованными пользователями или просмотра сведений об их присутствии. Пользователи всегда могут выполнять поиск, вручную отправлять мгновенные сообщения или вручную инициировать вызовы пользователей, не входящих в адресную книгу, вводя полное имя входа пользователя. Кроме того, контактные данные пользователя также можно найти в Outlook.</span><span class="sxs-lookup"><span data-stu-id="f19c1-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="f19c1-284">Несмотря на то, что в файлах адресной книги есть полные записи контактов, можно использовать Lync Server для инициирования электронных вызовов, звонков по телефону или корпоративной голосовой связи (то есть, если на сервере включена Корпоративная голосовая связь) с пользователями, не настроенными для запуска сеанса. Протокол SIP, некоторые организации предпочитают включать в свои записи сервера адресной книги только пользователей с включенной поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="f19c1-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="f19c1-285">Вы можете фильтровать адресную книгу так, чтобы включить в нее только пользователей с поддержкой SIP, сняв бит 0x800 в столбце **Флаги** следующих обязательных атрибутов: **mailNickname**, **telephoneNumber**, **homePhone** и **mobile**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="f19c1-286">Вы также можете отфильтровать адресную книгу, чтобы включить в нее только пользователей с поддержкой SIP, установив флаг 0x8000 (атрибут включения) в столбце **Флаги** атрибута **msRTCSIP-PrimaryUserAddress**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="f19c1-287">Это также помогает исключить учетные записи службы из файлов адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f19c1-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="f19c1-288">После изменения таблицы AbAttribute вы можете обновить данные в таблице AbUserEntry, выполнив командлет **Update-CsUserDatabase**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="f19c1-289">После завершения репликации UR, можно обновить файл в хранилище файлов сервера адресной книги вручную, выполнив командлет **UpdateCsAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="f19c1-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f19c1-290">Сервер переднего плана, на котором размещается сервер адресной книги, не может настраиваться административно.</span><span class="sxs-lookup"><span data-stu-id="f19c1-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="f19c1-291">Он выбирается во время развертывания — обычно первый сервер переднего плана разворачивается.</span><span class="sxs-lookup"><span data-stu-id="f19c1-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="f19c1-292">В случае сбоя служба адресной книги перейдет на другой сервер переднего плана и не требует вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="f19c1-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f19c1-293">Если вы консолидируем или иным образом изменили инфраструктуру в развертывании с несколькими лесами или родительской/дочерней среде (например, консолидируя инфраструктуру перед переходом на Lync Server), может оказаться, что загрузка службы адресной книги и веб-запрос адресной книги для некоторых пользователей завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f19c1-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="f19c1-294">В развертывании со множеством доменов или лесов атрибут <STRONG>MsRTCSIP-OriginatorSid</STRONG> заполняется в объектах пользователей, которые вызывают проблему.</span><span class="sxs-lookup"><span data-stu-id="f19c1-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="f19c1-295">Для атрибута <STRONG>MsRTCSIP-OriginatorSid</STRONG> необходимо задать значение NULL в этих объектах, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="f19c1-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

