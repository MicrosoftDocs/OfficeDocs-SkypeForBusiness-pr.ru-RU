---
title: Настройка правил ПИН-кодов для конференц-связи с телефонным подключением
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
ms.openlocfilehash: b446d38b3a2a2c054619373a605192ca05886174
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537206"
---
# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="8414d-102">Настройка правил ПИН-кодов для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414d-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8414d-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="8414d-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="8414d-104">Lync Server 2013 пользователи с учетными данными доменных служб Active Directory (AD DS) в организации могут присоединяться к конференциям в качестве пользователей, прошедших проверку подлинности, с помощью персонального идентификационного номера (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="8414d-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="8414d-105">Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="8414d-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="8414d-p102">Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов. Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно. Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой. Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет. Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена. Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="8414d-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8414d-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="8414d-112">In This Section</span></span>

  - [<span data-ttu-id="8414d-113">Изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414d-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="8414d-114">Создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей</span><span class="sxs-lookup"><span data-stu-id="8414d-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="8414d-115">Удаление параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8414d-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

