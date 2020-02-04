---
title: Создание фильтра URL-адресов для обработки гиперссылок в текстовых беседах
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="6bf1e-102">Создание фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="6bf1e-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf1e-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6bf1e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6bf1e-104">Помимо изменения глобального фильтра URL-адреса вы можете настроить пользовательские фильтры URL-адресов для отдельных сайтов в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="6bf1e-105">Подробнее об фильтрации URL-адресов можно узнать [в разделе Настройка параметров передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="6bf1e-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="6bf1e-106">Создание фильтра для нового URL-адреса</span><span class="sxs-lookup"><span data-stu-id="6bf1e-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="6bf1e-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6bf1e-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6bf1e-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6bf1e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6bf1e-110">На панели навигации слева выберите пункт **сообщение и сведения о присутствии**, а затем щелкните **Фильтр URL-адресов**.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="6bf1e-111">На странице **Фильтр URL-адресов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="6bf1e-112">В списке **выберите сайт**выберите сайт, для которого вы хотите создать фильтр URL-адресов, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="6bf1e-113">В диалоговом окне **Новый фильтр URL-адресов** установите флажок **включить фильтр URL** -адресов, чтобы включить фильтрацию URL-адресов для сайта.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="6bf1e-114">Чтобы заблокировать любой активный URL-адрес, содержащий файл с расширением, указанным в разделе **расширения типа файла, который будет заблокирован** в диалоговом окне **Изменение фильтра файлов**, установите флажок **блокировать URL-адреса с использованием расширения файла** .</span><span class="sxs-lookup"><span data-stu-id="6bf1e-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="6bf1e-115">В раскрывающемся списке " **префикс гиперссылки** " выберите параметр, соответствующий тому, как вы хотите обрабатывать URL-адреса в мгновенных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="6bf1e-116">Окно **Разрешить сообщение** позволяет отправлять пользователю предупреждение при отправке гиперссылок, которые разрешено отправлять.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="6bf1e-117">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6bf1e-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bf1e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6bf1e-118">See Also</span></span>


[<span data-ttu-id="6bf1e-119">Настройка фильтрации файлов и URL-адресов для обмена мгновенными сообщениями (IM) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf1e-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="6bf1e-120">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="6bf1e-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="6bf1e-121">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf1e-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="6bf1e-122">Изменение фильтра URL-адреса по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf1e-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

