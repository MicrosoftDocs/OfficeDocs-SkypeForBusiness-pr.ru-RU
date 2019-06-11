---
title: 'Lync Server 2013: защита IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="a8972-102">Защита IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8972-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8972-103">_**Тема последнего изменения:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="a8972-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="a8972-104">В Microsoft Office Communications Server 2007 и Microsoft Office Communications Server 2007 R2 служба IIS работала под учетной записью обычного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8972-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="a8972-105">Это может привести к возникновению проблем: в случае истечения срока действия пароля вы можете потерять веб-службы, проблему, которая часто сложно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="a8972-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="a8972-106">Чтобы избежать проблем с истекшим сроком действия паролей, Microsoft Lync Server 2013 позволяет создать учетную запись компьютера (на компьютере, который не существует), который может служить субъектом проверки подлинности для всех компьютеров на сайте, на котором запущены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="a8972-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="a8972-107">Поскольку для этих учетных записей применяется протокол проверки подлинности Kerberos, они называются учетными записями Kerberos, а новый процесс проверки подлинности — веб-проверкой подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a8972-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="a8972-108">Таким образом, одна учетная запись обеспечивает управление всеми серверами IIS.</span><span class="sxs-lookup"><span data-stu-id="a8972-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="a8972-109">Чтобы выполнить серверы для этого участника проверки подлинности, необходимо сначала создать учетную запись компьютера с помощью командлета New-Кскерберосаккаунт. Эта учетная запись затем назначается для одного или нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="a8972-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="a8972-110">После создания назначения связь между учетной записью и сайтом Lync Server 2013 будет включена путем запуска командлета Enable-Кстопологи.</span><span class="sxs-lookup"><span data-stu-id="a8972-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="a8972-111">Помимо прочего, в этом случае создается требуемое имя субъекта-службы (SPN) в доменных службах Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a8972-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a8972-112">Имя SPN предоставляет клиентским службам информацию о расположении конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="a8972-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="a8972-113">Подробности можно найти в разделе [New-кскерберосаккаунт](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="a8972-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="a8972-114">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="a8972-114">Best Practices</span></span>

<span data-ttu-id="a8972-115">Для повышения безопасности IIS мы рекомендуем использовать учетную запись Kerberos для IIS.</span><span class="sxs-lookup"><span data-stu-id="a8972-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="a8972-116">Если вы не реализуете учетную запись Kerberos, службы IIS работают под учетной записью обычного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8972-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

