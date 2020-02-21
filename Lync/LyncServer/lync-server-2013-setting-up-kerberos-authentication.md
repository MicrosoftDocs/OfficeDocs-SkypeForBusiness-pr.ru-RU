---
title: 'Lync Server 2013: Настройка проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="09ded-102">Настройка проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09ded-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="09ded-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="09ded-104">Lync Server 2013 поддерживает проверку подлинности NTLM и Kerberos для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="09ded-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="09ded-105">Office Communications Server 2007 и Office Communications Server 2007 R2 использовали Ртккомпонентсервице по умолчанию и Ртксервице в качестве учетных записей пользователей для запуска пулов приложений веб-служб, позволяя назначить пользователю имя участника-службы (SPN). учетные записи и служат субъектами проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="09ded-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="09ded-106">Lync Server использует NetworkService для запуска веб-служб, а служба NetworkService не может иметь назначенные имена участников-служб.</span><span class="sxs-lookup"><span data-stu-id="09ded-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="09ded-107">Чтобы устранить проблему, связанную с отсутствием объектов Active Directory для хранения имен участников-служб, в панели управления Lync Server для этой цели можно использовать объекты учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="09ded-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="09ded-108">Эти объекты могут содержать имена субъектов-служб и не имеют пароля с истекающим сроком действия, который затруднял использование учетных записей пользователей в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="09ded-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="09ded-109">Командлеты Windows PowerShell используются для настройки объектов компьютеров, обеспечивающих проверку подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="09ded-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09ded-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="09ded-110">In This Section</span></span>

  - [<span data-ttu-id="09ded-111">Необходимые условия для активации проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="09ded-112">Создание учетной записи проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="09ded-113">Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="09ded-114">Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="09ded-115">В Lync Server 2013 добавить проверку подлинности Kerberos для других сайтов</span><span class="sxs-lookup"><span data-stu-id="09ded-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="09ded-116">В Lync Server 2013 удаление проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="09ded-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="09ded-117">Тестирование и составление отчетов о состоянии и назначении проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ded-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

