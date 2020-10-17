---
title: Рекомендации по работе с сервером сохраняемого чата
description: Рекомендации по работе с сервером сохраняемого чата.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571265"
---
# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="0b8f7-103">Рекомендации по работе с сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="0b8f7-103">Persistent Chat Server best practices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b8f7-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0b8f7-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0b8f7-105">При создании категорий и комнат сохраняемого чата, а также при проектировании областей и членства следующие советы помогут вам в планировании:</span><span class="sxs-lookup"><span data-stu-id="0b8f7-105">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="0b8f7-p101">Если в организации не требуется создавать ограничение в соответствии с корпоративными стандартами, не сужайте область в дереве категорий. Поместите всех пользователей в области в одну категорию и создайте все чаты в этой категории. Затем используйте списки членства для предоставления или ограничения доступа к каждому чату.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-p101">If your company does not require an ethical wall, do not narrow the scope in your category tree. Put all your users in the scope of one category, and create all chat rooms in that category. Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="0b8f7-p102">В большинстве случаев требуется разрешить пользователям создание новых чатов, чтобы они могли начать обсуждение новых тем в любой момент. Это можно сделать, настроив список **Creators** так, чтобы его содержимое совпадало со списком **AllowedMembers**. Однако, если требуется, чтобы только центральная служба поддержки или назначенные пользователи могли создавать чаты, настройте список **Creators** как соответствующее подмножество.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-p102">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time. Do this by making the **Creators** list the same as the **AllowedMembers** list. However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="0b8f7-p103">Задайте для каждого чата полное имя и краткое описание, определяющее его назначение в организации. Поскольку пользователи не могут видеть имя категории при использовании чата, имя категории не поможет пользователям определить нужный форум для чата.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-p103">Give each chat room a complete name and description summary that describes where it fits in with your organization. Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="0b8f7-114">Может потребоваться создать настраиваемый рабочий процесс создания чатов при наличии определенных соглашений о наименовании или других средств контроля доступа или проверок, которые требуется внедрить.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-114">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="0b8f7-115">Конфигурация сохраняемого чата позволяет настроить **румманажементурл** для размещения на каком-либо узле.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-115">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="0b8f7-116">Например, если пользователи щелкают элемент **Создание комнаты** в клиенте Lync, они могут быть перенаправлены в ваше пользовательское решение.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-116">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="0b8f7-p105">Создайте различные надстройки, которые помогут улучшить работу с чатами, например, добавляя в них важные бизнес-данные. Администраторы должны зарегистрировать надстройки, которые они хотят разрешить в системе. Руководители и авторы могут выбирать надстройки из представленного списка и связывать их с чатами.</span><span class="sxs-lookup"><span data-stu-id="0b8f7-p105">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms. Administrators must register the add-ins that they want to allow in the system. Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0b8f7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0b8f7-120">See Also</span></span>


[<span data-ttu-id="0b8f7-121">Управление категориями, комнатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b8f7-121">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

