---
title: 'Lync Server 2013: настройка проверки подлинности Kerberos'
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
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="e18fd-102">Настройка проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e18fd-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e18fd-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e18fd-104">Lync Server 2013 поддерживает проверку подлинности NTLM и Kerberos для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="e18fd-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="e18fd-105">Office Communications Server 2007 и Office Communications Server 2007 R2 использовали по умолчанию Ртккомпонентсервице и Ртксервице для учетных записей пользователей для запуска пулов приложений веб-служб, позволяя назначить пользователю имя участника службы (SPN). учетные записи и роль участника проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e18fd-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="e18fd-106">Lync Server использует сетевую службу для работы веб-служб и NetworkService не может назначать ей SPN.</span><span class="sxs-lookup"><span data-stu-id="e18fd-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="e18fd-107">Чтобы решить проблему, не позволяющую объектам Active Directory хранить SPN, панель управления Lync Server может использовать объекты учетной записи компьютера для этой цели.</span><span class="sxs-lookup"><span data-stu-id="e18fd-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="e18fd-108">Объекты учетной записи компьютера могут содержать имена участников службы и не могут быть причиной истечения срока действия пароля, которая была связана с использованием учетных записей пользователей в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="e18fd-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="e18fd-109">Вы можете использовать командлеты Windows PowerShell для настройки объектов компьютера для обеспечения проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e18fd-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e18fd-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="e18fd-110">In This Section</span></span>

  - [<span data-ttu-id="e18fd-111">Необходимые условия для включения проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="e18fd-112">Создание учетной записи для проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="e18fd-113">Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="e18fd-114">Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="e18fd-115">Добавление в Lync Server 2013 проверки подлинности Kerberos для других сайтов</span><span class="sxs-lookup"><span data-stu-id="e18fd-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="e18fd-116">В Lync Server 2013 удаление проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="e18fd-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="e18fd-117">Тестирование и отчет о состоянии и назначении проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18fd-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

