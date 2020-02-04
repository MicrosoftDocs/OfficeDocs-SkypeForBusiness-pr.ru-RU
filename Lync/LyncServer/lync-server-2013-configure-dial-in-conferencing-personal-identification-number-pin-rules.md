---
title: Настройка правил для личного идентификационного номера конференц-связи с телефонным подключением (PIN)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aef41f14b37d2a21fa747bb14132bd6e9ba93ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="facca-102">Настройка правил для личного идентификационного номера конференц-связи с телефонным подключением (PIN) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="facca-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="facca-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="facca-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="facca-104">Пользователи Lync Server 2013, у которых есть учетные данные доменных служб Active Directory (AD DS) в вашей организации, могут присоединяться к конференциям в сети для пользователей с проверкой подлинности, используя персональный идентификационный номер (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="facca-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="facca-105">Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="facca-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="facca-106">Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="facca-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="facca-107">Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно.</span><span class="sxs-lookup"><span data-stu-id="facca-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="facca-108">Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой.</span><span class="sxs-lookup"><span data-stu-id="facca-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="facca-109">Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="facca-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="facca-110">Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена.</span><span class="sxs-lookup"><span data-stu-id="facca-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="facca-111">Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="facca-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="facca-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="facca-112">In This Section</span></span>

  - [<span data-ttu-id="facca-113">Изменение параметров ПИН-кодов по умолчанию для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="facca-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="facca-114">оздание или изменение параметров ПИН-кода для конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей</span><span class="sxs-lookup"><span data-stu-id="facca-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="facca-115">Удаление параметров контакта конференц-связи с телефонным подключением для сайта или группы пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="facca-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

