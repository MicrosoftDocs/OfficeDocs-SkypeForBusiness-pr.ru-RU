---
title: 'Lync Server 2013: перенос пользователей в единое хранилище контактов'
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
ms.openlocfilehash: 09897effe252f49eda73fea567d9b54bdc8ad52a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="a14e5-102">Миграция пользователей в единое хранилище контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14e5-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a14e5-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a14e5-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a14e5-104">Контакты пользователя автоматически переносятся на сервер Exchange 2013 в следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="a14e5-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="a14e5-105">пользователю назначена политика служб пользователя, где для параметра UcsAllowed установлено значение true;</span><span class="sxs-lookup"><span data-stu-id="a14e5-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="a14e5-106">Был подготовлен с помощью почтового ящика Exchange 2013 и выполнил вход по крайней мере один раз в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a14e5-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="a14e5-107">Выполняет вход с помощью полнофункционального клиента Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a14e5-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="a14e5-108">Если пользователь входит в систему с помощью клиента Lync 2010 или более ранней версии или если пользователь не подключен к серверу Exchange 2013, политика служб пользователя игнорируется, а контакты пользователя сохраняются в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a14e5-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="a14e5-109">Можно определить, перенесены ли контакты пользователя, с помощью любого из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="a14e5-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="a14e5-110">Проверьте следующий раздел реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="a14e5-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="a14e5-111">Программное\_обеспечение\\\\для текущего\\пользователя\\hKey\\\_Microsoft\\\<Office 15,0\>\\Lync SIP URL-адрес UCS</span><span class="sxs-lookup"><span data-stu-id="a14e5-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="a14e5-112">Если контакты пользователя хранятся в Exchange 2013, этот раздел содержит значение параметр inucsmode со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="a14e5-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="a14e5-113">Выполните командлет **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="a14e5-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="a14e5-114">В командной строке Командная консоль Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="a14e5-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="a14e5-115">Если командлет **Test-CsUnifiedContactStore** выполнен успешно, следовательно, выполнен перенос контактов пользователя к единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="a14e5-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

