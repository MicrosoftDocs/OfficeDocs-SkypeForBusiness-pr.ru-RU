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
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="d1265-102">Удаление учетной записи пользователя из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1265-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1265-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d1265-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d1265-104">Для удаления ранее добавленной учетной записи пользователя в Lync Server 2013 можно использовать описанную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="d1265-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1265-105">Удаление пользователя приведет к потере всех параметров, настроенных для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="d1265-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="d1265-106">Если вы хотите временно отключить учетную запись пользователя, ознакомьтесь с разделом <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1265-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="d1265-107">Удаление учетной записи пользователя с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d1265-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="d1265-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d1265-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1265-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1265-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1265-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1265-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1265-111">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d1265-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d1265-112">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить снова, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="d1265-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d1265-113">В таблице выберите учетную запись пользователя, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="d1265-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="d1265-114">В меню **действия** выберите команду **удалить из Lync Server**, и появится диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d1265-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="d1265-115">В диалоговом окне нажмите кнопку **ОК** , чтобы удалить пользователя.</span><span class="sxs-lookup"><span data-stu-id="d1265-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d1265-116">Удаление учетных записей пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1265-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d1265-117">Вы можете удалить учетные записи пользователей с помощью командлета Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="d1265-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="d1265-118">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1265-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="d1265-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1265-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="d1265-120">Удаление учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d1265-120">To remove a user account</span></span>

  - <span data-ttu-id="d1265-121">Чтобы удалить учетную запись пользователя, используйте командлет Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="d1265-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="d1265-122">Например:</span><span class="sxs-lookup"><span data-stu-id="d1265-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="d1265-123">После запуска этой команды вы не сможете повторно активировать учетную запись и ее предыдущие параметры.</span><span class="sxs-lookup"><span data-stu-id="d1265-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="d1265-124">Вместо этого, чтобы создать новую учетную запись для Кен мер, вам нужно будет использовать командлет Enable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="d1265-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="d1265-125">Дополнительные сведения можно найти в разделе справки по командлету [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="d1265-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1265-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d1265-126">See Also</span></span>


[<span data-ttu-id="d1265-127">Отключение и повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1265-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="d1265-128">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1265-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

