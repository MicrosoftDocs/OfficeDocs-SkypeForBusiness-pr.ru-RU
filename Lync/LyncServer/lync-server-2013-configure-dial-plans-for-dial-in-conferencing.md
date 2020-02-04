---
title: 'Lync Server 2013: настройка абонентских групп для конференц-связи с телефонным подключением'
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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="7f417-102">Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f417-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f417-103">_**Тема последнего изменения:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="7f417-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="7f417-104">При развертывании конференц-связи с телефонным подключением необходимо создать или изменить одну или несколько абонентских групп для маршрутизации номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="7f417-105">Убедитесь, что по крайней мере одно правило нормализации в каждой абонентской группе преобразует телефонные расширения в полные телефонные номера в формате E. 164.</span><span class="sxs-lookup"><span data-stu-id="7f417-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="7f417-106">Пользователи конференц-связи с телефонным подключением присоединяются к конференциям в качестве пользователей предприятия, прошедших проверку подлинности, путем ввода ПИН-кода и номера телефона.</span><span class="sxs-lookup"><span data-stu-id="7f417-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="7f417-107">Для преобразования добавочных номеров в полные номера телефонов требуется правило нормализации, чтобы пользователи могли для прохождения проверки подлинности вводить только добавочный номер.</span><span class="sxs-lookup"><span data-stu-id="7f417-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="7f417-108">Чтобы настроить абонентские группы для конференц-связи с телефонным подключением, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7f417-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="7f417-109">Независимо от того, развертываете ли вы корпоративную голосовую связь, добавьте в глобальную абонентскую группу регион конференц-связи с телефонным подключением и убедитесь, что правило нормализации правильно преобразует номера доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="7f417-110">Подробные инструкции можно найти [в разделе Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7f417-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="7f417-111">Если развертывание корпоративной голосовой связь не планируется, то создайте абонентские группы для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="7f417-112">Не забудьте добавить регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="7f417-113">Подробные инструкции можно найти [в разделе Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7f417-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="7f417-114">Если вы развернули корпоративную голосовую связь, добавьте в ее абонентские группы регионы и используйте соответствующие правила нормализации для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="7f417-115">Подробные инструкции можно найти [в разделе Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7f417-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="7f417-116">Кроме того, вы также можете создать выделенные абонентские группы, которые используются только для номеров доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7f417-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="7f417-117">Подробные инструкции можно найти [в разделе Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7f417-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="7f417-118">Подробнее о регионах планирования можно узнать [в разделе Требования к конференциям с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7f417-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f417-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="7f417-119">In This Section</span></span>

  - [<span data-ttu-id="7f417-120">Просмотр сведений о абонентской схеме в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f417-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="7f417-121">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f417-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="7f417-122">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f417-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="7f417-123">Определение правил нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f417-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

