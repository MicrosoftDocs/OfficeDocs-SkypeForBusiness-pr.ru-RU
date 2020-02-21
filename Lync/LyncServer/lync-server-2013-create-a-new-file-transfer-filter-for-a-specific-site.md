---
title: 'Lync Server 2013: создание нового фильтра передачи файлов для определенного сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bec5e9e33850fc1da53d370f70b948b7ec6b3f27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="b56dd-102">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="b56dd-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b56dd-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b56dd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b56dd-104">В дополнение к изменению глобального фильтра передачи файлов можно настроить пользовательские фильтры передачи файлов для определенных сайтов в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b56dd-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="b56dd-105">Подробные сведения о фильтрации передачи файлов приведены [в разделе Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="b56dd-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="b56dd-106">Создание фильтра передачи файлов для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="b56dd-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="b56dd-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b56dd-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b56dd-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b56dd-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b56dd-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b56dd-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b56dd-110">В левой области навигации щелкните пункт **Мгновенные сообщения и присутствие**, а затем **Фильтр файлов**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="b56dd-111">На странице **Фильтр файлов** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="b56dd-112">В диалоговом окне **Выбор сайта** щелкните сайт, для которого требуется создать фильтр передачи файлов, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="b56dd-113">В окне **Создание фильтра файлов** установите флажок **Включить фильтр файлов**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="b56dd-114">В раскрывающемся списке **Передача файлов** выберите пункт **Блокировать все** или **Блокировать определенные типы файлов**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="b56dd-115">При выборе варианта **Block All** (Блокировать все) перейдите к действию 10.</span><span class="sxs-lookup"><span data-stu-id="b56dd-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="b56dd-116">При выборе варианта **Блокировать определенные типы файлов** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b56dd-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="b56dd-117">Щелкните **Выбрать**, чтобы изменить список блокируемых расширений файлов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b56dd-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="b56dd-118">В диалоговом окне **Выбор типа файла** выберите типы файлов, которые требуется блокировать или разрешить, добавив или удалив их расширения из категорий в разделе **Расширения типов файлов**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="b56dd-119">Если расширения типов файлов, которые необходимо заблокировать, не отображаются, введите расширение в текстовое поле **Добавить расширения типов файлов в список**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="b56dd-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-120">Click **OK**.</span></span>

10. <span data-ttu-id="b56dd-121">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b56dd-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b56dd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b56dd-122">See Also</span></span>


[<span data-ttu-id="b56dd-123">Настройка передачи файлов и фильтрации URL-адресов для обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b56dd-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="b56dd-124">Создание нового фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="b56dd-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="b56dd-125">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b56dd-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="b56dd-126">Изменение фильтра URL-адресов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b56dd-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

