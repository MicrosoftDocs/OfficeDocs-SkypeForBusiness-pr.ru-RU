---
title: 'Lync Server 2013: политики конференц-связи'
description: 'Lync Server 2013: политики конференц-связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f117cfb077fc24c3e728e208d8bef78cd3284ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542745"
---
# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="5fc64-103">Политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc64-103">Conferencing policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fc64-104">_**Последнее изменение темы:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="5fc64-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="5fc64-p101">Политика конференц-связи определяет функции и возможности, доступные пользователям во время конференции (также называемой собранием). Настройки политики конференц-связи охватывают широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников. Администраторы могут использовать политику конференц-связи для управления безопасностью, пропускной способностью и правовыми аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="5fc64-p101">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting). Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="5fc64-p102">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. Политика уровня пользователя имеет наивысший приоритет. Если политика уровня пользователя не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fc64-p102">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a user policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="5fc64-p103">Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fc64-p103">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5fc64-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="5fc64-115">In This Section</span></span>

  - [<span data-ttu-id="5fc64-116">Просмотр сведений о политике конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc64-116">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="5fc64-117">Создание или изменение политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc64-117">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="5fc64-118">Удаление существующей политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc64-118">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="5fc64-119">Справочник по параметрам политики конференц-связи для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc64-119">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

