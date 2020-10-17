---
title: 'Lync Server 2013: развертывание единого хранилища контактов'
description: 'Lync Server 2013: развертывание единого хранилища контактов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 056792d2e4ea66699b276d0d571e83c8a0256483
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557755"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="7a83e-103">Развертывание единого хранилища контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a83e-103">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a83e-104">_**Последнее изменение темы:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="7a83e-104">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="7a83e-105">Для включения единого хранилища контактов в Lync Server 2013 не требуются параметры топологии.</span><span class="sxs-lookup"><span data-stu-id="7a83e-105">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="7a83e-106">Чтобы включить единое хранилище контактов для пользователей, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7a83e-106">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="7a83e-107">Политика единого хранилища контактов включена (по умолчанию — включена).</span><span class="sxs-lookup"><span data-stu-id="7a83e-107">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="7a83e-108">Пользователи входят в состав Lync 2013 по крайней мере один раз.</span><span class="sxs-lookup"><span data-stu-id="7a83e-108">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="7a83e-109">После миграции контактов пользователя, которые автоматически происходят при входе пользователя в Lync 2013, пользователь может получить доступ к своим контактам Lync и управлять ими из Lync 2013, Outlook 2013 или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="7a83e-109">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="7a83e-110">Пользователю не нужно войти в Lync, чтобы управлять своими контактами из Outlook или Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="7a83e-110">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a83e-111">Если пользователь входит в состав Lync 2010 после миграции, контакты и группы доступны и актуальны, но пользователь не может управлять (то есть добавлять, удалять, перемещать, помечать, унтаг или изменять) эти контакты.</span><span class="sxs-lookup"><span data-stu-id="7a83e-111">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a83e-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="7a83e-112">In This Section</span></span>

  - [<span data-ttu-id="7a83e-113">Включение пользователей для единого хранилища контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a83e-113">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="7a83e-114">Миграция пользователей в единое хранилище контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a83e-114">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="7a83e-115">Откат перенесенных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a83e-115">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

