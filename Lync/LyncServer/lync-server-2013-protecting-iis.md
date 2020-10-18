---
title: 'Lync Server 2013: защита IIS'
description: 'Lync Server 2013: защита IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51161f221c7235aad04850fdccc5d5e9db5cb579
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579735"
---
# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="7aa8a-103">Защита служб IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa8a-103">Protecting IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa8a-104">_**Последнее изменение темы:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="7aa8a-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="7aa8a-105">В Microsoft Office Communications Server 2007 и Microsoft Office Communications Server 2007 R2 службы IIS выполнялись от имени стандартной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-105">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="7aa8a-106">Это может привести к возникновению проблем: в случае истечения срока действия пароля можно потерять веб-службы, что часто трудно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-106">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="7aa8a-107">Чтобы избежать проблем с истекшим сроком действия паролей, Microsoft Lync Server 2013 позволяет создать учетную запись компьютера (для компьютера, который не существует), который может выступать в качестве субъекта проверки подлинности для всех компьютеров сайта, на котором запущены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-107">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="7aa8a-108">Так как эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи называются учетными записями Kerberos, а новый процесс проверки подлинности называется проверкой подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-108">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="7aa8a-109">Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-109">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="7aa8a-110">Для запуска серверов под этим субъектом проверки подлинности необходимо сначала создать учетную запись компьютера с помощью командлета New-CsKerberosAccount; Затем эта учетная запись назначается одному или нескольким сайтам.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-110">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="7aa8a-111">После выполнения назначения связь между учетной записью и сайтом Lync Server 2013 включается с помощью командлета Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-111">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="7aa8a-112">Помимо прочего, при этом создается имя участника-службы (SPN) в доменных службах Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7aa8a-112">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7aa8a-113">Имена субъектов-служб предоставляют клиентским приложениям способ для обнаружения конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-113">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="7aa8a-114">Дополнительные сведения см. в статье [New – CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-114">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="7aa8a-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7aa8a-115">Best Practices</span></span>

<span data-ttu-id="7aa8a-116">Для повышения безопасности IIS рекомендуется реализовать учетную запись Kerberos для служб IIS.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-116">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="7aa8a-117">Если вы не реализуете учетную запись Kerberos, службы IIS выполняются с использованием стандартной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-117">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

