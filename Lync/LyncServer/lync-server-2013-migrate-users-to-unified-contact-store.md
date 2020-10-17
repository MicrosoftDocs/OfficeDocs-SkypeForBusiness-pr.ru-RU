---
title: 'Lync Server 2013: перенос пользователей в единое хранилище контактов'
description: 'Lync Server 2013: перенос пользователей в единое хранилище контактов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568595"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="fb20e-103">Миграция пользователей в единое хранилище контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb20e-103">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb20e-104">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="fb20e-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="fb20e-105">Контакты пользователя автоматически переносятся на сервер Exchange 2013 в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="fb20e-105">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="fb20e-106">пользователю назначена политика служб пользователя, где для параметра UcsAllowed установлено значение true;</span><span class="sxs-lookup"><span data-stu-id="fb20e-106">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="fb20e-107">Был подготовлен с помощью почтового ящика Exchange 2013 и выполнил вход по крайней мере один раз в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="fb20e-107">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="fb20e-108">Выполняет вход с помощью полнофункционального клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fb20e-108">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="fb20e-109">Если пользователь входит в систему с помощью клиента Lync 2010 или более ранней версии или если пользователь не подключен к серверу Exchange 2013, политика служб пользователя игнорируется, а контакты пользователя сохраняются в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb20e-109">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="fb20e-110">Можно определить, перенесены ли контакты пользователя, с помощью любого из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="fb20e-110">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="fb20e-111">Проверьте следующий раздел реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="fb20e-111">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="fb20e-112">\_ \_ Программное обеспечение для текущего пользователя hKey \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="fb20e-112">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="fb20e-113">Если контакты пользователя хранятся в Exchange 2013, этот раздел содержит значение параметр inucsmode со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="fb20e-113">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="fb20e-114">Выполните командлет **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="fb20e-114">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="fb20e-115">В командной строке Командная консоль Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="fb20e-115">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="fb20e-116">Если командлет **Test-CsUnifiedContactStore** выполнен успешно, следовательно, выполнен перенос контактов пользователя к единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="fb20e-116">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

