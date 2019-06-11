---
title: 'Lync Server 2013: политики конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="15cc5-102">Политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cc5-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15cc5-103">_**Тема последнего изменения:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="15cc5-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="15cc5-104">Политика конференц-связи определяет возможности и возможности, которые пользователи смогут использовать во время конференции (также называемой собранием).</span><span class="sxs-lookup"><span data-stu-id="15cc5-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="15cc5-105">Настройки политики конференц-связи охватывают широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников.</span><span class="sxs-lookup"><span data-stu-id="15cc5-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="15cc5-106">Администраторы могут использовать политику конференций для управления безопасностью, пропускной способностью и юридическими аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="15cc5-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="15cc5-107">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="15cc5-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="15cc5-108">Параметры применяются к конкретному пользователю от самой узкой до самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="15cc5-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="15cc5-109">При назначении пользователю политики пользователя эти параметры имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="15cc5-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="15cc5-110">Если политика не назначена, применяется политика уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="15cc5-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="15cc5-111">Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="15cc5-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="15cc5-112">Глобальная политика существует по умолчанию, поэтому ее невозможно создать.</span><span class="sxs-lookup"><span data-stu-id="15cc5-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="15cc5-113">Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="15cc5-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="15cc5-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="15cc5-114">In This Section</span></span>

  - [<span data-ttu-id="15cc5-115">Просмотр сведений о политике конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cc5-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="15cc5-116">Создание и изменение политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cc5-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="15cc5-117">Удаление существующей политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cc5-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="15cc5-118">Справочник по параметрам политики конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cc5-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

