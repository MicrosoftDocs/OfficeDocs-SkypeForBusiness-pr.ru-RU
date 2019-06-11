---
title: 'Lync Server 2013: Администрирование службы адресной книги'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="6066c-102">Администрирование службы адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6066c-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6066c-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6066c-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6066c-104">Как часть развертывания Lync Server, Enterprise Edition или Standard Edition, служба адресной книги устанавливается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6066c-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="6066c-105">База данных, используемая службой адресных книг — Рткаб — создается на сервере SQL Server (для Enterprise Edition — это сервер SQL Server, размещенный на сервере Standard Edition, выровненный SQL Server).</span><span class="sxs-lookup"><span data-stu-id="6066c-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6066c-106">Сведения об использовании команды " <STRONG>Редактирование ADSI</STRONG> " для редактирования атрибутов объектов доменных служб Active Directory смотрите в разделе <A href="http://go.microsoft.com/fwlink/?linkid=330427">Редактирование ADSI</A>.</span><span class="sxs-lookup"><span data-stu-id="6066c-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="6066c-107">Сведения о средстве из набора ресурсов, специально предназначенном для службы адресной книги, можно найти в статьях <A href="http://go.microsoft.com/fwlink/?linkid=330429">инструменты Microsoft Lync Server 2013 Resource Kit</A>.</span><span class="sxs-lookup"><span data-stu-id="6066c-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="6066c-108">Нормализация номера телефона сервера адресной книги</span><span class="sxs-lookup"><span data-stu-id="6066c-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="6066c-109">Для Lync Server требуются стандартизированные телефонные номера RFC 3966/E. 164.</span><span class="sxs-lookup"><span data-stu-id="6066c-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="6066c-110">Чтобы использовать неструктурированные или неоднородные номера телефонов, сервер Lync Server использует сервер адресной книги для предварительной обработки телефонных номеров, прежде чем они будут переданы в правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="6066c-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="6066c-111">При использовании номера телефона из адресной книги и применения правила нормализации, клиенты, такие как Lync Phone Edition и Lync Mobile, могут использовать эти нормализованные номера.</span><span class="sxs-lookup"><span data-stu-id="6066c-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="6066c-112">Правила нормализации, которые использовались в предыдущих версиях, могут работать неправильно без некоторых корректировок.</span><span class="sxs-lookup"><span data-stu-id="6066c-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="6066c-113">Так как пробелы и необязательные знаки удаляются до правил нормализации, если выражение Regex специально ищет дефис или другой символ, который был удален, правило нормализации может завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="6066c-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="6066c-114">Необходимо проанализировать правила нормализации, чтобы убедиться в том, что эти необязательные символы, а также в том случае, если правило не просматриваются, и продолжит работу в том случае, если этот знак не отображается в том месте, где оно будет считаться.</span><span class="sxs-lookup"><span data-stu-id="6066c-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="6066c-115">Репликатор пользователей и сервер адресной книги</span><span class="sxs-lookup"><span data-stu-id="6066c-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="6066c-116">Сервер адресной книги использует данные, предоставленные репликатором пользователей, для обновления первоначально используемых данных в глобальном списке адресов (GAL).</span><span class="sxs-lookup"><span data-stu-id="6066c-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="6066c-117">Репликатор пользователей записывает атрибуты доменных служб Active Directory для каждого пользователя, контакта и группы в таблицу Абусерентри в базе данных, а сервер адресной книги синхронизирует данные пользователя из базы данных с файлами в хранилище файлов на сервере адресной книги и в базу данных адресной книги Рткаб.</span><span class="sxs-lookup"><span data-stu-id="6066c-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="6066c-118">Схема для таблицы Абусерентри использует два столбца: **усергуид** и **UserData**.</span><span class="sxs-lookup"><span data-stu-id="6066c-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="6066c-119">**Усергуид** — это Индексный столбец, который содержит 16-БАЙТОВЫЙ идентификатор GUID объекта службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6066c-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="6066c-120">**UserData** — это столбец с изображением, который содержит все ранее упомянутые атрибуты доменных служб Active Directory для этого контакта.</span><span class="sxs-lookup"><span data-stu-id="6066c-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="6066c-121">Репликатор пользователей определяет, какие атрибуты Active Directory нужно записать, прочитав таблицу конфигурации, расположенную в том же экземпляре SQL Server, что и в таблице Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="6066c-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="6066c-122">Таблица Абаттрибуте включает в себя три столбца: **ID**, **Name**, **flags**и **Enable**.</span><span class="sxs-lookup"><span data-stu-id="6066c-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="6066c-123">Таблица будет создана при настройке базы данных.</span><span class="sxs-lookup"><span data-stu-id="6066c-123">The table is created during database setup.</span></span> <span data-ttu-id="6066c-124">Если таблица Абаттрибуте пуста, то репликатор пользователей пропускает свою логику обработки таблицы Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="6066c-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="6066c-125">Атрибуты сервера адресной книги являются динамическими и извлекаются из таблицы Абаттрибуте, которая первоначально записывается сервером адресной книги при активации сервера адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6066c-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="6066c-126">Активация сервера адресной книги заполняет таблицу Абаттрибуте значениями, указанными в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="6066c-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6066c-127">ID</span><span class="sxs-lookup"><span data-stu-id="6066c-127">ID</span></span></th>
<th><span data-ttu-id="6066c-128">Имя</span><span class="sxs-lookup"><span data-stu-id="6066c-128">Name</span></span></th>
<th><span data-ttu-id="6066c-129">Флажки</span><span class="sxs-lookup"><span data-stu-id="6066c-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6066c-130">1</span><span class="sxs-lookup"><span data-stu-id="6066c-130">1</span></span></p></td>
<td><p><span data-ttu-id="6066c-131">Гивеннаме</span><span class="sxs-lookup"><span data-stu-id="6066c-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="6066c-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="6066c-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-133">2</span><span class="sxs-lookup"><span data-stu-id="6066c-133">2</span></span></p></td>
<td><p><span data-ttu-id="6066c-134">Серий</span><span class="sxs-lookup"><span data-stu-id="6066c-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="6066c-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="6066c-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-136">3</span><span class="sxs-lookup"><span data-stu-id="6066c-136">3</span></span></p></td>
<td><p><span data-ttu-id="6066c-137">Водить</span><span class="sxs-lookup"><span data-stu-id="6066c-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="6066c-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="6066c-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-139">4</span><span class="sxs-lookup"><span data-stu-id="6066c-139">4</span></span></p></td>
<td><p><span data-ttu-id="6066c-140">Название</span><span class="sxs-lookup"><span data-stu-id="6066c-140">Title</span></span></p></td>
<td><p><span data-ttu-id="6066c-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="6066c-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-142">5</span><span class="sxs-lookup"><span data-stu-id="6066c-142">5</span></span></p></td>
<td><p><span data-ttu-id="6066c-143">Атрибута mailNickname</span><span class="sxs-lookup"><span data-stu-id="6066c-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="6066c-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="6066c-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-145">6</span><span class="sxs-lookup"><span data-stu-id="6066c-145">6</span></span></p></td>
<td><p><span data-ttu-id="6066c-146">Между</span><span class="sxs-lookup"><span data-stu-id="6066c-146">Company</span></span></p></td>
<td><p><span data-ttu-id="6066c-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="6066c-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-148">7</span><span class="sxs-lookup"><span data-stu-id="6066c-148">7</span></span></p></td>
<td><p><span data-ttu-id="6066c-149">Фисикалделиверйоффиценаме</span><span class="sxs-lookup"><span data-stu-id="6066c-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="6066c-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="6066c-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-151">No8</span><span class="sxs-lookup"><span data-stu-id="6066c-151">8</span></span></p></td>
<td><p><span data-ttu-id="6066c-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="6066c-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="6066c-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="6066c-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-154">@</span><span class="sxs-lookup"><span data-stu-id="6066c-154">9</span></span></p></td>
<td><p><span data-ttu-id="6066c-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="6066c-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="6066c-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="6066c-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-157">5-10</span><span class="sxs-lookup"><span data-stu-id="6066c-157">10</span></span></p></td>
<td><p><span data-ttu-id="6066c-158">Хомефоне</span><span class="sxs-lookup"><span data-stu-id="6066c-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="6066c-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="6066c-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-160">11</span><span class="sxs-lookup"><span data-stu-id="6066c-160">11</span></span></p></td>
<td><p><span data-ttu-id="6066c-161">Мобильный</span><span class="sxs-lookup"><span data-stu-id="6066c-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="6066c-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="6066c-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-163">12</span><span class="sxs-lookup"><span data-stu-id="6066c-163">12</span></span></p></td>
<td><p><span data-ttu-id="6066c-164">Осертелефоне</span><span class="sxs-lookup"><span data-stu-id="6066c-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="6066c-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="6066c-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-166">рис</span><span class="sxs-lookup"><span data-stu-id="6066c-166">13</span></span></p></td>
<td><p><span data-ttu-id="6066c-167">Ипфоне</span><span class="sxs-lookup"><span data-stu-id="6066c-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="6066c-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="6066c-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-169">14</span><span class="sxs-lookup"><span data-stu-id="6066c-169">14</span></span></p></td>
<td><p><span data-ttu-id="6066c-170">Сообщения</span><span class="sxs-lookup"><span data-stu-id="6066c-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="6066c-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="6066c-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-172">10-15</span><span class="sxs-lookup"><span data-stu-id="6066c-172">15</span></span></p></td>
<td><p><span data-ttu-id="6066c-173">Грауптипе</span><span class="sxs-lookup"><span data-stu-id="6066c-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="6066c-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="6066c-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-175">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="6066c-175">16</span></span></p></td>
<td><p><span data-ttu-id="6066c-176">Отдел</span><span class="sxs-lookup"><span data-stu-id="6066c-176">Department</span></span></p></td>
<td><p><span data-ttu-id="6066c-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="6066c-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-178">18</span><span class="sxs-lookup"><span data-stu-id="6066c-178">17</span></span></p></td>
<td><p><span data-ttu-id="6066c-179">Описание</span><span class="sxs-lookup"><span data-stu-id="6066c-179">Description</span></span></p></td>
<td><p><span data-ttu-id="6066c-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="6066c-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-181">18</span><span class="sxs-lookup"><span data-stu-id="6066c-181">18</span></span></p></td>
<td><p><span data-ttu-id="6066c-182">Директор</span><span class="sxs-lookup"><span data-stu-id="6066c-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="6066c-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="6066c-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-184">19</span><span class="sxs-lookup"><span data-stu-id="6066c-184">19</span></span></p></td>
<td><p><span data-ttu-id="6066c-185">Проксяддресс</span><span class="sxs-lookup"><span data-stu-id="6066c-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="6066c-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="6066c-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-187">средняя</span><span class="sxs-lookup"><span data-stu-id="6066c-187">20</span></span></p></td>
<td><p><span data-ttu-id="6066c-188">Мсексчхидефромаддресслистс</span><span class="sxs-lookup"><span data-stu-id="6066c-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="6066c-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="6066c-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-190">99</span><span class="sxs-lookup"><span data-stu-id="6066c-190">99</span></span></p></td>
<td><p><span data-ttu-id="6066c-191">entryID</span><span class="sxs-lookup"><span data-stu-id="6066c-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="6066c-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="6066c-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6066c-193">Числа в столбце " **идентификатор** " должны быть уникальными и не должны использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="6066c-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="6066c-194">Кроме того, при сохранении значений ИДЕНТИФИКАТОРов в разделе 256 сохраняются места в выходных файлах, написанных сервером адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6066c-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="6066c-195">Однако максимальное значение идентификатора — 65535.</span><span class="sxs-lookup"><span data-stu-id="6066c-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="6066c-196">Столбец **Name** соответствует имени атрибута Active Directory, которое репликатор пользователей должен добавить в таблицу абусерентри для каждого контакта.</span><span class="sxs-lookup"><span data-stu-id="6066c-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="6066c-197">Значение в столбце **flags** используется для определения типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="6066c-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="6066c-198">Следующие типы атрибутов сервера адресной книги распознаются репликатором пользователей, обозначается младшим байтом значения в столбце **flags** .</span><span class="sxs-lookup"><span data-stu-id="6066c-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6066c-199">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6066c-199">Attribute</span></span></th>
<th><span data-ttu-id="6066c-200">Описание</span><span class="sxs-lookup"><span data-stu-id="6066c-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6066c-201">0x0</span><span class="sxs-lookup"><span data-stu-id="6066c-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="6066c-202">Строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-202">A string attribute.</span></span> <span data-ttu-id="6066c-203">Репликатор пользователей преобразует этот тип в кодировку UTF-8, прежде чем хранить его в таблице Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="6066c-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-204">0x1</span><span class="sxs-lookup"><span data-stu-id="6066c-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="6066c-205">Двоичный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-205">A binary attribute.</span></span> <span data-ttu-id="6066c-206">Репликатор пользователей сохраняет этот объект в объекте BLOB без каких-либо преобразований.</span><span class="sxs-lookup"><span data-stu-id="6066c-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-207">0x2</span><span class="sxs-lookup"><span data-stu-id="6066c-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="6066c-208">Атрибут String, который включается, только если значение атрибута начинается с &quot;Tel:.&quot;</span><span class="sxs-lookup"><span data-stu-id="6066c-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="6066c-209">В основном это для многозначных строковых атрибутов, особенно <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="6066c-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="6066c-210">В этом случае сервер адресной книги нужен только в записях <strong>proxyAddresses</strong> , начинающихся с &quot;Tel:&quot;.</span><span class="sxs-lookup"><span data-stu-id="6066c-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="6066c-211">Таким образом, в целях экономии места репликатор пользователей хранит только записи, которые начинаются с &quot;Tel:.&quot;</span><span class="sxs-lookup"><span data-stu-id="6066c-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-212">0x3</span><span class="sxs-lookup"><span data-stu-id="6066c-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="6066c-213">Логический атрибут String, который в случае ИСТИНности приводит к тому, что этот контакт не должен быть указан в таблице Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="6066c-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="6066c-214">Если задано значение FALSE, то служба тиражирования пользователей будет включать атрибуты этого контакта в таблицу Абусерентри, но не конкретный атрибут с этим флагом.</span><span class="sxs-lookup"><span data-stu-id="6066c-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="6066c-215">Это еще один особый тип случая, преимущественно для атрибута <strong>мсексчхидефромаддресслистс</strong> .</span><span class="sxs-lookup"><span data-stu-id="6066c-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-216">0x4</span><span class="sxs-lookup"><span data-stu-id="6066c-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="6066c-217">Атрибут String, который &quot;включается, только если значение атрибута начинается с SMTP:&quot; и содержит &quot; @ &quot; символ.</span><span class="sxs-lookup"><span data-stu-id="6066c-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-218">0x5</span><span class="sxs-lookup"><span data-stu-id="6066c-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="6066c-219">Атрибут String, который включается, &quot;только если значение атрибута начинается с Tel:&quot; или &quot;SMTP:&quot; и содержит &quot; @ &quot; символ.</span><span class="sxs-lookup"><span data-stu-id="6066c-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-220">0x100</span><span class="sxs-lookup"><span data-stu-id="6066c-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="6066c-221">Если этот параметр установлен, это многозначный атрибут, который может отображаться для каждого контакта более одного раза.</span><span class="sxs-lookup"><span data-stu-id="6066c-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-222">0x400</span><span class="sxs-lookup"><span data-stu-id="6066c-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="6066c-223">Если этот параметр установлен, он определяет атрибут имени учетной записи пользователя электронной почты для контакта.</span><span class="sxs-lookup"><span data-stu-id="6066c-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="6066c-224">Сервер адресной книги использует этот флаг, чтобы определить, какое значение атрибута отобразить в записи журнала событий нормализации телефона.</span><span class="sxs-lookup"><span data-stu-id="6066c-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-225">0x800</span><span class="sxs-lookup"><span data-stu-id="6066c-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="6066c-226">Если этот параметр установлен, он определяет обязательный атрибут для контакта.</span><span class="sxs-lookup"><span data-stu-id="6066c-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="6066c-227">Адресная книга сервер включает пользователя в таблицу Абусерентри только в том случае, если в службе каталогов Active Directory есть значение для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="6066c-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="6066c-228">Если имеется несколько обязательных атрибутов, для включения пользователя в таблицу Абусерентри требуется только один из них.</span><span class="sxs-lookup"><span data-stu-id="6066c-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="6066c-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="6066c-230">Если задано, сервер адресной книги всегда нормализует значение этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="6066c-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="6066c-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="6066c-232">Если задано, сервер адресной книги использует нормализованное число из <strong>proxyAddresses</strong>, если параметр <strong>усенормализатионрулес</strong> CMS имеет значение ложь; в противном случае она будет выглядеть так же, как если бы бит флага 0x1000.</span><span class="sxs-lookup"><span data-stu-id="6066c-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="6066c-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="6066c-234">Если задано, сервер адресной книги не включает в таблицу Абусерентри объекты, которые имеют это значение для указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="6066c-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="6066c-235">Например, если в атрибуте <strong>msRTCSIP-примарюсераддресс</strong> установлен этот бит флага, то контакты с этим атрибутом не записываются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="6066c-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="6066c-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="6066c-237">Если задано, сервер адресной книги не включает в таблицу Абусерентри объекты, которые не имеют этого значения для указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="6066c-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="6066c-238">Если для объекта заданы биты флага 0x4000 и 0x8000, атрибут с битовым значением флага, установленным на 0x4000, имеет приоритет, и объект исключается из таблицы Абусерентри.</span><span class="sxs-lookup"><span data-stu-id="6066c-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="6066c-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="6066c-240">Если этот параметр установлен, это представляет объект Group.</span><span class="sxs-lookup"><span data-stu-id="6066c-240">If set, this represents a group object.</span></span> <span data-ttu-id="6066c-241">Репликатор пользователей использует этот бит флага, чтобы включить контакты с атрибутом <strong>грауптипе</strong> , чье присутствие указывает на группу (например, список рассылки или группу безопасности).</span><span class="sxs-lookup"><span data-stu-id="6066c-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="6066c-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="6066c-243">Если задано, репликатор пользователей использует этот бит флага, чтобы включить этот атрибут в файлы сервера адресной книги для конкретных устройств (файлы с расширением Дабс).</span><span class="sxs-lookup"><span data-stu-id="6066c-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6066c-244">В предыдущих версиях Lync Server при применении изменения к Active Directory администратору потребуется выполнить командлеты **Update-ксусердатабасе** и **Update — ксаддрессбук** Windows PowerShell, чтобы сохранить изменения на сервере Lync. база данных пользователей и база данных Рткаб немедленно.</span><span class="sxs-lookup"><span data-stu-id="6066c-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="6066c-245">В Lync Server 2013 служба репликатора пользователей Lync Server выберет изменения из Active Directory и обновит базу данных пользователей Lync Server на основе заданного интервала.</span><span class="sxs-lookup"><span data-stu-id="6066c-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="6066c-246">Служба репликации пользователей Lync Server также будет автоматически распространять изменения базы данных Рткаб, не требуя администратора запускать Update-Ксаддрессбук.</span><span class="sxs-lookup"><span data-stu-id="6066c-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="6066c-247">Если включен веб-запрос на адресную книгу, изменения будут отражены в результатах поиска клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="6066c-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="6066c-248">Администраторам потребуется выполнить Update-Ксаддрессбук только в том случае, если разрешена загрузка файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6066c-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6066c-249">По умолчанию репликатор пользователей Lync Server запускается автоматически каждые 5 минут.</span><span class="sxs-lookup"><span data-stu-id="6066c-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="6066c-250">Этот интервал можно настроить с помощью Set-Ксусеррепликаторконфигуратион-Репликатионциклеинтервал &lt; &gt;.</span><span class="sxs-lookup"><span data-stu-id="6066c-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="6066c-251">Фильтрация адресной книги</span><span class="sxs-lookup"><span data-stu-id="6066c-251">Filtering the Address Book</span></span>

<span data-ttu-id="6066c-252">Пользователи, заполненные в серверной адресной книге, могут управляться с учетом определенных атрибутов доменных служб Active Directory, перечисленных в таблице Абаттрибуте.</span><span class="sxs-lookup"><span data-stu-id="6066c-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="6066c-253">Один из таких атрибутов, используемых для фильтрации, — это атрибут **мсексчанжехидефромаддрессбук** .</span><span class="sxs-lookup"><span data-stu-id="6066c-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="6066c-254">Это пользовательский атрибут, добавляемый в схему Exchange.</span><span class="sxs-lookup"><span data-stu-id="6066c-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="6066c-255">Если значение этого атрибута равно TRUE, сервер Exchange Server использует этот атрибут для скрытия контакта из глобального списка адресов Outlook (GAL).</span><span class="sxs-lookup"><span data-stu-id="6066c-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="6066c-256">Аналогичным образом, если значение этого атрибута — TRUE, то репликатор пользователей не включит этого пользователя в таблицу Абусерентри, и этот пользователь не будет находиться в файле адресной книги сервера.</span><span class="sxs-lookup"><span data-stu-id="6066c-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="6066c-257">Вы можете использовать несколько битов флагов, чтобы определить фильтр для использования в атрибутах сервера адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6066c-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="6066c-258">Например, наличие определенных битов флагов может определять атрибут как атрибут Include или атрибут Exclude.</span><span class="sxs-lookup"><span data-stu-id="6066c-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="6066c-259">Репликатор пользователей отфильтровывает контакты, которые содержат атрибут Exclude и отфильтровывает, что не содержит атрибут Include.</span><span class="sxs-lookup"><span data-stu-id="6066c-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6066c-260">Дополнительные сведения о том, как отфильтровать адресную книгу, приведены <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">в разделе Командлеты сервера адресной книги в Lync Server 2013</A>и фильтрация записной <A href="http://go.microsoft.com/fwlink/?linkid=330430">книжки Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="6066c-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="6066c-261">В настоящее время есть три разных фильтра.</span><span class="sxs-lookup"><span data-stu-id="6066c-261">Currently, there are three different filters.</span></span> <span data-ttu-id="6066c-262">Эти фильтры перечислены в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="6066c-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6066c-263">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6066c-263">Attribute</span></span></th>
<th><span data-ttu-id="6066c-264">Описание</span><span class="sxs-lookup"><span data-stu-id="6066c-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6066c-265">0x800</span><span class="sxs-lookup"><span data-stu-id="6066c-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="6066c-266">Если этот параметр установлен, он определяет обязательный атрибут для контакта.</span><span class="sxs-lookup"><span data-stu-id="6066c-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="6066c-267">Репликатор пользователей использует этот бит флага, чтобы отфильтровать контакты, которые не содержат хотя бы один обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="6066c-268">Аупасид — обязательный атрибут, который всегда задается.</span><span class="sxs-lookup"><span data-stu-id="6066c-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="6066c-269">По крайней мере один из других обязательных атрибутов должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="6066c-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="6066c-270">В противном случае контакт (то есть со значением требуемого атрибута Аупасид) по-прежнему не будет записываться в базу данных.</span><span class="sxs-lookup"><span data-stu-id="6066c-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="6066c-271">Например, если в качестве обязательных атрибутов определены <strong>telephoneNumber</strong> и <strong>хомефоне</strong> , в базу данных записываются только те контакты, которые имеют по крайней мере один из этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6066c-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6066c-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="6066c-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="6066c-273">Если этот параметр установлен, он определяет атрибут Exclude.</span><span class="sxs-lookup"><span data-stu-id="6066c-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="6066c-274">Репликатор пользователей использует этот бит флага, чтобы отфильтровать контакты, которые содержат этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="6066c-275">Например, если <strong>msRTCSIP-примарюсераддресс</strong> определен как атрибут Exclude, контакты, имеющие этот атрибут, не записываются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="6066c-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6066c-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="6066c-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="6066c-277">Если этот параметр установлен, он определяет атрибут Include.</span><span class="sxs-lookup"><span data-stu-id="6066c-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="6066c-278">Репликатор пользователей использует этот бит флага, чтобы отфильтровать контакты, не содержащие этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="6066c-279">Например, если <strong>msRTCSIP-примарюсераддресс</strong> определен как атрибут Include, в базу данных записываются только те контакты, у которых есть этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="6066c-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6066c-280">Если заданы биты флагов 0x4000 (исключить атрибут) и 0x8000 (include Attribute), бит 0x4000 переопределяет 0x8000 бит и контакт исключен.</span><span class="sxs-lookup"><span data-stu-id="6066c-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="6066c-281">Несмотря на то, что вы можете отфильтровать адресную книгу таким образом, чтобы она включала только некоторых пользователей, ограничение записей не ограничивает возможности других пользователей для связи с отфильтрованными пользователями или для просмотра состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="6066c-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="6066c-282">Пользователи могут находить и отправлять мгновенные сообщения вручную, а также вручную инициировать звонки пользователям, которые не входят в адресную книгу, вводя полное доменное имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="6066c-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="6066c-283">Кроме того, контактные данные пользователя также можно найти в Outlook.</span><span class="sxs-lookup"><span data-stu-id="6066c-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="6066c-284">Несмотря на то, что у вас есть полные записи контактов в записной книжке, вы можете использовать Lync Server для инициирования электронной почты, телефона или корпоративной голосовой связи (то есть если на сервере включена поддержка корпоративных голосовых звонков) с пользователями, которые не настроены для запуска сеанса. Protocol (SIP), в некоторых организациях предпочтительно включать в записную книжку сервера только пользователей с поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="6066c-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="6066c-285">Вы можете отфильтровать адресную книгу, чтобы включить только пользователей с поддержкой SIP, сняв флажок 0x800 \*\*\*\* в столбце flags следующих обязательных атрибутов **: mailNickname**, **telephoneNumber**, **хомефоне**и **Mobile**.</span><span class="sxs-lookup"><span data-stu-id="6066c-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="6066c-286">Вы также можете отфильтровать адресную книгу, чтобы включить только пользователей с поддержкой SIP, задав значение 0x8000 (include) \*\*\*\* в столбце Flags (атрибут **msRTCSIP-примарюсераддресс** ).</span><span class="sxs-lookup"><span data-stu-id="6066c-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="6066c-287">Это также помогает исключить учетные записи служб из файлов из адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6066c-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="6066c-288">После того как вы измените таблицу Абаттрибуте, вы можете обновить данные в таблице Абусерентри, выполнив команду командлет **Update-ксусердатабасе** .</span><span class="sxs-lookup"><span data-stu-id="6066c-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="6066c-289">После завершения репликации UR вы можете обновить файл в хранилище файлов на сервере адресной книги, вручную запустив команду командлета **упдатексаддрессбук** .</span><span class="sxs-lookup"><span data-stu-id="6066c-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6066c-290">Сервер переднего плана, на котором размещен сервер адресной книги, не является административно настраиваемым.</span><span class="sxs-lookup"><span data-stu-id="6066c-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="6066c-291">Он выбирается во время развертывания — обычно это первый сервер переднего плана, на котором развернута.</span><span class="sxs-lookup"><span data-stu-id="6066c-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="6066c-292">В случае сбоя служба адресной книги будет переведена на другой сервер переднего плана и не потребует вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="6066c-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6066c-293">Если вы объединили или изменили инфраструктуру из развертывания с несколькими лесами или родительским и дочерним развертыванием (например, консолидация инфраструктуры перед переходом на Lync Server), возможно, вы обнаружите, что служба адресной книги загружена и Веб-запрос адресной книги для некоторых пользователей завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="6066c-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="6066c-294">Если в развертывании используется несколько доменов или лесов, атрибут <STRONG>MsRTCSIP-оригинаторсид</STRONG> заполняется для объектов пользователей, которые представляют собой неполадку.</span><span class="sxs-lookup"><span data-stu-id="6066c-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="6066c-295">Для устранения этой проблемы атрибут <STRONG>MsRTCSIP-оригинаторсид</STRONG> должен иметь значение NULL для этих объектов.</span><span class="sxs-lookup"><span data-stu-id="6066c-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

