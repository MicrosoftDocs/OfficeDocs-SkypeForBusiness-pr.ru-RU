---
title: Участники групп и требования к правам пользователей для анализатора соответствия рекомендациям
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="710ae-102">Участие в группах и требования к правам пользователей для анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="710ae-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="710ae-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="710ae-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="710ae-104">Для успешного выполнения анализатора соответствия рекомендациям учетной записи пользователя, которую вы используете для входа, необходимо быть членом группы "Администраторы" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="710ae-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="710ae-105">Кроме того, для проверки среды учетной записи пользователя необходимо быть участником следующих групп:</span><span class="sxs-lookup"><span data-stu-id="710ae-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="710ae-106">**Администраторы домена**   для перечисления данных доменных служб Active Directory и вызова поставщиков WMI (инструментарий управления Windows) на контроллерах домена и серверах глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="710ae-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="710ae-107">**Администраторы**   , необходимые для каждого внутреннего компьютера Lync Server 2013 и каждый пограничный сервер, должны вызывать поставщики инструментария управления Windows (WMI) и получать доступ к реестру.</span><span class="sxs-lookup"><span data-stu-id="710ae-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="710ae-108">**Рткуниверсалреадонлядминс**   полный или делегированный доступ только для чтения, права администратора Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="710ae-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="710ae-109">**Exchange View только администратор**   с полным или делегированным Exchange View — только администратор в организации Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="710ae-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="710ae-110">Если учетная запись пользователя не имеет достаточных прав пользователя, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="710ae-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="710ae-111">В командной строке используйте команду **runas** для запуска средства под учетной записью, имеющей достаточно прав пользователя.</span><span class="sxs-lookup"><span data-stu-id="710ae-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="710ae-112">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="710ae-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="710ae-113">На странице **Подключение к Active Directory** задайте учетные данные для учетных записей, которые планируется использовать для проведения анализатора соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="710ae-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="710ae-114">Щелкните **Показать расширенные параметры входа**.</span><span class="sxs-lookup"><span data-stu-id="710ae-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="710ae-115">Вы можете ввести три учетные записи: для подключения к доменным службам Active Directory, для подключения к серверам Lync Server 2013 EDGE и для подключения к серверам Exchange.</span><span class="sxs-lookup"><span data-stu-id="710ae-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="710ae-116">Если вы не указали ни одну из этих учетных записей, используется учетная запись пользователя, который использовался для входа в систему и запуска анализатора соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="710ae-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

