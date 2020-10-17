---
title: 'Lync Server 2013: Удаление учетной записи пользователя из Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782077cc532dc751076d3152467de865fe799a29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536516"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="c69d4-102">Удаление учетной записи пользователя из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69d4-102">Remove a user account from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c69d4-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c69d4-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c69d4-104">Для удаления ранее добавленной учетной записи пользователя в Lync Server 2013 можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="c69d4-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c69d4-105">При удалении пользователя будут удалены все параметры, настроенные для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c69d4-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="c69d4-106">Если вместо этого вы хотите временно отключить учетную запись пользователя, ознакомьтесь с разделом <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c69d4-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="c69d4-107">Удаление учетной записи пользователя с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="c69d4-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="c69d4-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c69d4-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c69d4-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c69d4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c69d4-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c69d4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c69d4-111">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="c69d4-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c69d4-112">В поле **Поиск пользователей** введите полностью или только первую часть отображаемого имени, имени, фамилии, имени учетной записи диспетчера учетных записей безопасности (SAM), адреса SIP или строки универсального кода ресурса (URI) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="c69d4-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="c69d4-113">В таблице щелкните учетную запись пользователя, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c69d4-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="c69d4-114">В меню **Макрокоманда** выберите команду **Удалить с сервера Lync Server**; откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="c69d4-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="c69d4-115">В этом диалоговом окне нажмите кнопку **ОК** для удаления пользователя.</span><span class="sxs-lookup"><span data-stu-id="c69d4-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c69d4-116">Удаление учетных записей пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c69d4-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c69d4-117">Удалить учетные записи пользователей можно с помощью командлета Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="c69d4-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="c69d4-118">Этот командлет можно запустить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c69d4-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="c69d4-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c69d4-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="c69d4-120">Удаление учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="c69d4-120">To remove a user account</span></span>

  - <span data-ttu-id="c69d4-p104">Для удаления учетной записи пользователя используйте командлет Disable-CsUser. Пример:</span><span class="sxs-lookup"><span data-stu-id="c69d4-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="c69d4-p105">После завершения выполнения этой команды повторная активация учетной записи и ее предыдущих параметров невозможна. Вместо этого потребуется создать новую учетную запись для пользователя Ken Myer с помощью командлета Enable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="c69d4-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="c69d4-125">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Disable – CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="c69d4-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c69d4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c69d4-126">See Also</span></span>


[<span data-ttu-id="c69d4-127">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69d4-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="c69d4-128">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c69d4-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

