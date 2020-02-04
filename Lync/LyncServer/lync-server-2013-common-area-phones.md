---
title: 'Lync Server 2013: общие телефоны с областями'
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
ms.openlocfilehash: 71fa61773a4801d2050d67d4e86458eb5d37759c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="b516f-102">Общие Телефоны на мобильных телефонах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b516f-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b516f-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b516f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b516f-104">Обычные телефоны — это IP-телефоны, не связанные с конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="b516f-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="b516f-105">Вместо того чтобы находились в офисе другого пользователя, обычно они размещаются в здании приемных, кафетериас, мягких для сотрудников, комнатах собраний и в других местах, где часто может быть собрано большое количество людей.</span><span class="sxs-lookup"><span data-stu-id="b516f-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="b516f-106">В отличие от других телефонов в Lync Server, обычно использующих политики голосовой связи и абонентские группы, которым назначены индивидуальные пользователи, для них не могут быть назначены индивидуальные пользователи.</span><span class="sxs-lookup"><span data-stu-id="b516f-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="b516f-107">Это означает, что они должны управляться иначе, чем ваши другие телефоны.</span><span class="sxs-lookup"><span data-stu-id="b516f-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="b516f-108">Чтобы управлять стандартными телефонами, вы создаете объекты контактов доменных служб Active Directory для всех распространенных телефонов, например для учетных записей пользователей, могут назначаться политики и голосовые планы.</span><span class="sxs-lookup"><span data-stu-id="b516f-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="b516f-109">Этот подход позволяет поддерживать контроль над распространенными телефонами, даже если они не связаны с конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="b516f-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="b516f-110">В этом разделе приведены сведения о том, как создавать объекты контактов для обычных телефонов, изменять и удалять их, а также настраивать и просматривать сведения о конфигурации для телефонной сети, используемой в развертывании.</span><span class="sxs-lookup"><span data-stu-id="b516f-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b516f-111">У вас есть три варианта для стационарных телефонов: Aastra 6721ip Common Area Phone, телефонный номер HP 4110 IP и Polycom CX500 IP на стандартном телефоне.</span><span class="sxs-lookup"><span data-stu-id="b516f-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="b516f-112">Телефон конференц-связи по Polycom CX3000 является другим вариантом универсального телефона.</span><span class="sxs-lookup"><span data-stu-id="b516f-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="b516f-113">Однако она предназначена для использования в конференц-залах.</span><span class="sxs-lookup"><span data-stu-id="b516f-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="b516f-114">Подробнее об общих телефонах с областями можно узнать в разделе телефоны в области " <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Выбор новых устройств</A>".</span><span class="sxs-lookup"><span data-stu-id="b516f-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b516f-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="b516f-115">In This Section</span></span>

  - [<span data-ttu-id="b516f-116">Просмотр сведений о стандартном телефоне в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b516f-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="b516f-117">Создание или изменение объекта контактного телефона для общего города в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b516f-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="b516f-118">Включение и отключение функции поддержки горячей замены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b516f-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="b516f-119">Удаление объекта контактного телефона из общей области в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b516f-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="b516f-120">Назначение политик в Lync Server 2013 на стандартном телефоне</span><span class="sxs-lookup"><span data-stu-id="b516f-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

