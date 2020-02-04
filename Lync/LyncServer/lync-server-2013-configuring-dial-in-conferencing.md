---
title: 'Lync Server 2013: настройка конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d722abaf76ef915b7587039cb7732cb281a06308
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="bdc9e-102">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc9e-103">_**Тема последнего изменения:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="bdc9e-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="bdc9e-104">В этом разделе рассказывается, как настроить Конференц-связь с телефонным подключением в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdc9e-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bdc9e-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="bdc9e-105">In This Section</span></span>

  - [<span data-ttu-id="bdc9e-106">Необходимые условия и разрешения для настройки конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="bdc9e-107">Контрольный список развертывания для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="bdc9e-108">Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="bdc9e-109">Проверка абонентских планов Lync Server 2013 назначенные регионы</span><span class="sxs-lookup"><span data-stu-id="bdc9e-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="bdc9e-110">Проверка параметров политики ПИН-кодов в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="bdc9e-111">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="bdc9e-112">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="bdc9e-113">Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="bdc9e-114">Изменение назначенных клавиш для команд DTMF в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="bdc9e-115">Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="bdc9e-116">Проверка конференц-связи с телефонным подключением в Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="bdc9e-117">Развертывание надстройки собраний по сети для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="bdc9e-118">Настройка параметров учетных записей пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="bdc9e-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="bdc9e-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="bdc9e-120">Приветствие пользователей в конференции с телефонным подключением Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bdc9e-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="bdc9e-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bdc9e-121">Related Sections</span></span>

[<span data-ttu-id="bdc9e-122">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdc9e-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

