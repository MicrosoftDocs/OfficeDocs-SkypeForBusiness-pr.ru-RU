---
title: 'Lync Server 2013: Настройка конференц-связи с телефонным подключением'
description: 'Lync Server 2013: Настройка конференц-связи с телефонным подключением.'
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
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557945"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fb93b-103">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb93b-104">_**Последнее изменение темы:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="fb93b-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="fb93b-105">В этом разделе описывается настройка конференц-связи с телефонным подключением Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb93b-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb93b-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="fb93b-106">In This Section</span></span>

  - [<span data-ttu-id="fb93b-107">Необходимые условия и разрешения для настройки конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="fb93b-108">Контрольный список развертывания для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="fb93b-109">Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="fb93b-110">Убедитесь, что в телефонных планах Lync Server 2013 назначены регионы</span><span class="sxs-lookup"><span data-stu-id="fb93b-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="fb93b-111">Необязательно Проверка параметров политики ПИН-кода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="fb93b-112">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="fb93b-113">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="fb93b-114">Необязательно Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="fb93b-115">Необязательно Изменение сопоставления клавиш для команд DTMF в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="fb93b-116">Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="fb93b-117">Необязательно Проверка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="fb93b-118">Развертывание надстройки собраний по сети для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="fb93b-119">Настройка параметров учетных записей пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="fb93b-120">Предложен Создание каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="fb93b-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="fb93b-121">Необязательно Добро пожаловать в Конференц-связь с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="fb93b-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fb93b-122">Related Sections</span></span>

[<span data-ttu-id="fb93b-123">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb93b-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

