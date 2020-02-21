---
title: 'Lync Server 2013: Настройка абонентских планов для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="9fdc3-102">Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdc3-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fdc3-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9fdc3-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9fdc3-p101">При развертывании конференц-связи с телефонным подключением требуется создать или изменить одну абонентскую группу или несколько таких групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением. Убедитесь, что хотя бы одно правило нормализации в каждой абонентской группе преобразует добавочные номера в полные номера телефонов в формате E.164. Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона. Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, поэтому пользователи могут проходить проверку подлинности только с помощью добавочного номера.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="9fdc3-108">Чтобы настроить абонентские группы для конференц-связи с телефонным подключением, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9fdc3-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="9fdc3-109">Независимо от того, развернута ли корпоративная голосовая связь, измените глобальную абонентскую систему, чтобы добавить регион конференц-связи с телефонным подключением, и убедитесь, что правило нормализации правильно преобразует номера доступа с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="9fdc3-110">Подробные инструкции приведены в разделе [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="9fdc3-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="9fdc3-111">Если вы не разрешили развертывание корпоративной голосовой связи, создайте абонентские группы для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="9fdc3-112">Не забудьте добавить регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="9fdc3-113">Подробные инструкции приведены в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="9fdc3-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="9fdc3-114">Если вы развернули корпоративную голосовую связь, измените корпоративные абонентские группы, как необходимо, чтобы включить области и использовать соответствующие правила нормализации для номеров доступа по телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="9fdc3-115">Подробные инструкции приведены в разделе [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="9fdc3-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="9fdc3-116">Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9fdc3-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="9fdc3-117">Подробные инструкции приведены в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="9fdc3-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="9fdc3-118">Для получения дополнительных сведений о регионах, посвященных планированию, ознакомьтесь с [требованиями к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) .</span><span class="sxs-lookup"><span data-stu-id="9fdc3-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9fdc3-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="9fdc3-119">In This Section</span></span>

  - [<span data-ttu-id="9fdc3-120">Просмотр сведений о абонентской схеме в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdc3-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="9fdc3-121">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdc3-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="9fdc3-122">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdc3-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="9fdc3-123">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdc3-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

