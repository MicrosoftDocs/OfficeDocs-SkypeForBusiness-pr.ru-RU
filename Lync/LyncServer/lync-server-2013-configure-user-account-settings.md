---
title: 'Lync Server 2013: Настройка параметров учетных записей пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b3c8ea077b6dee724d131ea117aa7bf304e114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="f10c6-102">Настройка параметров учетных записей пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f10c6-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f10c6-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f10c6-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f10c6-104">Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="f10c6-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="f10c6-105">Для проверки подлинности необходим URI телефонной **линии** , указанный в учетных записях пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f10c6-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="f10c6-106">В этом разделе описывается назначение **Line URI** (URI линии) отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f10c6-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="f10c6-107">Чтобы назначить **Line URI** (URI линии) нескольким учетным записям пользователей, создайте сценарий, использующий командлет **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="f10c6-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="f10c6-108">Для получения дополнительных сведений об использовании примера сценария для назначения **универсального кода ресурса (URI)** для нескольких учетных записей пользователей, в [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)разделе "Назначение URI строк нескольким пользователям".</span><span class="sxs-lookup"><span data-stu-id="f10c6-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="f10c6-109">Настройка параметров учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="f10c6-109">To configure user account settings</span></span>

1.  <span data-ttu-id="f10c6-110">Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f10c6-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f10c6-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f10c6-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f10c6-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f10c6-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f10c6-113">В панели навигации слева щелкните **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="f10c6-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f10c6-114">В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Add filter** (Добавить фильтр), чтобы задать поля поиска, а затем щелкните **Find** (Поиск).</span><span class="sxs-lookup"><span data-stu-id="f10c6-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="f10c6-115">Дважды щелкните имя пользователя, чтобы открыть диалоговое окно **изменение пользователя Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="f10c6-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="f10c6-116">В разделе **Telephony** (Телефония) введите уникальный нормализованный номер телефона в поле **Line URI** (URI линии) (пример: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="f10c6-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f10c6-117">Вы можете указать <STRONG>URI строки</STRONG> только в том случае, если для параметра <STRONG>Телефония</STRONG> выбрано значение <STRONG>Только с одного ПК на другой</STRONG>, <STRONG>Корпоративная голосовая связь</STRONG>, <STRONG>Удаленное управление звонками</STRONG> или <STRONG>Только удаленное управление звонками</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f10c6-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="f10c6-118">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="f10c6-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

