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
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="39b08-102">Перенос пользователей в единое хранилище контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b08-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b08-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="39b08-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="39b08-104">Пользовательские контакты автоматически переносятся на сервер Exchange 2013, когда пользователь:</span><span class="sxs-lookup"><span data-stu-id="39b08-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="39b08-105">Назначена политика пользовательских служб, у которой Уксалловед установлено значение true.</span><span class="sxs-lookup"><span data-stu-id="39b08-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="39b08-106">Была настроена с помощью почтового ящика Exchange 2013 и один раз вошел в почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="39b08-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="39b08-107">Войдите в систему с помощью клиента Lync 2013 с богатыми возможностями.</span><span class="sxs-lookup"><span data-stu-id="39b08-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="39b08-108">Если пользователь входит в систему с помощью клиента Lync 2010 или более ранней версии или пользователь не подключен к серверу Exchange 2013, политика служб пользователей игнорируется, а контакты пользователя остаются в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39b08-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="39b08-109">Чтобы определить, перенесены ли контакты пользователя, используйте один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="39b08-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="39b08-110">На клиентском компьютере проверьте следующий раздел реестра:</span><span class="sxs-lookup"><span data-stu-id="39b08-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="39b08-111">\_Пользовательское\\программное\\обеспечение\\для\\hKey\\\_Microsoft\\\<Office 15,0\>\\Lync SIP URL UCS</span><span class="sxs-lookup"><span data-stu-id="39b08-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="39b08-112">Если контакты пользователя хранятся в Exchange 2013, в этом разделе содержится значение Инуксмоде со значением 2165.</span><span class="sxs-lookup"><span data-stu-id="39b08-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="39b08-113">Запустите командлет **Test-ксунифиедконтактсторе** .</span><span class="sxs-lookup"><span data-stu-id="39b08-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="39b08-114">В командной строке оболочки Lync Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="39b08-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="39b08-115">Если **тест-ксунифиедконтактсторе** выполняется успешно, контакты пользователя были перенесены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="39b08-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

