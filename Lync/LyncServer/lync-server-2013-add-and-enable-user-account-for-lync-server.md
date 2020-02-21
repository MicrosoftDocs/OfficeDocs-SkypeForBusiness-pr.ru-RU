---
title: 'Lync Server 2013: Добавление и включение учетной записи пользователя для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24fe3004f588f50edbcb9428d8bece7a4b20a28a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="52db3-102">Добавление и включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52db3-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52db3-103">_**Последнее изменение темы:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="52db3-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="52db3-104">После включения учетной записи пользователя в оснастке "Active Directory — пользователи и компьютеры" можно использовать панель управления Lync Server для создания и включения новых учетных записей пользователей Lync Server 2013, добавив пользователя Active Directory в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52db3-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="52db3-105">Добавление и включение нового пользователя Lync Server</span><span class="sxs-lookup"><span data-stu-id="52db3-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="52db3-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="52db3-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="52db3-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52db3-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52db3-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52db3-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52db3-109">В левой панели навигации щелкните элемент **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="52db3-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="52db3-110">Щелкните элемент **Enable users** (Разрешить пользователей).</span><span class="sxs-lookup"><span data-stu-id="52db3-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="52db3-111">В диалоговом окне **New Lync Server User** (Новый пользователь Lync Server) нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="52db3-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="52db3-112">В поле **Search users** (Поиск пользователей) полностью или частично введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности, адрес электронной почты, имя участника-пользователя или номер телефона требуемой учетной записи пользователя Active Directory, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="52db3-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="52db3-113">В таблице выберите учетную запись, которую нужно добавить на сервер Lync Server, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="52db3-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="52db3-114">Назначьте пользователя пулу, укажите дополнительные сведения и назначьте пользователю политики, а затем щелкните элемент **Enable** (Разрешить).</span><span class="sxs-lookup"><span data-stu-id="52db3-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52db3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="52db3-115">See Also</span></span>


[<span data-ttu-id="52db3-116">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52db3-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="52db3-117">Удаление учетной записи пользователя из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52db3-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="52db3-118">Включение и отключение пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52db3-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

