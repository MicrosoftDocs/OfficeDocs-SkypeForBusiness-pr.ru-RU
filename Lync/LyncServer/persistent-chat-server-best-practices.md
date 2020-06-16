---
title: Рекомендации по работе с сервером сохраняемого чата
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
ms.openlocfilehash: ebe9742b76ec6abfd7b7407f38edda937bdf6ecc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="abc7b-102">Рекомендации по работе с сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abc7b-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc7b-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="abc7b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="abc7b-104">При создании категорий и комнат сохраняемого чата, а также при проектировании областей и членства следующие советы помогут вам в планировании:</span><span class="sxs-lookup"><span data-stu-id="abc7b-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="abc7b-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span><span class="sxs-lookup"><span data-stu-id="abc7b-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="abc7b-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span><span class="sxs-lookup"><span data-stu-id="abc7b-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="abc7b-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span><span class="sxs-lookup"><span data-stu-id="abc7b-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="abc7b-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span><span class="sxs-lookup"><span data-stu-id="abc7b-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="abc7b-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span><span class="sxs-lookup"><span data-stu-id="abc7b-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="abc7b-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span><span class="sxs-lookup"><span data-stu-id="abc7b-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="abc7b-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span><span class="sxs-lookup"><span data-stu-id="abc7b-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="abc7b-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span><span class="sxs-lookup"><span data-stu-id="abc7b-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="abc7b-113">Может потребоваться создать настраиваемый рабочий процесс создания чатов при наличии определенных соглашений о наименовании или других средств контроля доступа или проверок, которые требуется внедрить.</span><span class="sxs-lookup"><span data-stu-id="abc7b-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="abc7b-114">Конфигурация сохраняемого чата позволяет настроить **румманажементурл** для размещения на каком-либо узле.</span><span class="sxs-lookup"><span data-stu-id="abc7b-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="abc7b-115">Например, если пользователи щелкают элемент **Создание комнаты** в клиенте Lync, они могут быть перенаправлены в ваше пользовательское решение.</span><span class="sxs-lookup"><span data-stu-id="abc7b-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="abc7b-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span><span class="sxs-lookup"><span data-stu-id="abc7b-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="abc7b-117">Administrators must register the add-ins that they want to allow in the system.</span><span class="sxs-lookup"><span data-stu-id="abc7b-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="abc7b-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span><span class="sxs-lookup"><span data-stu-id="abc7b-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="abc7b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="abc7b-119">See Also</span></span>


[<span data-ttu-id="abc7b-120">Управление категориями, комнатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc7b-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

