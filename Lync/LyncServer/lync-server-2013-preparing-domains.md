---
title: 'Lync Server 2013: подготовка доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1f5693a14084627d20ae66fa6ec85f6b6c6c6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="7fda0-102">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fda0-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fda0-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7fda0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7fda0-104">Подготовка домена — это заключительный этап подготовки доменных служб Active Directory для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7fda0-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="7fda0-105">На этапе подготовки домена в универсальные группы добавляются необходимые записи управления доступом (ACE), которые предоставляют разрешения для размещения и управления пользователями в домене.</span><span class="sxs-lookup"><span data-stu-id="7fda0-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="7fda0-106">При подготовке домена создаются записи ACE в корне домена и три встроенных контейнера: пользователи, компьютеры и контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="7fda0-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="7fda0-107">Вы можете выполнить подготовку домена на любом компьютере домена, на котором вы развертываете Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fda0-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="7fda0-108">Необходимо подготовить каждый домен, на котором будет размещен сервер Lync Server или пользователи.</span><span class="sxs-lookup"><span data-stu-id="7fda0-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="7fda0-109">Если в вашей организации отключены разрешения на наследование разрешений или аутентификация пользователей, прошедших проверку подлинности, необходимо выполнить дополнительные действия в процессе подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="7fda0-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="7fda0-110">Дополнительные сведения можно найти [в разделе Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="7fda0-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="7fda0-111">Если в вашей организации используются организационные подразделения (OU), а не три встроенных контейнера (например, пользователи, компьютеры и контроллеры домена), необходимо предоставить доступ на чтение к подразделениям для группы пользователей, прошедших проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7fda0-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="7fda0-112">Для подготовки домена требуется доступ на чтение к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="7fda0-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="7fda0-113">Если у группы пользователей, прошедших проверку подлинности, нет доступа на чтение к OU, выполните командлет **Grant-ксаупермиссион** , как показано в приведенных ниже примерах кода, чтобы предоставить разрешения на чтение для каждого подразделения.</span><span class="sxs-lookup"><span data-stu-id="7fda0-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="7fda0-114">Дополнительные сведения о командлете **Grant-ксаупермиссион** можно найти в документации по оболочке Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fda0-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="7fda0-115">Подробнее об ACE, созданных в корне домена и в контейнерах пользователей, компьютеров и контроллеров домена, можно узнать <A href="lync-server-2013-changes-made-by-domain-preparation.md">в статьях изменения подготовки домена в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7fda0-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7fda0-116">Содержание</span><span class="sxs-lookup"><span data-stu-id="7fda0-116">In This Section</span></span>

  - [<span data-ttu-id="7fda0-117">Проведение подготовки домена для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fda0-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="7fda0-118">Использование командлетов для отмены подготовки доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fda0-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

