---
title: Членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="1330c-102">Членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1330c-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1330c-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1330c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1330c-p101">Для успешного запуска анализатора соответствия рекомендациям используемая для входа учетная запись должна являться членом группы администраторов на локальном компьютере. Кроме того, для сканирования среды эта учетная запись пользователя должна быть членом следующих групп:</span><span class="sxs-lookup"><span data-stu-id="1330c-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="1330c-106">**Администраторы домена**   для перечисления сведений о доменных службах Active Directory и для вызова поставщиков инструментария управления Windows (WMI) на контроллерах домена и серверах глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="1330c-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="1330c-107">**Администраторы**   , необходимые для каждого внутреннего компьютера Lync Server 2013 и каждый пограничный сервер для вызова поставщиков инструментария управления Windows (WMI) и доступа к реестру.</span><span class="sxs-lookup"><span data-stu-id="1330c-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="1330c-108">**RTCUniversalReadOnlyAdmins**   полный или делегированный доступ только для чтения Lync Server 2013 административные права.</span><span class="sxs-lookup"><span data-stu-id="1330c-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="1330c-109">**Только администратор Exchange с правами администратора**   только для просмотра или делегированного администратора в организации Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="1330c-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="1330c-110">Если ваша учетная запись пользователя не обладает достаточными правами, возможны два варианта:</span><span class="sxs-lookup"><span data-stu-id="1330c-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="1330c-111">Выполните команду **runas** в командной строке, чтобы запустить средство под учетной записью с достаточными правами.</span><span class="sxs-lookup"><span data-stu-id="1330c-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="1330c-112">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1330c-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="1330c-113">На странице **Подключение к Active Directory** задайте учетные данные для учетных записей, которые планируете использовать для запуска анализатора соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="1330c-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="1330c-114">Щелкните элемент **Показать дополнительные варианты входа**.</span><span class="sxs-lookup"><span data-stu-id="1330c-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="1330c-115">Вы можете ввести три учетные записи: один для подключения к доменным службам Active Directory, один для подключения к пограничным серверам Lync Server 2013 и один для подключения к серверам Exchange.</span><span class="sxs-lookup"><span data-stu-id="1330c-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="1330c-116">Если вы не указываете какую-либо из этих учетных записей, используется та учетная запись, с помощью которой вы выполнили вход и запустили анализатор соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="1330c-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

