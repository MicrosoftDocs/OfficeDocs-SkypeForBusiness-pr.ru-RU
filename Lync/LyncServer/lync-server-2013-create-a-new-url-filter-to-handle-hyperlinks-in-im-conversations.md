---
title: Создание нового фильтра URL-адресов для обработки гиперссылок в текстовых беседах
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
ms.openlocfilehash: 889ba5f0582c96fc43445d28bcb669150cfff961
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="861b3-102">Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="861b3-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="861b3-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="861b3-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="861b3-104">В дополнение к изменению глобального фильтра URL-адресов можно настроить фильтры настраиваемых URL-адресов для отдельных сайтов в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861b3-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="861b3-105">Сведения об фильтрации URL-адресов приведены [в статье Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="861b3-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="861b3-106">Создание нового фильтра URL-адресов</span><span class="sxs-lookup"><span data-stu-id="861b3-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="861b3-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="861b3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="861b3-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="861b3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="861b3-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="861b3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="861b3-110">В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр URL-адресов**.</span><span class="sxs-lookup"><span data-stu-id="861b3-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="861b3-111">На странице **Фильтр URL-адресов** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="861b3-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="861b3-112">В диалоговом окне **Выбор сайта** щелкните сайт, для которого требуется создать фильтр URL-адресов, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="861b3-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="861b3-113">В диалоговом окне **Создание фильтра URL-адресов** установите флажок **Включить фильтр URL-адресов**, чтобы включить фильтрацию URL-адресов для сайта.</span><span class="sxs-lookup"><span data-stu-id="861b3-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="861b3-114">Чтобы заблокировать все активные URL-адреса, которые содержат файл с расширением, заданном в разделе **Расширения типов файлов для блокировки** в окне **Редактирование фильтра файлов**, установите флажок **Блокировать URL-адреса с расширением файлов**.</span><span class="sxs-lookup"><span data-stu-id="861b3-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="861b3-115">В раскрывающемся списке **Префикс гиперссылки** выберите вариант, который соответствует тому, как требуется обрабатывать URL-адреса в беседах с обменом мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="861b3-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="861b3-116">Флажок **Разрешить сообщение** позволяет отправку пользователю предупреждающего сообщения, когда отправляются разрешенные для отправки гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="861b3-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="861b3-117">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="861b3-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="861b3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="861b3-118">See Also</span></span>


[<span data-ttu-id="861b3-119">Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861b3-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="861b3-120">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="861b3-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="861b3-121">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861b3-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="861b3-122">Изменение фильтра URL-адресов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861b3-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

