---
title: 'Lync Server 2013: Телефоны с общими областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523238887e8ed5ac7dc45fb05177ae0c5fa9f291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="9561c-102">Телефон общего пользования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9561c-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9561c-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9561c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9561c-104">Телефонные телефоны — это IP-телефоны, которые не связаны с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="9561c-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="9561c-105">Вместо того чтобы разходилось в офисе другого пользователя, обычно они размещаются в зданиях залов, кафетериас, "мягких" сотрудников, комнатах для собраний и других местах, где большое количество людей, скорее всего, собираются.</span><span class="sxs-lookup"><span data-stu-id="9561c-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="9561c-106">В отличие от других телефонов в Lync Server, которые обычно поддерживаются с помощью политик голосовой связи и абонентских абонентов, назначенных отдельным пользователям, им не назначены индивидуальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="9561c-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="9561c-107">Это означает, что они должны управляться не так, как другие телефоны.</span><span class="sxs-lookup"><span data-stu-id="9561c-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="9561c-108">Для управления телефонами на общих телефонах вы создаете контактные объекты доменных служб Active Directory для всех общедоступных телефонов, например учетных записей пользователей, могут быть назначены политики и голосовые планы.</span><span class="sxs-lookup"><span data-stu-id="9561c-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="9561c-109">Такой подход позволяет поддерживать управление телефонными телефонами, несмотря на то, что эти телефоны не связаны с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="9561c-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="9561c-110">Используйте подразделы этого раздела, чтобы узнать, как создавать объекты контактов для общедоступных телефонов, изменять и удалять их, а также настраивать и просматривать сведения о конфигурации телефонной сети, используемой в развертывании.</span><span class="sxs-lookup"><span data-stu-id="9561c-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9561c-111">У вас есть три варианта для телефонов с общими областями: Aastra 6721ip, общий телефонный номер, HP 4110 IP-телефон и Polycom CX500 IP на общем телефоне.</span><span class="sxs-lookup"><span data-stu-id="9561c-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="9561c-112">Телефон конференц-связи Polycom CX3000 — это еще один вариант телефона.</span><span class="sxs-lookup"><span data-stu-id="9561c-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="9561c-113">Однако она предназначена для использования в конференц-залах.</span><span class="sxs-lookup"><span data-stu-id="9561c-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="9561c-114">Сведения о телефонах на общих участках можно найти в разделе Phone Phone phones of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">New Devices</A>.</span><span class="sxs-lookup"><span data-stu-id="9561c-114">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9561c-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="9561c-115">In This Section</span></span>

  - [<span data-ttu-id="9561c-116">Просмотр сведений о телефонах общей области в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9561c-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="9561c-117">Создание или изменение объекта контактного телефона общего пользования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9561c-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="9561c-118">Включение и отключение функции "горячая" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9561c-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="9561c-119">Удаление объекта контактного телефона общего пользования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9561c-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="9561c-120">Назначение политик в Lync Server 2013 на телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="9561c-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

