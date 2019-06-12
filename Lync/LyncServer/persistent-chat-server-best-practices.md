---
title: Рекомендации по работе с сервером сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="e9d2d-102">Рекомендации по работе с сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e9d2d-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d2d-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e9d2d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e9d2d-104">По мере создания категорий и сохраненных комнат чатов, а также для оформления областей и членства в них могут помочь следующие советы.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="e9d2d-105">Если в вашей компании не требуется безупречная стенка, не Ограничьте область в дереве категорий.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="e9d2d-106">Наведите всех пользователей в область одной категории и создайте все комнаты чата в этой категории.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="e9d2d-107">Затем вы можете предоставить или ограничить доступ к каждой комнате чата с помощью списков участников.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="e9d2d-108">В большинстве случаев необходимо разрешить пользователям создавать новые комнаты чата, чтобы обсуждения новых тем могли начаться в любое время.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="e9d2d-109">Для этого сделайте список **создателей** таким же, как и в списке **алловедмемберс** .</span><span class="sxs-lookup"><span data-stu-id="e9d2d-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="e9d2d-110">Тем не менее, если вы хотите разрешить создавать комнаты только для Центральной группы поддержки или для определенных пользователей, сделайте список **создателями** подходящим набором.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="e9d2d-111">Присвойте каждому из них полное имя и описание, описывающее, где он подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="e9d2d-112">Поскольку пользователи не видят название категории при использовании комнаты чата, нельзя полагаться на название категории, чтобы помочь пользователям определить предполагаемый форум обсуждений для комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="e9d2d-113">Возможно, потребуется создать настраиваемый рабочий процесс создания комнаты, если у вас есть определенные соглашения об именовании или другие элементы управления доступом или проверки для реализации.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="e9d2d-114">Настройка сохраняемого чата позволяет настроить **румманажементурл** на то, что вы размещаете.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="e9d2d-115">Например, при нажатии кнопки **создать комнату** в клиенте Lync они могут быть перенаправлены в свое собственное решение.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="e9d2d-116">Создавайте разнообразные надстройки, которые помогут вам улучшить взаимодействие комнат чата, приведя другие бизнес-данные в комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="e9d2d-117">Администраторы должны зарегистрировать надстройки, которые должны быть разрешены в системе.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="e9d2d-118">С помощью списка разрешенных надстроек для общения и создателей можно выбрать один из предложенных для них для соответствующих комнат.</span><span class="sxs-lookup"><span data-stu-id="e9d2d-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e9d2d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e9d2d-119">See Also</span></span>


[<span data-ttu-id="e9d2d-120">Управление категориями, чатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9d2d-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

